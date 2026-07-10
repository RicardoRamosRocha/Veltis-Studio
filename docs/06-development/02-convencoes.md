# Convenções

> Este documento define as convenções de nomenclatura, organização, versionamento e colaboração que deverão ser seguidas durante o desenvolvimento da Orizon Studio.

Versão: 1.0  
Status: Em elaboração

---

# Objetivo

Padronizar a forma como o código, arquivos, pastas, commits e branches serão organizados no projeto.

Convenções bem definidas reduzem dúvidas, evitam inconsistências e aumentam a produtividade.

---

# Idioma

A documentação será escrita em português.

O código deverá utilizar inglês para:

- Classes
- Métodos
- Propriedades
- Interfaces
- Enums
- Pastas técnicas

Exemplos:

```csharp
Project
Customer
Lead
Briefing
Document
Tenant
```

---

# Nomenclatura de Classes

Utilizar PascalCase.

Exemplos:

```csharp
ProjectService
CustomerRepository
LeadController
BriefingViewModel
```

---

# Nomenclatura de Métodos

Utilizar PascalCase.

Exemplos:

```csharp
GetAllAsync()
CreateAsync()
UpdateAsync()
DeleteAsync()
GetByIdAsync()
```

---

# Nomenclatura de Variáveis

Utilizar camelCase.

Exemplos:

```csharp
projectId
customerName
currentTenant
createdAt
```

---

# Interfaces

Interfaces deverão iniciar com `I`.

Exemplos:

```csharp
IProjectService
ICustomerRepository
ITenantProvider
IAiService
```

---

# Entidades

Entidades deverão representar conceitos do domínio.

Exemplos:

```csharp
Tenant
Customer
Lead
Project
Briefing
Document
Proposal
```

---

# Controllers

Controllers deverão terminar com `Controller`.

Exemplos:

```csharp
ProjectsController
CustomersController
LeadsController
BriefingsController
```

---

# Services

Services deverão terminar com `Service`.

Exemplos:

```csharp
ProjectService
CustomerService
LeadService
BriefingService
```

---

# Repositories

Repositories deverão terminar com `Repository`.

Exemplos:

```csharp
ProjectRepository
CustomerRepository
LeadRepository
BriefingRepository
```

---

# ViewModels

ViewModels deverão terminar com `ViewModel`.

Exemplos:

```csharp
ProjectFormViewModel
CustomerDetailsViewModel
LeadIndexViewModel
```

---

# DTOs

DTOs deverão terminar com `Dto`.

Exemplos:

```csharp
ProjectDto
CustomerDto
CreateLeadDto
UpdateProjectDto
```

---

# Enums

Enums deverão utilizar PascalCase.

Exemplos:

```csharp
ProjectStatus
LeadStatus
UserRole
DocumentType
```

---

# Pastas da Solução

Estrutura prevista:

```text
src/
├── OrizonStudio.Domain
├── OrizonStudio.Application
├── OrizonStudio.Infrastructure
├── OrizonStudio.Web
└── OrizonStudio.API
```

---

# Organização da Camada Domain

```text
OrizonStudio.Domain/
├── Entities
├── Enums
├── ValueObjects
├── Interfaces
└── Events
```

---

# Organização da Camada Application

```text
OrizonStudio.Application/
├── Interfaces
├── Services
├── DTOs
├── ViewModels
├── Validators
└── Mappings
```

---

# Organização da Camada Infrastructure

```text
OrizonStudio.Infrastructure/
├── Data
├── Repositories
├── Services
├── Configurations
├── Migrations
└── External
```

---

# Organização da Camada Web

```text
OrizonStudio.Web/
├── Areas
├── Controllers
├── Views
├── ViewModels
├── wwwroot
└── Extensions
```

---

# Organização da Camada API

```text
OrizonStudio.API/
├── Controllers
├── Middleware
├── Models
├── Extensions
└── Swagger
```

---

# Branches

Utilizar a branch principal:

```text
main
```

Para novas funcionalidades, utilizar:

```text
feature/nome-da-funcionalidade
```

Para correções:

```text
fix/nome-da-correcao
```

Para documentação:

```text
docs/nome-do-documento
```

---

# Commits

Utilizar padrão semelhante ao Conventional Commits.

Exemplos:

```text
feat: add customer module
fix: correct project validation
docs: update architecture overview
style: improve dashboard layout
refactor: simplify lead service
chore: update dependencies
```

---

# Migrations

Nomear migrations de forma clara.

Exemplos:

```text
AddTenantFoundation
AddCustomerModule
AddProjectModule
AddBriefingModule
```

---

# Arquivos de Configuração

Não versionar arquivos com segredos.

Arquivos sensíveis:

```text
appsettings.Development.json
.env
secrets.json
```

Utilizar arquivos de exemplo quando necessário:

```text
.env.example
appsettings.example.json
```

---

# CSS

Arquivos CSS deverão ser organizados por responsabilidade.

Exemplos:

```text
site.css
admin.css
design-system.css
landing.css
```

Evitar CSS inline nas Views.

---

# JavaScript

Arquivos JavaScript deverão ser organizados por módulo ou funcionalidade.

Exemplos:

```text
dashboard.js
crm-kanban.js
project-upload.js
briefing-wizard.js
```

Evitar scripts grandes dentro das Views.

---

# Views

Views deverão seguir organização padrão do ASP.NET Core MVC.

Exemplos:

```text
Views/Projects/Index.cshtml
Views/Projects/Create.cshtml
Views/Projects/Edit.cshtml
Views/Projects/Details.cshtml
```

---

# Areas

Utilizar Areas para separar contextos maiores.

Exemplos:

```text
Admin
ClientPortal
```

---

# Considerações Finais

As convenções definidas neste documento deverão ser seguidas por todo o projeto.

Manter padrões consistentes facilitará o desenvolvimento, a revisão de código, a manutenção e a entrada de novos colaboradores na Orizon Studio.