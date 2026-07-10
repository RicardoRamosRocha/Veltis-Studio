# Coding Standards

> Este documento define os padrões de desenvolvimento utilizados pela Orizon Studio.

Versão: 1.0
Status: Em elaboração

---

# Objetivo

Garantir que todo código produzido na plataforma seja:

- Limpo
- Organizado
- Legível
- Testável
- Consistente

O código deverá ser compreendido facilmente por qualquer desenvolvedor da equipe.

---

# Filosofia

Escrevemos código para pessoas.

O compilador apenas valida.

Sempre priorizar:

- Clareza
- Simplicidade
- Organização
- Manutenibilidade

---

# Princípios

Todo desenvolvimento deverá respeitar:

- SOLID
- DRY
- KISS
- YAGNI
- Clean Code

---

# Nomeação

Classes

PascalCase

```csharp
CustomerService
ProjectRepository
```

---

Métodos

PascalCase

```csharp
CreateAsync()
UpdateAsync()
```

---

Variáveis

camelCase

```csharp
customerName
projectId
```

---

Interfaces

Sempre iniciar com I

```csharp
ICustomerService
```

---

# Métodos

Métodos deverão possuir apenas uma responsabilidade.

Evitar métodos muito grandes.

Preferencialmente:

- até 30 linhas

Quando crescer demais:

extrair novos métodos.

---

# Controllers

Controllers deverão ser finos.

Responsáveis apenas por:

- receber requisição
- validar entrada
- chamar Services
- retornar resposta

Nunca colocar regra de negócio.

---

# Services

Services conterão:

- regras
- validações
- orquestração
- integrações

---

# Repositories

Responsáveis apenas pelo acesso aos dados.

Não colocar lógica de negócio.

---

# Comentários

Evitar comentários desnecessários.

Código limpo deve ser autoexplicativo.

Utilizar comentários apenas quando agregarem contexto.

---

# Strings

Evitar strings mágicas.

Utilizar:

- constantes
- enums

---

# Enums

Sempre utilizar enum quando representar estados.

Exemplo

```csharp
ProjectStatus
LeadStatus
ProposalStatus
```

---

# Async

Sempre utilizar Async/Await em operações de I/O.

---

# Exceptions

Nunca utilizar Exception genérica sem necessidade.

Criar exceções específicas quando fizer sentido.

---

# Logs

Registrar logs em:

- erros
- integrações
- autenticação
- IA
- auditoria

Evitar excesso de logs.

---

# Dependências

Sempre utilizar Dependency Injection.

Nunca instanciar dependências diretamente.

---

# ViewModels

Nunca expor entidades diretamente para Views.

Utilizar ViewModels.

---

# DTOs

Utilizar DTOs em:

- APIs
- integrações
- comunicação entre camadas quando necessário

---

# Validação

Utilizar FluentValidation.

Evitar validações repetidas.

---

# Organização

Cada arquivo deverá conter apenas uma classe pública.

---

# CSS

Nunca utilizar CSS inline.

Toda estilização deverá utilizar o Design System.

---

# JavaScript

Organizar por módulo.

Evitar scripts enormes.

---

# Banco

Nunca acessar banco diretamente em Controllers.

Sempre passar pelos Services e Repositories.

---

# IA

Toda integração deverá passar por interfaces.

Nunca acoplar o código ao provedor.

---

# Performance

Evitar:

- consultas N+1
- carregamentos desnecessários
- loops ineficientes

Sempre pensar em escalabilidade.

---

# Segurança

Sempre considerar:

- Tenant
- Autorização
- Validação
- Upload seguro
- Sanitização

---

# Refatoração

Sempre que identificar repetição significativa, avaliar a extração de componentes reutilizáveis.

Seguir a regra:

"A segunda repetição é um sinal para considerar abstração."

---

# Considerações Finais

Os padrões definidos neste documento deverão orientar todo o desenvolvimento da Orizon Studio.

A consistência do código é um ativo estratégico da plataforma e deverá ser preservada durante toda a evolução do projeto.