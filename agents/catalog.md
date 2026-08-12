# Catálogo de Agentes — Roberta (40)

Agentes são **papéis sob demanda**. O Orchestrator convoca apenas os necessários (§06/§07).
Especialização é **dinâmica por stack**: `backend-engineer` vira especialista em Python/FastAPI,
Node/NestJS ou .NET conforme a decisão de arquitetura do projeto.

## Executivo / Coordenação
| Agente | Quando convocar |
|---|---|
| `ceo-orchestrator` | sempre (ponto único de contato) |
| `engineering-manager` | quando há backlog, dependências ou paralelismo |

## Produto e Experiência
| Agente | Quando convocar |
|---|---|
| `product-manager` | projeto/feature novos, corte de escopo |
| `business-analyst` | regras de negócio complexas |
| `ux-researcher` | produto novo, dúvida sobre uso real |
| `ui-ux-designer` | qualquer interface nova ou redesenho |

## Arquitetura
| Agente | Quando convocar |
|---|---|
| `solution-architect` | desenho de sistemas e integrações |
| `software-architect` | estrutura interna, camadas, padrões |
| `api-designer` | criação/alteração de contrato |
| `tech-evaluator` | qualquer escolha tecnológica relevante |

## Engenharia
| Agente | Quando convocar |
|---|---|
| `frontend-engineer` | UI web |
| `backend-engineer` | serviços, APIs, regras |
| `mobile-engineer` | apps móveis |
| `database-engineer` | schema, migrations, consultas |
| `data-engineer` | pipelines, ETL, analytics |
| `ml-ai-engineer` | funcionalidades de IA/ML |
| `integration-engineer` | APIs de terceiros, webhooks, filas |
| `codebase-analyst` | **obrigatório** ao entrar em repositório existente |

## Segurança
| Agente | Quando convocar |
|---|---|
| `security-architect` | início do projeto, threat model, R3/R4 |
| `appsec-engineer` | toda entrega R2+ |
| `cloud-security-engineer` | mudança de infra/IaC/cloud |
| `pentester` | R4, antes de exposição pública |
| `dependency-license-auditor` | antes de qualquer dependência nova |
| `secrets-guardian` | antes de todo commit/PR |

## Qualidade
| Agente | Quando convocar |
|---|---|
| `qa-engineer` | toda entrega R2+ |
| `test-automation-engineer` | cobertura, suíte, regressão |
| `performance-engineer` | requisito de performance, gargalo |
| `code-reviewer` | toda entrega R1+ |
| `adversarial-reviewer` | R3/R4, antes da aprovação humana |
| `accessibility-specialist` | toda UI relevante |

## Operações
| Agente | Quando convocar |
|---|---|
| `devops-engineer` | CI/CD, containers, ambientes |
| `sre` | confiabilidade, DR, pré-produção |
| `cloud-architect` | infraestrutura em nuvem |
| `release-manager` | antes de merge em main / produção |
| `observability-engineer` | logs, métricas, alertas |
| `incident-responder` | incidente em produção |
| `finops-analyst` | antes de recurso pago, revisão de custo |

## Governança e Conhecimento
| Agente | Quando convocar |
|---|---|
| `compliance-officer` | dado pessoal/financeiro/saúde |
| `technical-writer` | documentação de entrega |
| `knowledge-curator` | início e fim de toda sessão/tarefa |

## Regra de proporcionalidade
- **R0**: 1 agente.
- **R1**: executor + `code-reviewer`.
- **R2**: + `qa-engineer` + `appsec-engineer`.
- **R3**: + `security-architect` + `adversarial-reviewer` + ADR + aprovação humana.
- **R4**: pipeline completo + `pentester` + `release-manager` + aprovação humana registrada.
