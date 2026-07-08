# UI Guidelines

> Este documento estabelece as diretrizes para construção das interfaces da Veltis Studio. Seu objetivo é garantir consistência visual, excelente experiência do usuário e padronização em todas as telas da plataforma.

Versão: 1.0
Status: Em elaboração

---

# Objetivo

Padronizar a construção das interfaces da Veltis Studio para que todos os módulos apresentem a mesma identidade visual, comportamento e organização.

Toda nova tela deverá seguir estas diretrizes.

---

# Princípios

A interface deverá transmitir:

- Clareza
- Organização
- Rapidez
- Elegância
- Simplicidade
- Profissionalismo

Cada tela deverá facilitar o trabalho do usuário.

---

# Filosofia

Antes de criar qualquer tela, devemos responder:

- Qual problema esta tela resolve?
- Qual é a ação principal?
- Como reduzir o número de cliques?
- Como tornar a tarefa mais simples?

O design deverá priorizar produtividade acima de efeitos visuais.

---

# Estrutura Geral

A maioria das telas seguirá esta estrutura:

```text
+------------------------------------------------------+
| Navbar                                                |
+------------------------------------------------------+
| Sidebar |                                            |
|         | Header da Página                           |
|         |--------------------------------------------|
|         | Barra de ações                             |
|         |--------------------------------------------|
|         | Conteúdo Principal                         |
|         |                                            |
|         |                                            |
+------------------------------------------------------+
```

---

# Cabeçalho

Cada página deverá possuir:

- Título
- Descrição opcional
- Breadcrumb
- Botões principais

Exemplo:

```text
Projetos

Gerencie todos os projetos cadastrados.

[ Novo Projeto ]
```

---

# Breadcrumb

Utilizar breadcrumb para facilitar navegação.

Exemplo:

```text
Dashboard

>

Projetos

>

Detalhes
```

---

# Barra de Ações

Sempre posicionada no topo do conteúdo.

Pode conter:

- Novo
- Editar
- Excluir
- Exportar
- Importar
- Pesquisar
- Filtros

---

# Formulários

Os formulários deverão ser organizados em grupos lógicos.

Exemplo:

```text
Dados Gerais

Endereço

Responsáveis

Observações

Arquivos
```

Evitar formulários longos sem divisão.

---

# Grid

A interface utilizará sistema de grid responsivo.

Priorizar:

- alinhamento;
- espaçamento uniforme;
- boa leitura.

---

# Espaçamento

Utilizar espaçamentos consistentes.

Evitar componentes "colados".

Toda tela deverá transmitir sensação de organização.

---

# Cards

Utilizar cards para separar grupos de informações.

Cada card deverá conter:

- título;
- descrição opcional;
- conteúdo;
- ações quando necessário.

---

# Dashboards

Os dashboards deverão apresentar apenas informações relevantes.

Priorizar:

- indicadores;
- gráficos;
- tendências;
- alertas;
- tarefas.

Evitar excesso de informações.

---

# CRUDs

Todas as telas CRUD seguirão o mesmo padrão.

## Listagem

- Busca
- Filtros
- Ordenação
- Paginação
- Ações rápidas

## Cadastro

- Botões no topo
- Campos organizados
- Validação imediata
- Mensagens claras

---

# Tabelas

Toda tabela deverá permitir:

- Busca
- Ordenação
- Paginação
- Seleção
- Responsividade

Linhas deverão possuir altura confortável para leitura.

---

# Estados Vazios

Sempre apresentar:

- Ilustração
- Mensagem amigável
- Explicação
- Botão de ação

Exemplo:

"Você ainda não possui projetos cadastrados."

[ Criar Projeto ]

---

# Estados de Carregamento

Toda operação deverá apresentar feedback.

Exemplos:

- Skeleton Loading
- Spinner
- Barra de progresso

---

# Mensagens

As mensagens deverão ser simples.

Evitar:

- códigos técnicos;
- mensagens genéricas.

Exemplo:

✔ Projeto salvo com sucesso.

✘ Exception 500.

---

# Confirmações

Operações destrutivas deverão solicitar confirmação.

Exemplo:

Excluir Projeto

Esta ação não poderá ser desfeita.

[Cancelar]

[Excluir]

---

# Notificações

Utilizar Toasts para:

- Sucesso
- Aviso
- Informação
- Erro

Mensagens deverão desaparecer automaticamente.

---

# Responsividade

A interface deverá adaptar-se para:

- Desktop
- Notebook
- Tablet
- Smartphone

O Desktop continuará sendo a principal prioridade.

---

# Acessibilidade

Toda tela deverá considerar:

- Contraste adequado
- Navegação por teclado
- Labels nos campos
- Componentes acessíveis

---

# Performance

Evitar:

- animações excessivas;
- carregamentos desnecessários;
- excesso de requisições.

A experiência deverá ser fluida.

---

# Consistência

Elementos iguais deverão possuir:

- mesmo comportamento;
- mesma aparência;
- mesmas cores;
- mesmas animações.

O usuário nunca deverá reaprender a utilizar uma tela.

---

# Inteligência Artificial

Sempre que possível, a IA deverá atuar como assistente.

Exemplos:

- preenchimento inteligente;
- sugestões;
- resumos;
- organização automática;
- recomendações.

A IA deverá acelerar o trabalho, sem substituir o controle do usuário.

---

# Considerações Finais

As UI Guidelines representam o padrão oficial para construção das interfaces da Veltis Studio.

Seguir estas diretrizes garantirá consistência visual, excelente experiência do usuário e maior produtividade durante o desenvolvimento.

Toda nova tela deverá respeitar os princípios definidos neste documento, fortalecendo a identidade da plataforma e proporcionando uma experiência premium em todos os módulos.