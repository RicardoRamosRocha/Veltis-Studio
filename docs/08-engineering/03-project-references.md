# Project References

> Este documento define a arquitetura de dependências entre os projetos da solução Veltis Studio.

Versão: 1.0
Status: Em elaboração

---

# Objetivo

Garantir que a comunicação entre os projetos siga a Clean Architecture, evitando dependências incorretas e preservando o baixo acoplamento.

---

# Filosofia

A direção das dependências sempre deverá apontar para o centro do domínio.

Nunca o contrário.

---

# Estrutura da Solução

```text
VeltisStudio.sln

│

├── VeltisStudio.Domain
├── VeltisStudio.Application
├── VeltisStudio.Infrastructure
├── VeltisStudio.Web
└── VeltisStudio.API
```

---

# Fluxo das Dependências

```text
          Web
            │
            │
            ▼
     Application
            ▲
            │
Infrastructure
            ▲
            │
          Domain
```

A API seguirá o mesmo padrão da Web.

---

# Domain

Responsável pelo núcleo da aplicação.

Não poderá referenciar nenhum outro projeto.

Responsabilidades:

- Entidades
- Enums
- Interfaces de domínio
- Value Objects
- Eventos de domínio
- Regras de negócio

Dependências:

Nenhuma.

---

# Application

Responsável pelos casos de uso.

Pode referenciar:

- Domain

Não pode referenciar:

- Infrastructure
- Web
- API

Responsabilidades:

- Serviços
- DTOs
- ViewModels
- Validators
- Mappings

---

# Infrastructure

Responsável pela implementação técnica.

Pode referenciar:

- Domain
- Application

Responsabilidades:

- Entity Framework Core
- Repositórios
- Identity
- Storage
- E-mail
- IA
- Serviços externos

---

# Web

Responsável pela interface MVC.

Pode referenciar:

- Domain
- Application
- Infrastructure

Responsabilidades:

- Controllers
- Views
- Layouts
- Razor
- Middleware Web

---

# API

Responsável pelos endpoints REST.

Pode referenciar:

- Domain
- Application
- Infrastructure

Responsabilidades:

- Controllers REST
- Swagger
- JWT
- Integrações

---

# Diagrama Geral

```text
                 Domain
                    ▲
                    │
             Application
              ▲        ▲
              │        │
      Infrastructure   │
          ▲            │
          │            │
         Web          API
```

---

# Inversão de Dependência

Sempre que possível utilizar interfaces.

Exemplo:

```text
Application

↓

ICustomerRepository

↓

Infrastructure

↓

CustomerRepository
```

A Application conhece apenas a interface.

A Infrastructure fornece a implementação.

---

# Dependency Injection

Toda implementação deverá ser registrada através de DI.

Exemplo:

```csharp
services.AddScoped<ICustomerRepository, CustomerRepository>();
```

Evitar criação manual de dependências.

---

# Comunicação entre Contextos

Os módulos deverão interagir preferencialmente através da camada Application.

Evitar dependências diretas entre contextos.

---

# Eventos

Quando apropriado, utilizar eventos de domínio para desacoplar processos.

Exemplos:

- LeadConvertedToCustomer
- ProjectCreated
- ProposalApproved

---

# Integrações Externas

Todas as integrações deverão ficar na Infrastructure.

Exemplos:

- OpenAI
- Google Gemini
- Azure
- Amazon S3
- WhatsApp
- Microsoft Graph

---

# Testes

Os projetos de testes poderão referenciar:

- Domain
- Application
- Infrastructure

Nunca deverão depender da Web para validar regras de negócio.

---

# Evolução

Novos projetos deverão respeitar esta arquitetura.

Exemplos futuros:

```text
VeltisStudio.Mobile

VeltisStudio.Worker

VeltisStudio.BackgroundJobs
```

Esses projetos utilizarão Application como principal ponto de entrada.

---

# Considerações Finais

A arquitetura de referências definida neste documento deverá permanecer estável durante toda a evolução da plataforma.

Qualquer alteração deverá ser cuidadosamente analisada para evitar aumento de acoplamento e perda de manutenibilidade.