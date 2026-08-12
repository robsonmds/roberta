# Roberta — Como instalar e usar

Pacote independente de interface. A mesma organização funciona no Claude Code, no Claude Desktop,
em Projects e via API.

```
roberta/
├── ROBERTA.md          ← o sistema operacional (prompt mestre)
├── CLAUDE.md            ← drop-in para a raiz de um repositório (Claude Code)
├── agents/              ← 40 subagentes + catalog.md
├── templates/           ← ADR, PR, aprovação, security review, DoD, post-mortem, briefing
└── scaffold/.roberta/  ← estrutura de memória para copiar em cada projeto novo
```

---

## 1. Claude Code (recomendado — é onde os subagentes são reais)

### Instalação global (vale para todos os seus projetos)
```bash
mkdir -p ~/.claude/agents
cp roberta/agents/*.md ~/.claude/agents/
cp roberta/ROBERTA.md ~/.claude/ROBERTA.md
```

### Instalação por projeto (versionada com o time)
```bash
cd seu-projeto
mkdir -p .claude/agents
cp -r roberta/agents/*.md .claude/agents/
cp roberta/ROBERTA.md .claude/ROBERTA.md
cp roberta/CLAUDE.md ./CLAUDE.md
cp -r roberta/templates .claude/templates
cp -r roberta/scaffold/.roberta ./.roberta
git add .claude CLAUDE.md .roberta && git commit -m "chore: instala organização Roberta"
```

Verifique com `/agents` dentro do Claude Code. Depois, use naturalmente:
> "Roberta, quero adicionar login com Google neste sistema."

Para acionar um especialista direto:
> "Peça ao appsec-engineer para revisar `src/auth/`."

### Nota sobre `tools:` no frontmatter
Os revisores (`code-reviewer`, `appsec-engineer`, `adversarial-reviewer`, `secrets-guardian`,
`pentester`, `codebase-analyst`) vêm **sem permissão de escrita** de propósito: é assim que se
garante que quem revisa não conserta o próprio achado às escondidas. Se sua versão do Claude Code
usar nomes de ferramentas diferentes, basta remover a linha `tools:` — o agente herda tudo.

---

## 2. Claude Desktop / claude.ai — via Project (melhor opção)

1. Crie um Project chamado **Roberta**.
2. Em **Instruções do projeto**, cole o conteúdo de `ROBERTA.md`.
3. Faça upload, no conhecimento do projeto, de `agents/catalog.md` e dos agentes que usa mais
   (ou de todos, se couber). Adicione também `templates/`.
4. Abra uma conversa e comece com: *"Você é a Roberta. Assuma o papel de CEO/Orchestrator."*

Sem Projects: cole `ROBERTA.md` como primeira mensagem e anexe `agents/catalog.md`.
Neste modo os "subagentes" são **papéis simulados** pelo mesmo Claude — o Orchestrator deve
declarar explicitamente qual agente está falando e manter a separação executor/revisor.

---

## 3. API / outras ferramentas
`ROBERTA.md` vira o system prompt. Cada arquivo de `agents/` vira o system prompt de uma chamada
separada — é o modo que mais respeita a separação de contexto e economiza tokens.

---

## 4. Início de um projeto novo
```bash
cp -r roberta/scaffold/.roberta ./
```
Depois diga: *"Roberta, iniciar projeto. Conduza o discovery."*

## 5. Entrando em um projeto existente
> "Roberta, este repositório já existe. Aplique o protocolo 30.2."

A Roberta **não vai tocar em nada** antes de entregar entendimento, mapa de arquitetura,
dependências, avaliação de segurança, dívida técnica, cobertura, riscos e plano de melhoria.

## 6. Manutenção
- Convenções aprendidas → `.roberta/memory/conventions.md`
- Decisões → `.roberta/project/decisions/ADR-*.md`
- Erros que não podem se repetir → `.roberta/memory/lessons-learned.md`

Peça periodicamente: *"knowledge-curator, consolide a memória do projeto."*
