# Integração com IXC Soft (Gateway SMS)

***

## 🔗 Integração com IXC Soft (Gateway SMS)

Este guia mostra como configurar o envio de mensagens via WhatsApp no **IXC Soft**, utilizando integração com API.

***

### ⚙️ 1. Acessar o Painel Administrativo

1. Acesse o painel administrativo do **IXC Soft**
2. No menu lateral esquerdo:
   * Clique na **3ª aba (ícone de engrenagem ⚙️)**

***

### 🔌 2. Acessar Integrações

1. Clique em:\
   **Configurações de Integração**
2. Depois acesse:\
   **Gateway SMS**

***

### ➕ 3. Criar Novo Gateway

1. No menu superior, clique em **Novo**

***

### 🧩 4. Preencher Configuração

Preencha os campos da seguinte forma:

* **Gateway:** `Gammu`
* **URL:**

```
https://testeapi.whazing.com.br/v1/api/external/ixc
```

* **Usuário:**

```
1ec48d55-cbdf-463e-8792-9b798239d76c
```

* **Senha:**

```
SEU_TOKEN_COPIADO
```

***

### 🔑 5. Onde pegar os dados?

Você deve utilizar os dados da sua API:

* URL base:

```
https://testeapi.whazing.com.br/v1/api/external/SEU_ID
```

* **Usuário:**\
  ➡️ É o mesmo ID da URL\
  (ex: `1ec48d55-cbdf-463e-8792-9b798239d76c`)
* **Senha:**\
  ➡️ Token gerado na API

***

### ⚠️ Importante

* O campo **Gateway deve ser "Gammu"**
* O **Usuário sempre será o ID da API**
* A **Senha sempre será o token**
* **Marque opção adicionar fila como sim, limite caracteres pode aumentar pois como não é sms não tem esse limite**
* A URL do gateway deve terminar com:

```
/ixc
```

***

### 🧪 6. Testar Envio

Após salvar:

1. Utilize alguma função de envio de SMS dentro do IXC
2. Faça um envio de teste
3. Verifique se a mensagem chegou no WhatsApp

***

### ✅ Pronto!

Se tudo estiver correto, o IXC estará integrado e enviando mensagens via WhatsApp 🚀

