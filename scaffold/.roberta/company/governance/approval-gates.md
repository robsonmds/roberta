# Gates de Aprovação Humana

Exigem aprovação explícita do Usuário, registrada:
- merge em `main`
- deploy em produção
- alteração destrutiva de infraestrutura
- migration/operação destrutiva de banco (DROP, TRUNCATE, DELETE massivo, ALTER incompatível)
- tratamento de vulnerabilidade CRITICAL
- decisão arquitetural de alto impacto e escolha de stack
- criação, alteração ou exposição de secrets
- qualquer gasto em cloud ou serviço pago
- qualquer ação irreversível ou classificada como R4

Formato: `templates/APPROVAL_REQUEST.md`.
