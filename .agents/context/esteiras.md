# CONTEXTO DE DOMÍNIO: Esteiras (Processos)

## Visão geral

A esteira é um dos principais conceitos do sistema Gestão Segura.

Ela representa um fluxo de trabalho no formato de quadro Kanban, onde eventos transitam entre etapas.

---

## Terminologia

* Esteira = Processo
* Processo é o termo técnico
* Esteira é o termo de negócio utilizado para evitar ambiguidade com processos de sinistro

---

## Estrutura

Uma esteira é composta por:

* Esteira

  * Tipos de evento
  * Etapas

    * Configurações (formulário, SLA, status)

---

## Esteira

Representa um fluxo de trabalho completo.

### Características

* Pode existir múltiplas esteiras no sistema
* Cada esteira possui seu próprio conjunto de etapas
* Cada esteira define como os eventos devem evoluir

---

## Tipos de Evento

Define a classificação de eventos dentro da esteira.

### Exemplos

* Roubo
* Furto
* Colisão

### Observação

* Um evento pertence a um tipo
* O tipo pode influenciar regras e comportamento do fluxo

---

## Evento

Dentro da esteira, as "tarefas" são chamadas de eventos.

### Características

* Um evento transita entre etapas
* Representa uma instância de trabalho (ex: sinistro)
* Está sempre associado a uma esteira

---

## Etapas (Colunas do Kanban)

Representam os estágios do fluxo.

### Características

* Funcionam como colunas de um quadro Kanban
* Um evento sempre está em uma etapa
* O evento se move entre etapas ao longo do processo

---

## Configurações da Etapa

Cada etapa pode possuir configurações opcionais:

---

### 📄 Formulário

* Uma etapa pode possuir um formulário associado
* Cada etapa possui no máximo 1 formulário
* Ao entrar na etapa:

  * O formulário é aplicado ao evento
* O formulário aplicado é fixo (snapshot)

---

### 🔵 Status / Fases

Define estados possíveis dentro da etapa.

### Exemplo

* Em análise
* Aguardando documentação
* Finalizado

### Observação

* São estados internos da etapa
* Não alteram a posição no Kanban

---

### ⏱️ SLA (Service Level Agreement)

Define o tempo esperado para permanência do evento na etapa.

### Características

* Opcional por etapa
* Pode ser configurado em:

  * minutos
  * horas
  * dias

---

### Configurações do SLA

* Pode utilizar dias úteis ou corridos
* Pode habilitar os níveis:

#### Níveis

* No prazo
* Alerta
* Crítico

---

### Comportamento do SLA

* O SLA acompanha o tempo do evento na etapa
* Pode ser exibido visualmente (ex: cores ou indicadores)
* Pode impactar alertas e automações

---

## Comportamento geral da esteira

* Eventos entram na esteira
* São classificados por tipo
* Transitarem entre etapas
* Podem ter formulários aplicados ao longo do fluxo
* São impactados por SLA e regras de negócio

---

## Relação com formulários

* Cada etapa pode aplicar um formulário
* O formulário coleta dados naquele momento do fluxo
* Os dados coletados podem influenciar:

  * dependências de campos
  * regras de automação
  * movimentação do evento

---

## Observações importantes

* A esteira define o fluxo do sistema
* O comportamento do evento depende da etapa atual
* O sistema deve suportar múltiplas esteiras simultaneamente
* Toda a estrutura é configurável (não fixa)

---

## Resultado esperado

O sistema deve ser capaz de:

* Representar fluxos complexos de trabalho (Kanban)
* Permitir múltiplas esteiras independentes
* Controlar movimentação de eventos entre etapas
* Aplicar formulários ao longo do fluxo
* Monitorar SLA por etapa
* Suportar evolução sem necessidade de refatoração estrutural
