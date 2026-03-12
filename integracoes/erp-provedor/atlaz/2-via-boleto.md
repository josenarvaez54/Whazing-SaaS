# 2 Via Boleto

***

## 📌 O que você vai precisar

* Acesso ao **painel da Atlaz** (usaremos o painel demo como exemplo)
* Acesso ao **Whazing** com permissão para criar integrações e filas

***

## 1️⃣ Acessando o painel da Atlaz

Para este exemplo, utilizaremos o painel demo:

No painel da Atlaz, siga o caminho:

**Painel → Configurações → Recursos**

<figure><img src="../../../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>

### 🔑 Copiar o Token da API

* Localize o **Token da API**
* Copie esse token
* Guarde, pois ele será usado no Whazing

***

## 2️⃣ Criando a integração no Whazing

Agora vamos configurar a integração dentro do Whazing.

Acesse:

**Cadastro → Filas - Integrações → Integrações**

Clique em **Adicionar** e selecione:

👉 **2ª via boleto Atlaz**

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

***

## 3️⃣ Preenchendo os dados da integração

Preencha os campos com atenção:

### 📝 Nome da integração

* Escolha um nome para identificar essa integração no sistema
* Exemplo: `Boleto Atlaz`

### 🌐 URL da integração

*   No painel demo, utilize:

    [**https://demo.atlaz.com.br**](https://demo.atlaz.com.br)

⚠️ **Muito importante:**

* **Não** coloque `/` no final da URL
* **Não** adicione nenhum outro caminho

### 🔄 Fila de transferência (em caso de erro)

* Escolha uma fila para atendimento humano caso ocorra erro
* ❌ **Não utilize a mesma fila da integração**

### 🔐 API Key

* Cole aqui o **token da API** que você copiou no painel da Atlaz

***

## 4️⃣ Opções adicionais da integração

Algumas opções podem ser ativadas conforme sua necessidade:

### ✅ Ativar Desbloqueio de Confiança

* Quando ativado, ao solicitar o boleto:
  * O cliente é automaticamente desbloqueado por confiança

### 💬 Tipo de interação (lista, botões ou copiar/colar)

* Essa opção depende da API/canal utilizado
* Exemplos:
  * WhatsApp: geralmente suporta listas e botões
  * Telegram: **não suporta botões reply**

⚠️ Se ativar uma opção que o canal **não suporta**, a mensagem **não será entregue**.

<figure><img src="../../../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>

***

## 5️⃣ Criando a fila da integração

Agora vamos criar a fila que vai usar essa integração.

1. Crie uma nova **Fila**
2. Marque a opção **Usar integração**
3. Selecione a integração que você acabou de criar

⚠️ Importante:

*   Deixe **desativada** a opção:

    **“Inicia integração ao transferir”**

<figure><img src="../../../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

***

## 6️⃣ Configurando o bot para enviar o cliente à fila

No fluxo do seu bot:

* Configure para **transferir o atendimento** para a fila criada
* Defina uma mensagem ao transferir, solicitando:

👉 **CPF ou CNPJ do cliente**

Exemplo de mensagem:

> “Para localizar seus boletos, por favor informe seu CPF ou CNPJ.”

<figure><img src="../../../.gitbook/assets/image (5) (1) (1).png" alt=""><figcaption></figcaption></figure>

***

## 7️⃣ Arquivo de exemplo do bot

Você pode usar o arquivo abaixo como base para configuração do bot:

{% file src="../../../.gitbook/assets/boletoatlaz.json" %}

***

## 8️⃣ Funcionamento final (como o cliente vê)

1. O cliente chega na fila da integração
2. Digita o **CPF ou CNPJ**
3. O sistema consulta automaticamente a Atlaz
4. Os boletos disponíveis são listados para o cliente

<figure><img src="../../../.gitbook/assets/image (72).png" alt=""><figcaption></figcaption></figure>

***

✅ **Pronto!** Sua integração de **2ª via de boleto Atlaz** está funcionando.

Se quiser, você pode adaptar mensagens, filas e regras conforme o seu fluxo de atendimento.
