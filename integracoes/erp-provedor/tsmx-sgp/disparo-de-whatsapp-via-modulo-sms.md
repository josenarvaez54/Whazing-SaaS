---
description: >-
  Este guia mostra como enviar mensagens de WhatsApp utilizando o módulo de SMS
  do sistema SGP.
---

# Disparo de WhatsApp via Módulo SMS

> ⚠️ **Importante:**\
> Esse método funciona **somente com API não oficial do WhatsApp**.

***

### 🔐 1. Criar Token de Acesso da API

Se você ainda não possui um token, siga os passos:

No Whazing

1. Acesse:\
   **Configurações → Canais/API → API**
2. Clique em **Adicionar**
3. Preencha:
   * **Nome:** qualquer nome (ex: "API WhatsApp")
   * **Canal:** selecione **API não oficial WhatsApp**
4. Salve

👉 Após salvar, você terá:

* URL da API
* Token de acesso

Guarde essas informações.

***

### ⚙️ 2. Agora no Painel do SGP

Agora vamos configurar o gateway para envio:

1. Acesse:\
   **Sistema → Gateways → Gateway SMS**
2. Clique em **Adicionar configuração**
3. Preencha:

* **Descrição:** nome que preferir (ex: "WhatsApp API")
* **Gateway:** selecione **HTTP Genérico**

***

#### 🧩 Configuração

No campo de configuração, adicione:

```json
{
  "url": "SUA_URL/sgp",
  "bearertoken": "SEU_TOKEN"
}
```

***

#### ⚠️ Importante

* Sempre adicione **`/sgp` no final da URL**
* Isso é essencial para o funcionamento correto

✔️ Exemplo:

```
https://testeapi.whazing.com.br/v1/api/external/1ec48d55-cbdf-463e-8792-9b798239d76c/sgp
```

***

### ⏱️ 3. Intervalo de Envio

Defina o campo:

**Intervalo (em segundos)**

👉 Recomendação:

* Use um valor **mais alto** (ex: 60s, 120s ou mais)

> ⚠️ Enviar muitas mensagens rapidamente pode:

* Fazer o WhatsApp detectar como spam
* Levar ao **banimento do número**

***

### ⚙️ 4. Outras Configurações

As demais opções podem ser configuradas conforme sua necessidade.

***

### 🧪 5. Testar Envio

Para testar:

1. Acesse:\
   **Sistema → SMS → SMS**
2. Selecione:
   * O gateway criado
3. Preencha:
   * Telefone
   * Mensagem
4. Envie

***

### ✅ Pronto!

Se tudo estiver correto, a mensagem será enviada via WhatsApp 🚀
