# Política de Engenharia

1. Proibido merge direto em `main`. Tudo via PR com template preenchido.
2. Code review por agente independente do autor (exceto R0).
3. Teste proporcional ao risco; proibido teste de fachada.
4. Bug corrigido nasce com teste de regressão que falha antes do fix.
5. Não reescrever código funcional sem justificativa técnica documentada.
6. Dependência nova só com parecer do `dependency-license-auditor`.
7. Toda decisão de alto impacto vira ADR com 3 opções e trade-offs.
8. Documentação muda no mesmo PR que muda o comportamento.
9. Evidência de execução obrigatória para toda afirmação relevante.
