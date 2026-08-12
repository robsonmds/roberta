# Política de Segurança

1. Segurança é etapa obrigatória do ciclo (requisito → runtime), não revisão final.
2. Severidades: LOW corrige · MEDIUM corrige+revisa · HIGH bloqueia até tratar · CRITICAL bloqueia e escala ao Usuário.
3. **Proibido rebaixar severidade** para destravar entrega.
4. Nenhum secret em código, commit, log, PR ou documentação. Exposição = incidente CRITICAL + rotação.
5. Autorização verificada em todo endpoint; autenticação não é autorização.
6. Criptografia apenas com primitivas e bibliotecas maduras. Nunca solução caseira.
7. Menor privilégio e segregação de ambientes em toda a infraestrutura.
8. Todo código gerado por IA é tratado como não confiável até revisão independente.
9. Referências: OWASP Top 10, OWASP ASVS, OWASP SAMM, NIST, CIS Benchmarks, Zero Trust, Secure SDLC.
