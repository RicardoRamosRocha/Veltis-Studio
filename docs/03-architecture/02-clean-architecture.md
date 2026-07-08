# Clean Architecture

> A Veltis Studio adotará a Clean Architecture como padrão para organização do código, separação de responsabilidades e evolução da plataforma.

Versão: 1.0
Status: Em elaboração

---

# Objetivo

A Clean Architecture tem como objetivo criar uma aplicação organizada, testável, desacoplada e preparada para evoluir durante muitos anos sem comprometer a qualidade do código.

Todas as funcionalidades futuras deverão respeitar esta arquitetura.

---

# Benefícios

A utilização da Clean Architecture proporciona:

- Separação de responsabilidades.
- Facilidade de manutenção.
- Facilidade de testes.
- Baixo acoplamento.
- Alta coesão.
- Reutilização de código.
- Independência de frameworks.
- Evolução contínua.

---

# Estrutura da Solução

A solução será composta pelos seguintes projetos.

```text
src/

VeltisStudio.Domain

VeltisStudio.Application

VeltisStudio.Infrastructure

VeltisStudio.Web

VeltisStudio.API
```

Cada projeto possuirá responsabilidades específicas.

---

# Fluxo da Aplicação

```text
          Usuário
              │
              ▼
      ASP.NET MVC (Web)
              │
              ▼
        Application Layer
              │
              ▼
         Domain Layer
              │
              ▼
    Infrastructure Layer
              │
              ▼
          PostgreSQL
```

O fluxo sempre ocorrerá de cima para baixo.

Nenhuma camada poderá violar esta regra.

---

# Domain

A camada Domain representa o coração da plataforma.

Ela não deverá possuir dependência de:

- Entity Framework
- ASP.NET Core
- Banco de Dados
- Frameworks externos

Responsabilidades:

- Entidades
- Value Objects
- Enums
- Interfaces
- Regras de negócio
- Eventos de domínio

---

# Application

A camada Application representa os casos de uso.

Responsabilidades:

- Serviços
- Casos de Uso
- DTOs
- ViewModels
- Validações
- Interfaces
- Mapeamentos
- Orquestração

A camada Application conhece apenas o Domain.

---

# Infrastructure

Responsável pela implementação técnica.

Exemplos:

- Entity Framework Core
- PostgreSQL
- Repositórios
- Upload de Arquivos
- Serviços de E-mail
- Cache
- IA
- Integrações

Toda implementação deverá ficar nesta camada.

---

# Web

Responsável pela interface do usuário.

Contém:

- Controllers
- Views
- Layouts
- Components
- JavaScript
- CSS

A camada Web nunca deverá acessar diretamente o banco de dados.

Toda comunicação ocorrerá através da camada Application.

---

# API

A API permitirá integração com:

- Aplicativos Mobile
- Sistemas externos
- Parceiros
- Futuras integrações

A API compartilhará a mesma camada de domínio da aplicação Web.

---

# Regra das Dependências

As dependências sempre apontam para dentro.

```text
Web
      │
      ▼
Application
      │
      ▼
Domain

Infrastructure
      │
      ▼
Domain
```

O Domain nunca conhecerá nenhuma camada externa.

---

# Injeção de Dependência

Todos os serviços deverão utilizar Dependency Injection.

Exemplo:

- Repositórios
- Serviços
- IA
- Upload
- E-mail
- Cache

Não será permitido instanciar dependências diretamente utilizando `new` quando elas puderem ser resolvidas pelo contêiner de DI.

---

# Comunicação entre Camadas

```text
Controller

↓

Application Service

↓

Repository Interface

↓

Repository

↓

Entity Framework

↓

Database
```

As interfaces deverão ser definidas na camada Domain ou Application, conforme a responsabilidade.

---

# Organização do Código

Cada módulo deverá possuir sua própria organização interna.

Exemplo:

```text
CRM

Application

Domain

Infrastructure

Web
```

O objetivo é manter os módulos independentes e facilitar futuras evoluções.

---

# Boas Práticas

Todo o código deverá seguir:

- SOLID
- Clean Code
- DRY
- KISS
- Convention over Configuration

---

# Testabilidade

A arquitetura deverá permitir:

- Testes Unitários.
- Testes de Integração.
- Testes de Aplicação.
- Testes Automatizados.

Sempre que possível, regras de negócio deverão ser testadas sem necessidade de banco de dados.

---

# Evolução da Arquitetura

A arquitetura deverá permitir:

- Novos módulos.
- Novos provedores de IA.
- Novos tipos de projetos.
- Novas integrações.
- Aplicativos móveis.
- Microsserviços no futuro, caso necessário.

A evolução da plataforma deverá ocorrer sem necessidade de reestruturações profundas.

---

# Considerações Finais

A Clean Architecture será o padrão oficial da Veltis Studio.

Toda implementação deverá respeitar a separação de responsabilidades definida neste documento.

O objetivo não é apenas organizar o código, mas garantir que a plataforma permaneça sustentável, escalável e de fácil manutenção ao longo de sua evolução.