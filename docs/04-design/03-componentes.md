# Componentes

> Este documento define os componentes visuais oficiais da Orizon Studio. Todo elemento de interface utilizado na plataforma deverá seguir estes padrões, garantindo consistência visual, reutilização de código e uma experiência uniforme para o usuário.

Versão: 1.0
Status: Em elaboração

---

# Objetivo

Estabelecer um catálogo único de componentes reutilizáveis para toda a plataforma.

Nenhum módulo deverá criar componentes diferentes quando já existir um componente equivalente definido neste documento.

---

# Princípios

Todos os componentes deverão seguir os seguintes princípios:

- Simplicidade
- Consistência
- Reutilização
- Acessibilidade
- Responsividade
- Performance

---

# Botões

## Objetivo

Executar ações do usuário.

## Variantes

- Primário
- Secundário
- Sucesso
- Perigo
- Aviso
- Link
- Ícone

## Estados

- Normal
- Hover
- Focus
- Loading
- Disabled

---

# Cards

## Objetivo

Agrupar informações relacionadas.

## Utilização

- Dashboard
- Estatísticas
- Projetos
- Clientes
- CRM
- Portal do Cliente

Os cards deverão possuir:

- Bordas suaves
- Sombras discretas
- Espaçamento interno consistente

---

# Campos de Entrada

## Componentes

- Input
- Textarea
- Select
- Checkbox
- Radio Button
- Switch
- DatePicker
- TimePicker

Todos deverão apresentar comportamento visual consistente.

---

# Tabelas

## Características

- Responsivas
- Paginação
- Ordenação
- Busca
- Filtros
- Seleção múltipla
- Ações rápidas

As tabelas deverão priorizar legibilidade.

---

# Modais

Utilizados para:

- Confirmações
- Formulários rápidos
- Visualização de detalhes
- Alertas

Evitar modais excessivamente grandes.

---

# Sidebar

A Sidebar será o principal elemento de navegação da plataforma.

Características:

- Recolhível
- Ícones consistentes
- Organização por módulos
- Destaque da página atual

---

# Navbar

A Navbar deverá conter:

- Busca global
- Perfil do usuário
- Notificações
- Acesso rápido
- Configurações

---

# Dashboard Cards

Utilizados para apresentar indicadores.

Exemplos:

- Leads
- Clientes
- Projetos
- Receita
- Conversão
- Pendências

Cada card poderá conter:

- Ícone
- Valor
- Descrição
- Indicador de crescimento
- Link para detalhes

---

# Alertas

Tipos:

- Sucesso
- Informação
- Aviso
- Erro

Todos deverão possuir:

- Ícone
- Título
- Mensagem
- Ação opcional

---

# Toasts

Mensagens rápidas para confirmação de ações.

Exemplos:

- Registro salvo.
- Registro excluído.
- Operação concluída.
- Erro ao processar.

Os Toasts deverão desaparecer automaticamente após alguns segundos.

---

# Badges

Utilizados para representar estados.

Exemplos:

- Ativo
- Inativo
- Em andamento
- Concluído
- Pendente
- Cancelado

Cada status possuirá uma cor padronizada.

---

# Timeline

Utilizada para apresentar histórico.

Exemplos:

- Atividades
- Alterações
- Comentários
- Auditoria

---

# Kanban

Utilizado principalmente no CRM.

Colunas previstas:

- Novo Lead
- Contato
- Reunião
- Proposta
- Negociação
- Fechado

Permitirá movimentação por Drag & Drop.

---

# Stepper

Utilizado em processos divididos por etapas.

Exemplos:

- Configurador Inteligente
- Briefing Digital
- Cadastro de Projeto

---

# Abas (Tabs)

Utilizadas para organizar informações extensas.

Exemplo:

Projeto

- Informações
- Arquivos
- Cronograma
- Comentários
- Financeiro

---

# Upload de Arquivos

Características:

- Drag & Drop
- Barra de progresso
- Pré-visualização
- Múltiplos arquivos
- Cancelamento

---

# Busca

A busca deverá oferecer:

- Pesquisa instantânea
- Sugestões
- Histórico
- Filtros

---

# Paginação

Todas as listagens deverão possuir:

- Número da página
- Total de registros
- Itens por página
- Navegação rápida

---

# Estados Vazios

Quando não houver dados, o sistema deverá apresentar:

- Ilustração
- Mensagem amigável
- Explicação
- Botão de ação

Exemplo:

"Nenhum projeto encontrado."

"Comece cadastrando seu primeiro projeto."

---

# Estados de Carregamento

Sempre que houver processamento, deverão ser utilizados:

- Skeleton Loading
- Spinner
- Barra de progresso

O usuário nunca deverá ficar sem feedback visual.

---

# Componentes Inteligentes

Alguns componentes poderão utilizar Inteligência Artificial.

Exemplos:

- Sugestão de preenchimento
- Resumo automático
- Recomendações
- Autocompletar
- Assistente de escrita

---

# Padronização

Todos os componentes deverão seguir:

- Mesma paleta de cores
- Mesmo espaçamento
- Mesma tipografia
- Mesmas animações
- Mesmo comportamento

Isso garantirá consistência visual em toda a plataforma.

---

# Evolução

Novos componentes poderão ser adicionados ao Design System desde que respeitem os princípios estabelecidos neste documento.

Sempre que possível, novos componentes deverão ser construídos reutilizando elementos já existentes.

---

# Considerações Finais

Os componentes definidos neste documento representam a base visual da Orizon Studio.

Sua utilização consistente permitirá acelerar o desenvolvimento, facilitar a manutenção do código e proporcionar uma experiência de usuário moderna, intuitiva e profissional em toda a plataforma.