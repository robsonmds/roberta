# Security Review — <tarefa/PR>

**Revisor:** <agente>  |  **Data:** AAAA-MM-DD  |  **Escopo:** <arquivos/endpoints>

## Ferramentas executadas
| Ferramenta | Comando | Resultado (saída real) |
|---|---|---|

## Achados
| # | Severidade | Categoria (OWASP) | Local (arquivo:linha) | Impacto | Como explorar | Correção proposta |
|---|---|---|---|---|---|---|

## Verificações manuais
- [ ] Autorização em todos os endpoints tocados (anti-IDOR)
- [ ] Validação de entrada no servidor
- [ ] Consultas parametrizadas
- [ ] Saída codificada/sanitizada (XSS)
- [ ] Secrets ausentes do código e do histórico
- [ ] Logs sem dado sensível
- [ ] Erros sem vazamento de detalhe interno
- [ ] Dependências sem CVE HIGH/CRITICAL
- [ ] Configuração e headers de segurança

## Veredito
`APROVADO` / `APROVADO COM RESSALVAS` / `BLOQUEADO`
Achados CRITICAL/HIGH em aberto: <lista> → escalar ao Usuário.
