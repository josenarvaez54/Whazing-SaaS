---
description: Suporte à 2ª via de boletos e desbloqueio de confiança (HubSoft)
---

# HubSoft

Este tutorial explica, de forma **simples e passo a passo**, como configurar a integração do **HubSoft** no Whazing para:

* 📄 **2ª via de boletos**
* 🔓 **Desbloqueio de confiança**

⚠️ **Importante:** ao encaminhar o atendimento para a fila da integração, o bot **deve obrigatoriamente solicitar o CPF ou CNPJ do cliente**, pois é essa informação que a integração espera receber.

***

### 📌 O que você vai precisar

* Acesso ao **HubSoft** com permissão para API
* Dados de acesso à **API do HubSoft**
* Usuário criado no HubSoft para integração
* Acesso ao **Whazing** com permissão para criar integrações, filas e chatbot

***

### 1️⃣ Configurar a Integração no Whazing

No Whazing, acesse:

**Cadastro → Filas - Integrações → Integrações**

Clique em **Adicionar** e selecione a integração do **HubSoft**.

Preencha os dados conforme mostrado na imagem abaixo:

<figure><img src="../../.gitbook/assets/image (4) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### 🔐 Credenciais da API HubSoft

* Preencha os dados de acesso à **API do HubSoft**
* Essas informações são geradas dentro do painel do HubSoft

***

### 2️⃣ Opções da Integração (muito importante)

Essas opções definem como a integração irá se comportar:

#### 🔓 Desbloqueio de Confiança

* Quando ativado:
  * Ao solicitar o boleto, o cliente é **automaticamente desbloqueado por confiança** no HubSoft

#### 💬 Tipo de interação (Lista / Botões / Copiar e colar)

* Escolha conforme o canal utilizado
* Exemplos:
  * WhatsApp: suporta **listas e botões**
  * Telegram: **não suporta botões reply**

⚠️ Se selecionar uma opção que o canal não suporta, a mensagem **não será entregue** ao cliente.

***

### 3️⃣ Configurar as Filas

Agora vamos criar a fila que utilizará a integração do HubSoft.

Acesse:

**Cadastro → Filas → Adicionar**

Preencha os dados conforme mostrado na imagem abaixo:

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>

#### ⚙️ Ajustes importantes da fila

* Marque a opção **Usar integração**
* Selecione a integração do **HubSoft** criada anteriormente
* ❌ Não utilize essa mesma fila como fila de erro

***

### 4️⃣ Criar o Chatbot

Agora crie ou edite o chatbot responsável pelo atendimento.

* O bot deve **transferir o atendimento** para a fila da integração
* Antes da transferência, exiba uma mensagem solicitando:

👉 **CPF ou CNPJ do cliente**

Exemplo de mensagem:

> “Para localizar seus boletos, por favor informe seu CPF ou CNPJ.”

(Exemplo visual de chatbot)

![](https://doc.whazing.com.br/~gitbook/image?url=https%3A%2F%2F858671661-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252FL28BkT6aCze1NvvWNwS5%252Fuploads%252Fgit-blob-48f570295bea2ee68bff1fee7839ec512a51b87b%252Ftela3.png%3Falt%3Dmedia\&width=300\&dpr=4\&quality=100\&sign=35229649\&sv=2)

***

### 5️⃣ Configurar as Condições do Bot

Nas **Condições** do chatbot:

1. Configure para **rotear o atendimento** para a fila criada
2. Garanta que o cliente tenha informado o **CPF ou CNPJ** antes da transferência

Essa informação é essencial para que o HubSoft retorne os boletos corretamente.

***

### 6️⃣ Funcionamento final (como o cliente vê)

O fluxo funciona da seguinte forma:

1. O cliente conversa com o bot
2. Informa o **CPF ou CNPJ**
3. O sistema consulta o HubSoft automaticamente
4. Os boletos são listados
5. Se configurado, o cliente é **desbloqueado por confiança**

***

### 🖥️ Telas de configuração no HubSoft

As imagens abaixo mostram como criar usuário e configurar a API no HubSoft:

#### ➕ Criar usuário

<figure><img src="../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### 📝 Preencher os dados do usuário

<figure><img src="../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

#### ⚙️ Configuração da API

<figure><img src="../../.gitbook/assets/image (3) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

***

✅ **Pronto!** A integração do **HubSoft** está configurada e funcionando corretamente.

Você pode ajustar mensagens, tipo de interação e regras de desbloqueio conforme o seu fluxo de atendimento.

🙏 **Agradecimento especial** a **Adroaldo Ortolan** pelo apoio.
