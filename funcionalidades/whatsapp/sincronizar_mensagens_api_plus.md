---
icon: arrows-rotate
---

# SINCRONIZAR MENSAGENS - API PLUS - WuzApi

## 🔄 Sincronizar Mensagens – API PLUS (WuzApi)

Esta função permite **sincronizar mensagens antigas que não foram importadas automaticamente para o Whazing** após a leitura do QR Code.

> ⚠️ **Importante**
>
> * Apenas mensagens que **já existem no servidor da API Plus ou WuzApi** podem ser sincronizadas.
> * Essa opção **não substitui a importação via Baileys**.
> * Caso precise importar todo o histórico inicial, utilize **Baileys** e, após a importação, **migre para API Plus**.

***

### 📌 Onde é possível sincronizar mensagens

Existem **duas formas de sincronização** disponíveis no sistema:

1. **Sincronizar mensagens de todos os contatos (via Canal)**
2. **Sincronizar mensagens de um contato específico (via Ticket)**

***

### 🔐 Requisito do plano

Para sincronizar mensagens **diretamente pelos canais**, é obrigatório que o plano tenha o recurso:

✅ **Importar Mensagens**

Sem esse recurso ativo, a opção não ficará disponível.

***

### 🔁 Sincronizar mensagens de **todos os contatos** (Canal)

> ⏳ **Atenção:** Esse processo é **extremamente lento**, principalmente em contas com muitos contatos.

#### Como funciona

* O sistema percorre **todos os contatos cadastrados**
* Para cada contato, ele verifica no servidor da **API Plus ou WuzApi** se existem mensagens antigas
* Caso existam, as mensagens são baixadas e salvas no Whazing

📊 **Exemplo prático** Se você tiver **1.000 contatos**, o sistema fará aproximadamente:

* **1.000 sincronizações de JID**
* **1.000 sincronizações de LID** ➡️ Total aproximado: **2.000 sincronizações**

***

#### Passo a passo

1. Acesse: **Configurações → Canais**
2. Com o canal **conectado**, aparecerá a opção **Sincronizar mensagens**

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

3. Informe a **quantidade de mensagens por contato**
   * Valor mínimo: **1**
   * Valor máximo: **100**
4. Clique em **Salvar** para iniciar a sincronização

> ⏳ Durante o processo:
>
> * Não há barra de progresso ou status em tempo real
> * O acompanhamento é feito observando a **criação de novos tickets** no sistema

***

### 🎯 Sincronizar mensagens de **um contato específico**

Essa opção é ideal quando você precisa recuperar mensagens de **apenas um contato**, sem impactar todo o sistema.

#### Pré-requisitos

* ✅ O contato precisa estar **cadastrado**
* ✅ Deve existir um **ticket aberto** para esse contato

#### Passo a passo

1. Cadastre o contato (caso ainda não exista)
2. Abra um novo ticket (se não houver nenhum ativo)
3. No ticket, clique na opção de **Sincronizar mensagens**

<figure><img src="../../.gitbook/assets/sinc (1).png" alt=""><figcaption></figcaption></figure>

4. Informe a **quantidade máxima de mensagens**
   * Limite: **até 100 mensagens**
5. Confirme a ação

📥 Se houver mensagens disponíveis no servidor, elas **começarão a ser baixadas automaticamente** para o ticket.

***

### ✅ Resumo rápido

* 🔄 Sincronização busca mensagens **já existentes** na API Plus ou WuzApi
* 🚫 Não substitui importação completa via Baileys
* 🧾 Pode ser feita:
  * Para **todos os contatos** (via Canal)
  * Para **um contato específico** (via Ticket)
* ⏳ Processo lento e sem progresso visual
* 🔐 Recurso disponível apenas em planos com **Importar Mensagens**
