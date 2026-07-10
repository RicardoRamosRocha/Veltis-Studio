# NuGet Packages

> Este documento define os pacotes NuGet oficiais utilizados pela Orizon Studio.

Versão: 1.0
Status: Em elaboração

---

# Objetivo

Padronizar os pacotes utilizados em toda a solução.

Evitar:

- bibliotecas duplicadas;
- dependências desnecessárias;
- soluções diferentes para o mesmo problema.

---

# Filosofia

Sempre preferiremos:

- bibliotecas oficiais;
- bibliotecas maduras;
- projetos ativos;
- baixo número de dependências.

Menos pacotes significam menor custo de manutenção.

---

# Plataforma

Framework principal

- .NET 8 LTS

Linguagem

- C#

---

# Banco de Dados

## Entity Framework Core

Pacotes

```text
Microsoft.EntityFrameworkCore
Microsoft.EntityFrameworkCore.Design
Microsoft.EntityFrameworkCore.Tools
```

---

## PostgreSQL

```text
Npgsql.EntityFrameworkCore.PostgreSQL
```

---

# Autenticação

ASP.NET Core Identity

```text
Microsoft.AspNetCore.Identity.EntityFrameworkCore
```

---

# Validação

FluentValidation

```text
FluentValidation
FluentValidation.DependencyInjectionExtensions
```

---

# Mapeamento

AutoMapper

```text
AutoMapper
AutoMapper.Extensions.Microsoft.DependencyInjection
```

---

# Logs

Utilizar inicialmente:

```text
Microsoft.Extensions.Logging
```

No futuro poderá ser incorporado:

```text
Serilog
```

Somente quando houver necessidade.

---

# Cache

Primeira versão:

```text
Microsoft.Extensions.Caching.Memory
```

Futuro:

```text
Redis
```

---

# API

Swagger

```text
Swashbuckle.AspNetCore
```

---

# Upload

Inicialmente utilizar:

ASP.NET Core nativo.

Não adicionar bibliotecas externas.

---

# JSON

Utilizar:

```text
System.Text.Json
```

Evitar Newtonsoft.Json, salvo necessidade comprovada.

---

# IA

Inicialmente criar interfaces próprias.

Não acoplar o domínio a SDKs específicos.

Exemplo:

```text
IAIProvider

↓

OpenAI

Gemini

Claude

Azure OpenAI
```

Cada integração ficará isolada na Infrastructure.

---

# Storage

Primeira versão:

Sistema de arquivos.

Futuro:

- Azure Blob Storage
- Amazon S3
- Google Cloud Storage

---

# E-mail

Inicialmente:

```text
MailKit
```

---

# Testes

Unitários

```text
xUnit
```

Mock

```text
Moq
```

Assertions

```text
FluentAssertions
```

---

# Qualidade

Análise estática

```text
Microsoft.CodeAnalysis.NetAnalyzers
```

---

# Documentação

Swagger

Markdown

XML Documentation

---

# Pacotes que NÃO utilizaremos inicialmente

Para manter o MVP simples, evitaremos:

- MediatR
- MassTransit
- Hangfire
- Quartz
- Orleans
- Dapper
- GraphQL
- ElasticSearch

Essas tecnologias poderão ser incorporadas futuramente caso exista necessidade real.

---

# Política para novos pacotes

Antes de adicionar um novo pacote devemos responder:

- Resolve um problema real?
- Existe alternativa nativa?
- O projeto é mantido?
- Vale o custo de manutenção?

Se a resposta for negativa, o pacote não deverá ser adicionado.

---

# Atualizações

Atualizações de pacotes deverão ocorrer de forma planejada.

Evitar atualizar todas as dependências ao mesmo tempo.

---

# Considerações Finais

A Orizon Studio deverá utilizar apenas as bibliotecas realmente necessárias.

A simplicidade da solução será um dos pilares da arquitetura, reduzindo riscos, facilitando manutenção e garantindo maior estabilidade ao longo do tempo.