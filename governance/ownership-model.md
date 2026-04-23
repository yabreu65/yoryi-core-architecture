# Ownership Model

Modelo de ownership por dominio para evitar ambiguedad operacional y cuellos de botella.

## Principios

- Un owner accountable por dominio.
- Responsabilidad distribuida por execution teams.
- Escalamiento explicito para decisiones D2/D3.

## RACI por dominio

| Dominio | Accountable | Responsible | Consulted | Informed |
| --- | --- | --- | --- | --- |
| Constitution/Governance | Principal Architecture | Architecture Team | Security, Platform | All Leads |
| Backend/NestJS | Backend Architecture | Backend Team | Platform | Frontend/AI Leads |
| SaaS/Multi-tenant | SaaS Architecture | Backend + Platform | Security | Product Leads |
| AI/Agents/Runtime | AI Architecture | AI Platform Team | Security, Backend | Product Leads |
| Frontend/Quality | Frontend Architecture | Frontend Team | Backend, Product | Support/Ops |
| Operations Playbooks | SRE/Platform | Platform Team | Domain Tech Leads | All Teams |

## Decision escalation

- D1: owner de dominio decide.
- D2: owner de dominio + review cross-domain.
- D3: decision board (Principal Architecture + owners relevantes).

## Ownership checks

- [ ] Cada doc tiene owner explicito.
- [ ] Cada issue de sprint tiene responsible asignado.
- [ ] Incident commander y backup definidos por dominio.
- [ ] Revisión trimestral de ownership vigente.
