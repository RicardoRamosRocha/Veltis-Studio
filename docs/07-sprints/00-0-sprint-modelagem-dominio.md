# Sprint 0.0 — Modelagem do Domínio

> Esta sprint tem como objetivo definir a base conceitual do domínio da Orizon Studio antes da implementação em ASP.NET Core.

Versão: 1.0  
Status: Planejada

---

# Objetivo

Definir as entidades principais, relacionamentos, padrões de auditoria, multi-tenant e estrutura base do domínio.

Esta sprint evita retrabalho futuro com entidades, migrations e regras mal definidas.

---

# Entidades Base

## BaseEntity

Toda entidade principal deverá herdar de `BaseEntity`.

Campos:

```text
Id
CreatedAt
UpdatedAt
```

---

## AuditableEntity

Entidades auditáveis poderão possuir:

```text
CreatedBy
UpdatedBy
DeletedAt
DeletedBy
IsDeleted
```

---

## TenantEntity

Entidades pertencentes a uma empresa deverão possuir:

```text
TenantId
Tenant
```

---

# Entidades Principais

## Tenant

Representa uma empresa/escritório cliente da plataforma.

Campos iniciais:

```text
Id
Name
Slug
Document
Email
Phone
Status
CreatedAt
UpdatedAt
```

---

## TenantSettings

Configurações específicas de cada empresa.

```text
TenantId
LogoUrl
PrimaryColor
SecondaryColor
Timezone
Language
```

---

## SubscriptionPlan

Plano comercial disponível na plataforma.

```text
Name
Description
Price
MaxUsers
MaxProjects
MaxStorageMb
Active
```

---

## TenantSubscription

Assinatura ativa de uma empresa.

```text
TenantId
SubscriptionPlanId
Status
StartDate
EndDate
NextBillingDate
```

---

## ApplicationUser

Usuário da plataforma.

```text
TenantId
FullName
Email
Phone
Active
```

---

## Customer

Cliente final do escritório.

```text
TenantId
Name
Email
Phone
Document
Address
Notes
```

---

## Lead

Potencial cliente captado pela plataforma.

```text
TenantId
Name
Email
Phone
Source
Status
AssignedToUserId
```

---

## Project

Projeto contratado pelo cliente.

```text
TenantId
CustomerId
Name
Description
Category
Status
StartDate
EndDate
```

---

## Briefing

Informações coletadas antes do início do projeto.

```text
TenantId
LeadId
CustomerId
ProjectType
Objective
Budget
Location
Notes
```

---

## Document

Arquivo relacionado a cliente, lead ou projeto.

```text
TenantId
ProjectId
CustomerId
FileName
FilePath
ContentType
Size
Version
```

---

## Proposal

Proposta comercial.

```text
TenantId
LeadId
CustomerId
Title
Description
Amount
Status
ValidUntil
```

---

# Relacionamentos Principais

```text
Tenant 1:N Users
Tenant 1:N Customers
Tenant 1:N Leads
Tenant 1:N Projects
Tenant 1:N Briefings
Tenant 1:N Documents
Tenant 1:N Proposals

Customer 1:N Projects
Lead 1:1 Briefing
Lead 1:N Proposals
Project 1:N Documents
Project 1:N Comments
Project 1:N Tasks
```

---

# Enums Iniciais

```text
TenantStatus
SubscriptionStatus
LeadStatus
ProjectStatus
ProposalStatus
DocumentType
UserStatus
```

---

# Regras Gerais

## RG-001

Toda entidade de negócio deverá possuir `TenantId`.

## RG-002

Nenhuma consulta poderá retornar dados de outro tenant.

## RG-003

Entidades importantes deverão possuir auditoria.

## RG-004

Exclusões deverão usar Soft Delete sempre que fizer sentido.

## RG-005

Entidades não deverão conter lógica de infraestrutura.

---

# Fora do Escopo

Nesta sprint não implementaremos:

- Controllers
- Views
- APIs
- CRUDs
- Layouts
- IA
- Integrações externas

---

# Critérios de Aceite

A sprint será considerada concluída quando:

- Entidades principais estiverem definidas.
- Relacionamentos estiverem claros.
- Entidades base estiverem planejadas.
- Multi-tenant estiver modelado.
- Auditoria estiver definida.
- Enums iniciais estiverem definidos.

---

# Próxima Sprint

Sprint 0.1 — Estrutura da Solução ASP.NET Core.