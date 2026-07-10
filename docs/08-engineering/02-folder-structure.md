# Folder Structure

> Este documento define a organização oficial das pastas da Orizon Studio, estabelecendo um padrão único para toda a solução.

Versão: 1.0
Status: Em elaboração

---

# Objetivo

Padronizar a estrutura da solução desde o primeiro dia.

Uma organização consistente facilita:

- manutenção;
- navegação;
- onboarding de novos desenvolvedores;
- crescimento da plataforma.

---

# Estrutura Geral

```text
Orizon-Studio
│
├── assets/
├── database/
├── docs/
├── scripts/
├── src/
├── tests/
├── README.md
├── CHANGELOG.md
└── OrizonStudio.sln
```

---

# Assets

Armazenará recursos utilizados na documentação.

```text
assets/

logos/

wireframes/

mockups/

icons/

screenshots/
```

---

# Database

Arquivos relacionados ao banco.

```text
database/

backups/

scripts/

seeds/

views/

functions/
```

---

# Docs

Toda documentação oficial.

```text
docs/

01-business

02-product

03-architecture

04-design

05-marketing

06-development

07-sprints

08-engineering
```

---

# Scripts

Automações.

```text
scripts/

linux/

windows/

docker/

deploy/
```

---

# Source

Código da aplicação.

```text
src/

OrizonStudio.Domain

OrizonStudio.Application

OrizonStudio.Infrastructure

OrizonStudio.Web

OrizonStudio.API
```

---

# Tests

Projeto de testes.

```text
tests/

UnitTests

IntegrationTests
```

---

# Organização do Domain

```text
Domain/

Common/

Tenancy/

Identity/

Marketing/

CRM/

Projects/

Documents/

ClientPortal/

Dashboard/

AI/
```

---

# Common

```text
Common/

Entities/

Enums/

Interfaces/

Events/

ValueObjects/

Results/

Exceptions/
```

---

# CRM

```text
CRM/

Entities/

Enums/

Interfaces/

Services/

Specifications/
```

---

# Projects

```text
Projects/

Entities/

Enums/

Interfaces/

Services/
```

---

# AI

```text
AI/

Entities/

Enums/

Interfaces/

Providers/

Prompts/

Services/
```

---

# Application

```text
Application/

Interfaces/

Services/

DTOs/

ViewModels/

Validators/

Mappings/

Behaviors/
```

---

# Infrastructure

```text
Infrastructure/

Data/

Repositories/

Configurations/

Services/

External/

Identity/

Storage/

Email/
```

---

# Web

```text
Web/

Areas/

Controllers/

Views/

ViewModels/

Extensions/

Filters/

Middleware/

wwwroot/
```

---

# Área Admin

```text
Areas/

Admin/

Controllers/

Views/

ViewModels/
```

---

# API

```text
API/

Controllers/

Middleware/

Extensions/

Models/

Swagger/
```

---

# CSS

```text
wwwroot/

css/

site.css

admin.css

variables.css

components.css

landing.css
```

---

# JavaScript

```text
wwwroot/

js/

dashboard.js

crm.js

projects.js

portal.js

ai.js
```

---

# Uploads

Durante o desenvolvimento:

```text
uploads/

tenants/

customers/

projects/

documents/
```

Em produção poderá ser substituído por armazenamento em nuvem.

---

# Convenções

Cada contexto deverá possuir apenas os arquivos relacionados ao seu domínio.

Evitar dependências cruzadas desnecessárias.

---

# Crescimento

Novos módulos deverão seguir exatamente esta organização.

Exemplos:

```text
Finance/

Marketplace/

Reports/

Notifications/
```

Sem alterar a estrutura existente.

---

# Filosofia

A estrutura da solução deverá permanecer simples.

Sempre que um novo módulo for criado devemos responder:

"Em qual contexto de negócio ele pertence?"

Nunca criar pastas genéricas como:

- Utils
- Misc
- Temp
- Helpers

sem um propósito claramente definido.

---

# Considerações Finais

Esta estrutura deverá permanecer estável durante toda a evolução da plataforma.

A organização consistente facilitará a manutenção do código, reduzirá a complexidade e permitirá que a Orizon Studio cresça sem perder qualidade arquitetural.