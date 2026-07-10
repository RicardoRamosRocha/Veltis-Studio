# Domain Map

> Este documento apresenta o mapa inicial do domínio da Orizon Studio, definindo os principais contextos, entidades e relacionamentos antes da implementação da solução ASP.NET Core.

Versão: 1.0  
Status: Em elaboração

---

# Objetivo

Organizar o domínio da Orizon Studio de forma clara antes da implementação.

Este documento servirá como base para:

- criação das entidades;
- modelagem do banco;
- configuração do Entity Framework Core;
- definição dos módulos;
- organização das pastas;
- futuras regras de negócio.

---

# Filosofia

A Orizon Studio será construída com uma abordagem prática de DDD Lite.

Não utilizaremos DDD de forma excessivamente acadêmica.

O objetivo é ter um domínio organizado, compreensível e preparado para crescer.

---

# Bounded Contexts

A plataforma será organizada inicialmente nos seguintes contextos:

```text
Common

Tenancy

Identity

Marketing

CRM

Projects

Documents

ClientPortal

Dashboard

AI
```

---

# Common

Contexto compartilhado da aplicação.

Responsável por elementos base reutilizados por todos os módulos.

## Componentes

```text
BaseEntity
AuditableEntity
TenantEntity
SoftDelete
DomainEvent
Result
```

---

# Tenancy

Contexto responsável pela estrutura multi-tenant da plataforma.

## Entidades

```text
Tenant
TenantSettings
SubscriptionPlan
TenantSubscription
```

## Responsabilidades

- Representar empresas clientes.
- Isolar dados por empresa.
- Controlar plano contratado.
- Armazenar configurações da empresa.

---

# Identity

Contexto responsável pelos usuários e permissões.

## Entidades

```text
ApplicationUser
ApplicationRole
UserProfile
UserPermission
```

## Responsabilidades

- Autenticação.
- Autorização.
- Perfis de acesso.
- Permissões.
- Usuários vinculados ao Tenant.

---

# Marketing

Contexto responsável pela captação de clientes.

## Entidades

```text
LandingPage
ProjectLibraryItem
ProjectCategory
ProjectConfiguration
MarketingLeadSource
```

## Responsabilidades

- Landing Pages.
- Biblioteca de Projetos.
- Configurador Inteligente.
- Origem de Leads.
- Conteúdos de marketing.

---

# CRM

Contexto responsável pelo relacionamento comercial.

## Entidades

```text
Lead
Customer
Contact
PipelineStage
Opportunity
Proposal
CommercialActivity
FollowUpTask
```

## Responsabilidades

- Captar Leads.
- Converter Leads em Clientes.
- Gerenciar negociações.
- Criar propostas.
- Registrar histórico comercial.

---

# Projects

Contexto responsável pela execução dos projetos contratados.

## Entidades

```text
Project
ProjectStage
ProjectTask
ProjectComment
ProjectApproval
ProjectMember
ProjectTimeline
```

## Responsabilidades

- Gerenciar projetos.
- Controlar etapas.
- Organizar tarefas.
- Registrar comentários.
- Controlar aprovações.

---

# Documents

Contexto responsável por arquivos e documentos.

## Entidades

```text
Document
DocumentVersion
DocumentFolder
DocumentShare
```

## Responsabilidades

- Upload de arquivos.
- Versionamento.
- Organização por pastas.
- Compartilhamento.
- Controle de acesso.

---

# ClientPortal

Contexto responsável pela experiência do cliente final.

## Entidades

```text
ClientPortalAccess
ClientNotification
ClientMessage
ClientApproval
```

## Responsabilidades

- Acesso do cliente.
- Visualização de projetos.
- Aprovações.
- Mensagens.
- Notificações.

---

# Dashboard

Contexto responsável por indicadores e métricas.

## Entidades

```text
DashboardWidget
KpiSnapshot
Report
```

## Responsabilidades

- KPIs.
- Dashboards.
- Relatórios.
- Indicadores comerciais.
- Indicadores operacionais.

---

# AI

Contexto responsável pela inteligência artificial.

## Entidades

```text
AIProvider
AIModel
PromptTemplate
AIExecutionLog
AIRecommendation
```

## Responsabilidades

- Integração com provedores de IA.
- Templates de prompts.
- Logs de execução.
- Controle de custos.
- Recomendações inteligentes.
- Growth Engine.

---

# Fluxo Principal do Domínio

```text
Visitante

↓

Landing Page

↓

Biblioteca de Projetos

↓

Configurador Inteligente

↓

Briefing Digital

↓

Lead

↓

CRM

↓

Proposta

↓

Cliente

↓

Projeto

↓

Portal do Cliente

↓

Entrega

↓

Pós-venda
```

---

# Fluxo Lead → Cliente → Projeto

```text
Lead
  │
  ├── Briefing
  │
  ├── Proposal
  │
  └── CommercialActivity
          │
          ▼
      Customer
          │
          ▼
       Project
          │
          ├── Documents
          ├── Tasks
          ├── Comments
          ├── Approvals
          └── ClientPortal
```

---

# Regras Gerais

## DG-001 — Tenant obrigatório

Toda entidade de negócio deverá possuir `TenantId`.

Exemplos:

- Lead
- Customer
- Project
- Proposal
- Document
- Briefing

---

## DG-002 — Dados globais

Algumas entidades poderão ser globais e não possuir `TenantId`.

Exemplos:

- SubscriptionPlan
- Templates padrão
- Categorias globais
- Configurações da plataforma

---

## DG-003 — Lead pode virar Cliente

Um Lead poderá ser convertido em Customer após o fechamento da negociação.

O histórico comercial deverá ser preservado.

---

## DG-004 — Cliente pode ter vários Projetos

Um Customer poderá possuir múltiplos Projects.

---

## DG-005 — Projeto pode ter vários Documentos

Um Project poderá possuir múltiplos Documents e DocumentVersions.

---

## DG-006 — Documento pode estar ligado a diferentes contextos

Um Document poderá estar relacionado a:

- Customer
- Lead
- Project
- Proposal

A modelagem definitiva deverá evitar excesso de relacionamentos opcionais.

---

## DG-007 — IA atua de forma transversal

A IA poderá apoiar:

- Marketing
- CRM
- Projects
- Documents
- Dashboard
- ClientPortal

---

# Relação entre Contextos

```text
Tenancy
   │
   ├── Identity
   ├── Marketing
   ├── CRM
   ├── Projects
   ├── Documents
   ├── ClientPortal
   ├── Dashboard
   └── AI
```

---

# Organização Inicial no Código

Dentro do projeto `OrizonStudio.Domain`, os contextos poderão ser organizados por pastas:

```text
OrizonStudio.Domain/
├── Common
├── Tenancy
├── Identity
├── Marketing
├── CRM
├── Projects
├── Documents
├── ClientPortal
├── Dashboard
└── AI
```

Cada contexto poderá conter:

```text
Entities
Enums
Interfaces
ValueObjects
Events
```

---

# Decisão Arquitetural

A Orizon Studio não começará com microsserviços.

A plataforma será inicialmente um monólito modular.

Essa decisão permite:

- desenvolvimento mais rápido;
- menor complexidade operacional;
- deploy mais simples;
- evolução controlada;
- possibilidade futura de extração de serviços.

---

# Considerações Finais

Este mapa de domínio representa a primeira visão estruturada do coração da Orizon Studio.

Ele não é definitivo.

O domínio deverá evoluir conforme o produto avançar, mas todas as alterações deverão preservar os princípios centrais:

- clareza;
- organização;
- baixo acoplamento;
- multi-tenant;
- evolução incremental;
- foco em crescimento dos escritórios.

A partir deste documento, a implementação da solução ASP.NET Core poderá começar de forma muito mais segura e orientada.