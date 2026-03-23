---
description: Suporte à 2ª via de boletos e desbloqueio de confiança (IXC Soft)
---

# IXC Soft

Este tutorial explica, de forma **simples e passo a passo**, como configurar a integração do **IXC Soft** no Whazing para:

* 📄 **2ª via de boletos**
* 🔓 **Desbloqueio de confiança**

⚠️ **Importante:** ao encaminhar o atendimento para a fila da integração, o bot **deve obrigatoriamente solicitar o CPF ou CNPJ do cliente**, pois é essa informação que a integração espera receber.

***

### 📌 O que você vai precisar

* Acesso ao **IXC Soft** com permissão de API
* Dados de acesso à **API do IXC**
* IP da VPS liberado no IXC
* Acesso ao **Whazing** com permissão para criar integrações, filas e bot

***

### 1️⃣ Configurar a Integração no Whazing

Acesse no Whazing:

**Cadastro → Filas - Integrações → Integrações**

Clique em **Adicionar** e selecione a integração do **IXC Soft**. Teremos boleto e uma separa somente desbloqueio de confiança

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### 🌐 URL da integração

⚠️ Atenção total neste ponto (erro comum):

Exemplo de domínio do IXC:

```
https://ixc.whazing.com.br/webservice/v1
```

Na **URL da integração**, preencha **somente**:

```
https://ixc.whazing.com.br
```

* ❌ Não inclua `/webservice/v1`
* ❌ Não coloque `/` no final

#### 🔐 Credenciais da API IXC

* Preencha os dados de acesso da **API do IXC**
* No painel do IXC, libere o **IP da sua VPS** para acesso à API

(As telas abaixo mostram onde configurar isso no IXC) Em caso duvidas entre contato suporte do IXC

***

### 2️⃣ Opções da Integração (muito importante)

Essas opções controlam o comportamento da integração:

#### 🔓 Desbloqueio de Confiança

* Quando ativado:
  * Ao solicitar o boleto, o cliente é **automaticamente desbloqueado por confiança** no IXC

#### 💬 Tipo de interação (Lista / Botões / Copiar e colar)

* Defina conforme o canal utilizado
* Exemplos:
  * WhatsApp: suporta **listas e botões**
  * Telegram: **não suporta botões reply**

⚠️ Se selecionar uma opção que o canal não suporta, a mensagem **não será entregue**.

***

### 3️⃣ Configurar as Filas

Agora vamos criar a fila que utilizará a integração.

Acesse:

**Cadastro → Filas → Adicionar**

Preencha os dados conforme a imagem abaixo:

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### ⚙️ Ajustes importantes da fila

* Marque a opção **Usar integração**
* Selecione a integração do **IXC Soft** criada no passo anterior
* ❌ Não utilize essa mesma fila como fila de erro
*   Deixe **desativada** a opção:

    **“Inicia integração ao transferir”**

***

### 4️⃣ Criar o Chatbot

Agora crie ou edite o chatbot responsável pelo atendimento.

* O bot deve **transferir o atendimento** para a fila da integração
* Antes da transferência, exiba uma mensagem solicitando:

👉 **CPF ou CNPJ do cliente**

Exemplo de mensagem:

> “Para localizar seus boletos, por favor informe seu CPF ou CNPJ.”

***

### 5️⃣ Configurar as Condições do Bot

Nas **Condições** do chatbot:

1. Configure para **rotear o atendimento** para a fila criada
2. Garanta que o cliente tenha informado o **CPF ou CNPJ** antes do envio

Essa informação é essencial para que o IXC retorne os boletos corretamente.

***

### 6️⃣ Funcionamento final (como o cliente vê)

O fluxo funciona da seguinte forma:

1. O cliente conversa com o bot
2. Informa o **CPF ou CNPJ**
3. O sistema consulta o IXC automaticamente
4. Os boletos são listados
5. Se configurado, o cliente é **desbloqueado por confiança**

***

### 🖥️ Telas de configuração no IXC

As imagens abaixo mostram onde configurar permissões e dados no painel do IXC:

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>

***

✅ **Pronto!** A integração do **IXC Soft** está configurada e funcionando.

Você pode ajustar mensagens, tipo de interação e regras de desbloqueio conforme o seu fluxo de atendimento.

🙏 **Agradecimento especial** a **André Alves Magalhães** pelo apoio.
