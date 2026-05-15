# FEATURE: Nova apresentação comercial de esteiras

## 📌 Identificação

- ID: 20260515131517-apresentacao-esteiras
- Criado em: 15/05/2026 13:15:17
- Status: Draft
- Issue GitHub: [#1](https://github.com/gestao-segura/docs/issues/1)

---

## 🎯 Objetivo

Criar uma nova apresentação independente em `apresentacoes/esteiras/`, com a mesma identidade visual da apresentação de formulários, mas com narrativa comercial sobre o conceito de esteira no SGS.

---

## 🧠 Contexto

A esteira é o quadro Kanban do produto e concentra a lógica de fluxo do evento: tipos de evento, etapas, formulários, SLA, diretórios e guias adicionais.

Essa feature existe para transformar esse conceito em um material claro para o time comercial, destacando valor de negócio, flexibilidade e diferenciação do SGS.

---

## 🧩 Escopo

### Inclui

- Nova apresentação HTML em `apresentacoes/esteiras/`
- Reutilização da identidade visual da apresentação de formulários
- Narrativa comercial sobre esteira, evento, etapas e tipos de evento
- Destaque para configurações de etapa, diretórios e guias adicionais
- Mensagem final orientada a valor para o time comercial

### Não inclui

- Alterar a apresentação existente de `apresentacoes/formularios`
- Alterar regras de produto ou backend
- Gerar PDF ou pacote adicional de distribuição

---

## ⚙️ Requisitos

### Funcionais

- RF01 - A nova apresentação deve existir em um diretório próprio.
- RF02 - A apresentação deve manter a mesma identidade visual da base de formulários.
- RF03 - O conteúdo deve explicar a esteira como fluxo Kanban configurável.
- RF04 - O conteúdo deve destacar tipos de evento, etapas, formulários, SLA, diretórios e guias adicionais.
- RF05 - A apresentação deve comunicar o valor comercial do SGS para o time comercial.

### Não Funcionais

- RNF01 - O layout deve funcionar em 1280x720.
- RNF02 - A nova apresentação deve ser autocontida.
- RNF03 - O conteúdo deve ser legível, consistente e alinhado ao vocabulário do produto.

---

## 🧪 Critérios de Aceite

- Dado que a feature foi implementada, quando abrir `apresentacoes/esteiras/index.html`, então a apresentação deve carregar sem depender da pasta de formulários.
- Dado que a apresentação foi aberta, então a identidade visual deve permanecer coerente com o deck base.
- Dado que o time comercial apresentar o material, então a história deve ficar centrada em valor de negócio e diferenciação.
- Dado que a apresentação for revisada, então diretórios e guias adicionais devem aparecer como parte do entregável.

---

## 🔗 Dependências

- Conteúdo de domínio em `.agents/context/esteiras.md`
- Terminologia complementar em `.agents/context/eventos.md`
- Terminologia complementar em `.agents/context/formularios.md`

---

## 📝 Observações

- A feature deve gerar um entregável separado, não uma variação dentro do deck atual.
- A pasta final esperada é `apresentacoes/esteiras/`.

---

## 🐙 Issue GitHub

- Tipo: feature
- Título: feat: nova apresentacao comercial de esteiras
- Labels:
  - feature
- Tasks relacionadas:
  - Nenhuma no momento
