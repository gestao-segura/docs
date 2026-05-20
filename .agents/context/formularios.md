# CONTEXTO DE DOMÍNIO: Formulários

## Visão geral

O formulário é um dos principais elementos do sistema Gestão Segura.

Ele é utilizado para coletar dados estruturados dentro de um fluxo de processo (esteira), podendo também disparar ações automáticas com base nas respostas.

---

## Estrutura

Um formulário é composto por:

* Formulário

  * Seções

    * Campos

---

## Formulário

Representa um conjunto de informações a serem coletadas.

### Propriedades

* Id
* Nome
* Versão
* Lista de seções

---

## Seção

Agrupa campos relacionados.

### Características

* Possui nome
* Organiza visualmente os campos
* Não possui regra de negócio

---

## Campo

Representa uma unidade de entrada de dados.

### Propriedades

* Id
* TipoDeCampo
* Label
* Placeholder
* Required
* Opções (quando aplicável)
* Dependências (opcional)
* Regras de automação (opcional)
* Grupo de usuários (opcional)

---

# 🔴 DEPENDÊNCIAS (VISIBILIDADE)

Campos podem possuir dependências que controlam sua visibilidade.

## Funcionamento

* A visibilidade de um campo depende da resposta de um ou mais campos anteriores
* Se a condição NÃO for atendida:

  * O campo NÃO deve ser exibido
  * O campo NÃO deve participar do fluxo

## Regras importantes

* Dependências são avaliadas dinamicamente
* Devem reagir a mudanças de valor (tempo real)
* Podem existir múltiplas condições

## Exemplo

* Campo "Motivo" só aparece se "Aprovado" = false

---

# 🔵 REGRAS DE AUTOMAÇÃO (AÇÕES)

Campos podem possuir regras que disparam ações no sistema com base nas respostas.

## Funcionamento

* Baseadas em condições (semelhantes às dependências)
* Podem considerar múltiplos campos
* São avaliadas após interação com o formulário

## Ações possíveis

* Alteração de etapa
* Alteração de esteira
* Clonagem de evento
* Notificação por e-mail
* Notificação por WhatsApp

## Observação importante

* Automação ≠ UI
* Inicialmente, o front NÃO precisa executar essas ações
* Mas precisa respeitar e carregar essa estrutura

---

# 🟢 GRUPO DE USUÁRIOS (CONTROLE DE RESPOSTA)

Um campo pode estar associado a um grupo de usuários.

## Regras

* Se o campo possuir grupo:

  * Apenas usuários pertencentes ao grupo podem responder
* Se NÃO possuir grupo:

  * Qualquer usuário pode responder

## Comportamento no front

* Campo pode estar:

  * editável
  * somente leitura
* Isso depende do usuário atual

---

## Tipos de Campo

O sistema suporta múltiplos tipos:

* Texto
* Área de Texto
* Número
* Dinheiro
* Verdadeiro ou Falso
* Data
* Data e Hora
* Email
* Telefone
* CPF
* CNPJ
* Caixa de Seleção
* Anexo
* Imagem
* Vídeo
* Áudio

---

## Aplicação do formulário

Um formulário NÃO é respondido diretamente.

Ele é:

👉 Aplicado a um evento

---

## Evento

Representa uma instância dentro de um processo.

### Relação com formulário

* Um evento pode ter vários formulários aplicados
* Cada formulário pertence a uma etapa
* Um formulário é sempre aplicado com uma versão fixa

---

## Etapa

Representa um estágio dentro da esteira.

### Regras

* Cada etapa possui no máximo 1 formulário
* Ao entrar na etapa:

  * o formulário é aplicado ao evento
* O formulário aplicado NÃO muda mesmo que o formulário original seja alterado

---

## Formulário aplicado

É a versão do formulário associada ao evento.

### Características

* Contém snapshot da estrutura (seções e campos)
* Não sofre alterações após aplicação
* Pode possuir respostas

---

## Respostas

Cada campo pode possuir uma resposta.

### Estrutura

* IdEvento
* IdFormulário
* IdSeção
* IdCampo
* Valor (tipado)

---

## Comportamento esperado no front

Ao abrir um evento:

* Deve carregar todos os formulários aplicados
* Deve identificar:

  * formulário da etapa atual
  * formulários de etapas anteriores

---

## Regras de UI

* O formulário da etapa atual deve ser editável
* Formulários anteriores devem ser somente leitura
* Os campos devem ser renderizados dinamicamente com base no tipo
* Os campos devem respeitar:

  * dependências (visibilidade)
  * permissões por grupo

---

## Observações importantes

* A estrutura é dinâmica (não hardcoded)
* O front não deve assumir tipos fixos
* O sistema deve ser preparado para novos tipos de campo no futuro
* Regras de automação fazem parte do domínio, mesmo que não executadas no front inicialmente

---

## Resultado esperado

O sistema deve ser capaz de:

* Renderizar qualquer formulário dinamicamente
* Controlar visibilidade de campos com base em dependências
* Respeitar permissões por grupo de usuários
* Preparar base para execução de automações
* Suportar evolução sem necessidade de refatoração estrutural
