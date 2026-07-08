# Arquitetura Multi-Tenant

> A Veltis Studio será desenvolvida como uma plataforma SaaS Multi-Tenant, permitindo que diversos escritórios de engenharia, arquitetura e design utilizem a mesma aplicação de forma segura, independente e isolada.

Versão: 1.0
Status: Em elaboração

---

# Objetivo

Definir como será realizado o isolamento dos dados entre empresas, garantindo segurança, escalabilidade e facilidade de administração.

A arquitetura Multi-Tenant deverá ser transparente para o usuário final e aplicada de forma consistente em toda a plataforma.

---

# Conceito

Cada escritório utilizará a Veltis Studio como se fosse um sistema exclusivo.

Embora todas as empresas compartilhem a mesma infraestrutura da aplicação, seus dados permanecerão completamente isolados.

---

# Modelo Adotado

A Veltis Studio utilizará inicialmente o modelo:

## Banco Compartilhado

Database Shared

↓

Schema Compartilhado

↓

TenantId em todas as entidades

Este modelo oferece:

- Menor custo operacional.
- Facilidade de manutenção.
- Escalabilidade.
- Simplicidade para backups.
- Atualizações centralizadas.

---

# Identificação do Tenant

Cada empresa possuirá um identificador único.

Exemplo:

```text
Tenant

Id

Nome

Domínio

Plano

Status
```

Todas as informações cadastradas estarão vinculadas ao respectivo Tenant.

---

# Isolamento de Dados

Toda entidade pertencente a uma empresa deverá possuir um identificador do Tenant.

Exemplo:

```text
Cliente

Id

TenantId

Nome

Telefone
```

```text
Projeto

Id

TenantId

Nome

Status
```

```text
Lead

Id

TenantId

Nome

Origem
```

---

# Fluxo de Autenticação

```text
Usuário

↓

Login

↓

Identificação do Tenant

↓

Carregamento das Permissões

↓

Acesso à Plataforma

↓

Consultas Filtradas pelo Tenant
```

Após a autenticação, o Tenant será identificado e utilizado automaticamente em todas as operações da aplicação.

---

# Escopo do Tenant

Cada Tenant possuirá seus próprios:

- Usuários
- Clientes
- Leads
- Projetos
- Briefings
- Arquivos
- Dashboard
- Configurações
- Integrações
- Histórico
- Permissões

Nenhuma empresa poderá visualizar dados de outra.

---

# Dados Compartilhados

Algumas informações poderão ser compartilhadas entre todos os tenants.

Exemplos:

- Planos de Assinatura
- Estados
- Cidades
- Categorias padrão
- Templates padrão
- Biblioteca pública de projetos
- Configurações globais

Esses dados serão controlados pela administração da plataforma.

---

# Segurança

Toda consulta deverá considerar automaticamente o Tenant.

Exemplo conceitual:

```text
SELECT *

FROM Projetos

WHERE TenantId = TenantAtual
```

O desenvolvedor não deverá precisar escrever manualmente esse filtro em cada consulta.

---

# Auditoria

Toda operação deverá registrar:

- Tenant
- Usuário
- Data
- Hora
- Operação
- Origem

Permitindo rastreabilidade completa das ações realizadas.

---

# Benefícios

A arquitetura Multi-Tenant proporcionará:

- Escalabilidade.
- Segurança.
- Facilidade de manutenção.
- Redução de custos.
- Atualizações centralizadas.
- Crescimento sustentável.

---

# Evolução Futura

A arquitetura deverá permitir migração futura para outros modelos caso necessário.

Exemplos:

- Database por Tenant.
- Schema por Tenant.
- Infraestrutura dedicada para grandes clientes.

A implementação inicial deverá ser compatível com essas possibilidades.

---

# Boas Práticas

Durante o desenvolvimento deverão ser seguidas as seguintes diretrizes:

- Nunca acessar dados sem considerar o Tenant.
- Nunca compartilhar informações privadas entre empresas.
- Centralizar a resolução do Tenant.
- Evitar duplicação de regras de isolamento.
- Automatizar filtros de acesso sempre que possível.

---

# Considerações Finais

A arquitetura Multi-Tenant é um dos pilares fundamentais da Veltis Studio.

Todo o desenvolvimento da plataforma deverá considerar o isolamento entre empresas como um requisito obrigatório, garantindo que cada escritório utilize a solução com total segurança, privacidade e independência.

A implementação deverá ser simples para o desenvolvedor, transparente para o usuário e preparada para suportar o crescimento contínuo da plataforma.