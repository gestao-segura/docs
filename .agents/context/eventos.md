# CONTEXTO DE DOMÍNIO: Evento

## Visão geral

O evento representa uma ocorrência de sinistro de veículo dentro do sistema.

Ele é a principal entidade operacional do sistema, sendo responsável por concentrar todas as informações, interações e movimentações dentro de uma esteira.

---

## Terminologia

* Evento = ocorrência de sinistro
* Tipo de evento = classificação da ocorrência

---

## Tipo de Evento

Define a natureza da ocorrência.

### Exemplos

* Colisão
* Incêndio
* Roubo
* Furto

### Observação

* Os tipos são configuráveis pelo cliente
* Cada tipo pertence a uma esteira

---

## Estrutura do Evento

Um evento é composto por múltiplos conjuntos de informações:

---

### 📄 Informações Gerais

Contém os dados principais do evento.

#### Exemplos

* Tipo de evento
* Organização
* Boletim de ocorrência
* Data da ocorrência
* Outras informações administrativas

---

### 👥 Envolvidos

Representa as pessoas relacionadas ao evento.

#### Exemplos

* Associado
* Testemunha
* Proprietário do veículo
* Vítima

---

### 🚗 Veículos

Contém os veículos envolvidos no evento.

---

### 📍 Endereço do Evento

Local onde ocorreu o sinistro.

---

### 🌎 Estrutura Organizacional

Relaciona o evento com a estrutura da operação.

* Regional
* Cooperativa
* Voluntário

---

## Elementos operacionais do Evento

Além das informações principais, o evento possui diversos módulos operacionais:

---

### 📎 Anexos

* Documentos e arquivos relacionados ao evento

---

### 🧾 Tarefas (Formulários)

* Onde os formulários são aplicados
* Representam etapas de coleta de informação
* Cada tarefa corresponde a um formulário aplicado em uma etapa

---

### 💰 Cotações e Ordens

* Cotações
* Ordens de compra
* Ordens de devolução

---

### 📊 Orçamentos

* Controle financeiro relacionado ao evento

---

### 💸 Outras despesas

* Exemplo: guincho
* Custos adicionais associados ao evento

---

### 🏭 Oficinas

* Controle de veículos em oficinas
* Acompanhamento de manutenção e reparos

---

## Histórico e rastreabilidade

O evento mantém rastreabilidade completa:

---

### 🔔 Histórico de notificações

* Notificações enviadas:

  * para usuários
  * para envolvidos

---

### 💬 Histórico de interações

* Comunicação entre usuários do sistema
* Registro de interações operacionais

---

### 📜 Logs

* Registro de tudo que acontece no evento
* Alterações
* Movimentações de etapa
* Execução de ações
* Auditoria completa

---

## Relação com Esteira

* Um evento pertence a uma esteira
* O evento transita entre etapas
* Cada etapa pode aplicar um formulário ao evento

---

## Relação com Formulários

* Formulários são aplicados ao evento ao entrar em uma etapa
* O evento acumula múltiplos formulários ao longo do fluxo
* Apenas o formulário da etapa atual é editável
* Os demais são históricos

---

## Comportamento do Evento

* O evento evolui ao longo da esteira
* Recebe dados via formulários
* Pode sofrer ações automáticas (regras de automação)
* Possui controle de SLA por etapa
* Centraliza toda a operação do sistema

---

## Observações importantes

* O evento é a entidade central do sistema
* Toda informação relevante está associada a ele
* O sistema deve permitir rastreamento completo (auditoria)
* O modelo deve suportar expansão de funcionalidades

---

## Resultado esperado

O sistema deve ser capaz de:

* Representar uma ocorrência completa de sinistro
* Centralizar dados, documentos e interações
* Controlar fluxo via esteira
* Aplicar formulários ao longo do processo
* Registrar todas as ações realizadas
* Permitir evolução sem necessidade de refatoração estrutural
