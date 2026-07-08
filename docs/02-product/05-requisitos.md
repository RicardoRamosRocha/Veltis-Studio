# Requisitos do Sistema

> Este documento descreve os requisitos funcionais e não funcionais da Veltis Studio, servindo como referência para o desenvolvimento, testes e evolução da plataforma.

Versão: 1.0  
Status: Em elaboração

---

# Objetivo

Definir todas as funcionalidades e características técnicas esperadas para a plataforma, garantindo alinhamento entre negócio, desenvolvimento e experiência do usuário.

---

# Requisitos Funcionais

## RF-001 — Autenticação

O sistema deverá permitir que usuários realizem login utilizando e-mail e senha.

---

## RF-002 — Recuperação de Senha

O sistema deverá permitir recuperação de senha por e-mail.

---

## RF-003 — Cadastro de Empresas

O sistema deverá permitir o cadastro de empresas (multi-tenant).

Cada empresa possuirá:

- Usuários
- Clientes
- Projetos
- Configurações
- Arquivos

isolados das demais empresas.

---

## RF-004 — Gestão de Usuários

O sistema deverá permitir:

- Cadastro
- Edição
- Exclusão
- Ativação
- Desativação

de usuários.

---

## RF-005 — Controle de Permissões

O sistema deverá possuir controle de acesso baseado em perfis.

Exemplos:

- Administrador
- Gestor
- Engenheiro
- Arquiteto
- Designer
- Colaborador

---

## RF-006 — Biblioteca de Projetos

O sistema deverá permitir:

- Cadastro de projetos
- Categorias
- Busca
- Filtros
- Favoritos
- Destaques

---

## RF-007 — Configurador Inteligente

O cliente deverá conseguir:

- Escolher um modelo
- Personalizar características
- Salvar configurações
- Solicitar orçamento

---

## RF-008 — Briefing Digital

O sistema deverá permitir:

- Perguntas dinâmicas
- Upload de arquivos
- Upload de imagens
- Localização do terreno
- Observações

---

## RF-009 — CRM

O sistema deverá permitir:

- Cadastro de Leads
- Histórico
- Pipeline Comercial
- Agenda
- Follow-up
- Tarefas

---

## RF-010 — Gestão de Projetos

O sistema deverá permitir:

- Cadastro de projetos
- Cronograma
- Comentários
- Checklist
- Aprovações
- Histórico

---

## RF-011 — Portal do Cliente

O cliente deverá visualizar:

- Projetos
- Arquivos
- Cronograma
- Aprovações
- Mensagens
- Histórico

---

## RF-012 — Gestão de Documentos

O sistema deverá permitir:

- Upload
- Download
- Versionamento
- Organização por pastas

---

## RF-013 — Dashboard

O sistema deverá apresentar indicadores como:

- Leads
- Clientes
- Projetos
- Receita
- Conversão

---

## RF-014 — Inteligência Artificial

O sistema deverá utilizar IA para:

- Resumir briefings
- Recomendar projetos
- Gerar resumos
- Auxiliar na gestão comercial
- Sugerir melhorias

---

## RF-015 — Auditoria

O sistema deverá registrar:

- Inclusões
- Alterações
- Exclusões
- Login
- Acessos

---

# Requisitos Não Funcionais

## RNF-001 — Performance

As páginas deverão carregar em até 2 segundos em condições normais de uso.

---

## RNF-002 — Responsividade

O sistema deverá funcionar corretamente em:

- Desktop
- Notebook
- Tablet
- Smartphone

---

## RNF-003 — Segurança

A autenticação deverá utilizar ASP.NET Core Identity.

As senhas deverão ser armazenadas utilizando hash seguro.

---

## RNF-004 — Multi-Tenant

Cada empresa deverá possuir dados completamente isolados.

---

## RNF-005 — Escalabilidade

A arquitetura deverá permitir crescimento sem necessidade de reestruturação significativa.

---

## RNF-006 — Disponibilidade

A plataforma deverá buscar disponibilidade mínima de 99,9%.

---

## RNF-007 — Backup

Os dados deverão possuir rotina automática de backup.

---

## RNF-008 — Banco de Dados

O banco de dados deverá utilizar PostgreSQL.

---

## RNF-009 — Arquitetura

O sistema deverá utilizar:

- ASP.NET Core 8+
- Clean Architecture
- Entity Framework Core
- REST API
- Dependency Injection

---

## RNF-010 — Interface

A interface deverá seguir um Design System único.

Características:

- Moderna
- Responsiva
- Premium
- Acessível
- Consistente

---

## RNF-011 — Inteligência Artificial

A arquitetura deverá permitir integração com múltiplos provedores de IA.

Exemplos:

- OpenAI
- Google Gemini
- Anthropic Claude
- Azure OpenAI

---

## RNF-012 — Logs

O sistema deverá registrar logs de:

- Erros
- Auditoria
- Requisições
- Integrações

---

## RNF-013 — API

Todas as funcionalidades principais deverão ser acessíveis por meio de APIs REST.

---

## RNF-014 — Versionamento

Documentos deverão possuir histórico de versões.

---

## RNF-015 — LGPD

O sistema deverá atender aos princípios da Lei Geral de Proteção de Dados (LGPD), permitindo gerenciamento de consentimento, privacidade e exclusão de dados quando aplicável.

---

# Critérios Gerais

Todos os requisitos deverão ser:

- Claros
- Objetivos
- Testáveis
- Mensuráveis
- Rastreáveis

Sempre que um novo módulo for criado, seus requisitos deverão ser incorporados a este documento.

---

# Considerações Finais

Este documento representa a base funcional e técnica da Veltis Studio.

Os requisitos aqui descritos deverão orientar o desenvolvimento de todos os módulos da plataforma, garantindo consistência, qualidade e alinhamento com a visão do produto.

Novos requisitos poderão ser adicionados conforme a evolução do projeto e o feedback obtido com clientes reais.