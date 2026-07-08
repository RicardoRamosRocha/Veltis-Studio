# Checklists

> Este documento reúne os checklists oficiais utilizados durante o desenvolvimento da Veltis Studio, garantindo que todas as etapas sejam executadas de forma consistente antes de commits, releases e deploys.

Versão: 1.0
Status: Em elaboração

---

# Objetivo

Padronizar verificações importantes antes da entrega de qualquer funcionalidade.

O uso destes checklists reduz falhas e melhora a qualidade do produto.

---

# Checklist de Desenvolvimento

Antes de finalizar qualquer funcionalidade verificar:

- Código compilando.
- Sem erros.
- Sem warnings importantes.
- Padrões respeitados.
- Código organizado.
- Comentários desnecessários removidos.

---

# Checklist de Banco de Dados

Verificar:

- Migration criada.
- Migration validada.
- Banco atualizado.
- Relacionamentos corretos.
- Índices revisados.

---

# Checklist de Interface

Confirmar:

- Responsividade.
- Layout consistente.
- Componentes corretos.
- Botões funcionando.
- Mensagens claras.
- Navegação adequada.

---

# Checklist de Segurança

Verificar:

- Autenticação.
- Autorização.
- Tenant.
- Validação de dados.
- Upload seguro.
- Proteção contra ataques comuns.

---

# Checklist de Inteligência Artificial

Quando houver IA verificar:

- Prompt validado.
- Respostas consistentes.
- Tratamento de erros.
- Controle de custos.
- Logs.

---

# Checklist de Testes

Executar:

- Build
- Testes Unitários
- Testes de Integração
- Testes Manuais
- Validação visual

---

# Checklist antes do Commit

Confirmar:

- Código limpo.
- Arquivos corretos.
- Documentação atualizada.
- Sem arquivos temporários.
- .gitignore revisado.

---

# Checklist antes do Push

Executar:

```bash
git status

dotnet build

dotnet test
```

Confirmar que a branch está correta antes de enviar.

---

# Checklist antes do Deploy

Verificar:

- Build concluído.
- Testes aprovados.
- Migrations revisadas.
- Backup disponível.
- Changelog atualizado.
- Ambiente correto.

---

# Checklist Pós Deploy

Após a publicação verificar:

- Sistema disponível.
- Login funcionando.
- Banco atualizado.
- Logs sem erros críticos.
- Performance normal.

---

# Checklist de Documentação

Sempre atualizar quando necessário:

- Business
- Product
- Architecture
- Design
- Marketing
- Development

A documentação deverá evoluir junto com o sistema.

---

# Checklist de Release

Antes de uma nova versão confirmar:

- Funcionalidades concluídas.
- Bugs críticos corrigidos.
- Documentação atualizada.
- Deploy validado.
- Changelog revisado.

---

# Filosofia

Antes de qualquer entrega devemos responder:

- Está funcionando?
- Está organizado?
- Está seguro?
- Está documentado?
- Está preparado para produção?

Se alguma resposta for negativa, a entrega deverá ser reavaliada.

---

# Considerações Finais

Os checklists representam uma etapa obrigatória do processo de desenvolvimento da Veltis Studio.

Seguir estas verificações garantirá maior qualidade, estabilidade e previsibilidade durante a evolução da plataforma, reduzindo retrabalho e aumentando a confiança em cada nova entrega.