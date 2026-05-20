# Configurando o Google Drive como Storage no Gestão Segura

## Visão Geral

O Gestão Segura permite utilizar um Google Drive compartilhado como repositório de arquivos da organização.

Com essa integração, todos os novos anexos enviados pelo sistema passam a ser armazenados diretamente no Google Drive da empresa.

---

# Pré-requisitos

Antes de iniciar a configuração, é necessário:

* Possuir uma conta do Google Workspace
* Ter permissões administrativas no Google Cloud Platform
* Possuir permissão para criar Shared Drives e Service Accounts

> Contas gratuitas do Google não suportam adequadamente este cenário, pois o recurso de Drives Compartilhados (Shared Drives) é necessário para a integração.

---

# Etapa 1 — Criar um Projeto no Google Cloud

Acesse:

https://console.cloud.google.com/

## Passos

1. Clique em **Selecionar Projeto**
2. Clique em **Novo Projeto**
3. Informe:

   * Nome do projeto
   * Organização (se aplicável)
4. Clique em **Criar**

---

# Etapa 2 — Habilitar a Google Drive API

Com o projeto selecionado:

1. Acesse:
   https://console.cloud.google.com/apis/library

2. Pesquise por:

   `Google Drive API`

3. Clique na API

4. Clique em **Ativar**

---

# Etapa 3 — Criar uma Service Account

A Service Account será utilizada pelo Gestão Segura para acessar os arquivos da organização.

## Passos

1. Acesse:
   https://console.cloud.google.com/iam-admin/serviceaccounts

2. Clique em **Criar Conta de Serviço**

3. Informe:

   * Nome da conta
   * ID da conta (gerado automaticamente)

4. Clique em **Criar e Continuar**

5. Não é necessário adicionar permissões adicionais nesta etapa

6. Finalize a criação

---

# Etapa 4 — Gerar a Chave JSON da Service Account

## Passos

1. Abra a Service Account criada

2. Vá até a aba **Chaves**

3. Clique em:

   * **Adicionar Chave**
   * **Criar nova chave**

4. Selecione:

   * Tipo: **JSON**

5. Clique em **Criar**

O arquivo JSON será baixado automaticamente.

> Guarde este arquivo com segurança. Ele será utilizado pelo Gestão Segura para autenticação no Google Drive.

---

# Etapa 5 — Criar um Drive Compartilhado

## Passos

1. Acesse:
   https://drive.google.com/

2. No menu lateral:

   * Clique em **Drives Compartilhados**

3. Clique em:

   * **Novo**

4. Informe o nome do Drive Compartilhado

Exemplo:

* Gestão Segura
* Documentos GS
* Arquivos Corporativos

---

# Etapa 6 — Compartilhar o Drive com a Service Account

Esta é a etapa mais importante da configuração.

A Service Account precisa ter acesso ao Drive Compartilhado para que o Gestão Segura consiga enviar e ler arquivos.

---

## Como identificar o e-mail da Service Account

O e-mail normalmente possui formato semelhante a:

```text
gestao-segura-storage@meu-projeto.iam.gserviceaccount.com
```

---

## Compartilhando o Drive

1. Abra o Drive Compartilhado criado

2. Clique em:

   * **Gerenciar membros**

3. Adicione o e-mail da Service Account

4. Defina a permissão como:

* Editor

5. Salve

> Sem essa permissão, o Gestão Segura não conseguirá enviar arquivos ao Google Drive.

---

# Etapa 7 — Configurar o Gestão Segura

No Gestão Segura:

1. Acesse as configurações da organização

2. Vá até:

   * Storage
   * Google Drive

3. Envie o arquivo JSON da Service Account

4. Informe:

   * ID do Drive Compartilhado (se solicitado)

5. Salve a configuração

---

# Como localizar o ID do Drive Compartilhado

O ID normalmente está presente na URL do Drive.

Exemplo:

```text
https://drive.google.com/drive/folders/0AFxxxxxxxxUk9PVA
```

O ID será:

```text
0AFxxxxxxxxUk9PVA
```

---

# Validação da Configuração

Após salvar, o Gestão Segura realizará validações automáticas:

* Conexão com a Google Drive API
* Acesso ao Drive Compartilhado
* Permissão de leitura
* Permissão de escrita

---

# Problemas Comuns

## Erro: Permissão negada

### Possível causa

A Service Account não foi adicionada ao Drive Compartilhado.

### Solução

Verifique se o e-mail da Service Account foi compartilhado corretamente como Editor.

---

## Erro: API não habilitada

### Possível causa

A Google Drive API não foi ativada no projeto.

### Solução

Ative a API no Google Cloud Console.

---

## Erro: Drive não encontrado

### Possível causa

O ID do Drive está incorreto.

### Solução

Revise o ID informado na configuração.

---

# Importante

Após a configuração:

* Novos arquivos enviados pelo Gestão Segura passarão a ser armazenados no Google Drive configurado
* Arquivos antigos continuarão disponíveis normalmente
* Migração de arquivos antigos pode ser realizada posteriormente sob demanda

---

# Links Oficiais do Google

## Google Drive API

https://developers.google.com/workspace/drive

## Google Cloud Console

https://console.cloud.google.com/

## Service Accounts

https://cloud.google.com/iam/docs/service-accounts-create

## Shared Drives

https://support.google.com/a/users/answer/9310249
