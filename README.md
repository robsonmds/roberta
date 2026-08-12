# Roberta — Organização Virtual de Engenharia de Software

Pacote pronto para instalar no Claude Code, Claude Desktop, Projects ou API.
Construído a partir da especificação de requisitos (respostas 1–66) do documento de origem.

| Arquivo | O que é |
|---|---|
| `ROBERTA.md` | Sistema operacional da organização — 30 seções: princípios, hierarquia, delegação, níveis de risco, segurança, QA, revisão adversarial, Git, gates de aprovação, memória, anti-alucinação, anti-vibe-coding, protocolo de execução |
| `CLAUDE.md` | Versão resumida para a raiz de um repositório (Claude Code lê automaticamente) |
| `agents/` | 40 contratos de agentes + `catalog.md` com a regra de convocação |
| `templates/` | ADR, Pull Request, pedido de aprovação, briefing de delegação, security review, Definition of Done, post-mortem |
| `scaffold/.roberta/` | Estrutura de memória persistente para copiar em cada projeto |
| `INSTALACAO.md` | Como instalar em cada superfície |

## Decisões adotadas por padrão (perguntas 67–72, não respondidas na origem)

| # | Tema | Padrão adotado | Como mudar |
|---|---|---|---|
| 67 | CEO e Orchestrator são o mesmo interlocutor | **Sim** — dois chapéus, um agente (`ceo-orchestrator`) | separar em dois arquivos de agente |
| 68 | Comportamento proativo (discovery antes de codar) | **Sim** — obrigatório em pedido amplo (§04) | remover o bloco "Comportamento proativo" |
| 69 | Agentes podem contestar o Usuário | **Sim**, com decisão final sempre do Usuário (§02.10, §04) | ajustar princípio 10 |
| 70 | Proporcionalidade ao risco | **Sim** — níveis R0–R4 (§07) | ajustar a tabela de risco |
| 71 | Independente de interface (Desktop + Code) | **Sim** — regras não citam ferramenta específica | — |
| 72 | Criar e manter a estrutura `.roberta/` | **Sim** — memória mora no projeto, não na conversa (§20) | remover `scaffold/` e a §20 |

Se algum desses padrões não for o desejado, o ajuste é local e não afeta o resto do sistema.

## Como começar em 3 passos
1. Instale conforme `INSTALACAO.md`.
2. Copie `scaffold/.roberta/` para o projeto.
3. Diga: **"Você é a Roberta. Assuma o papel de CEO/Orchestrator."**
