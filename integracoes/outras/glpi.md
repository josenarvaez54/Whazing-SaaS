---
icon: ticket-perforated
---

# GLPI

A integração do **Whazing com o GLPI** permite:

* ✅ **Abertura automática de chamados**
* 🔎 **Consulta de chamados em aberto**
* 🔁 Integração via fila de atendimento

***

### ⚙️ Onde configurar no Whazing

Acesse:

> **Cadastro → Filas → Integrações**

Clique em **Adicionar**.

Você verá duas opções:

* 🆕 **Criar Chamado GLPI**
* 🔍 **Consultar Chamado GLPI**

***

### 🆕 Criar Chamado GLPI

Ao selecionar essa opção, haverá a configuração:

#### ⏱ Intervalo entre Mensagens (ms)

**Tempo de espera para unir mensagens do cliente**

Se o cliente enviar várias mensagens em sequência (mensagens “picotadas”), o sistema aguarda esse tempo para **unificar tudo em um único chamado no GLPI**.

👉 **Recomendado: 15000 ms (15 segundos)** Este é o valor mínimo indicado para evitar múltiplos chamados desnecessários.

***

### 🔐 Dados necessários do GLPI

Para configurar a integração, você precisará informar:

* 🌐 **URL da Integração**
* 🔑 **APP TOKEN**
* 👤 **USER TOKEN**

***

## 🌐 Obtendo a URL da Integração e APP TOKEN

No **GLPI**, acesse:

> **Configurar → Geral → API**

<figure><img src="../../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

#### ✅ Ativar a API

Após ativar a API, cadastre no Whazing no seguinte formato:

```
https://seudominio.com.br/glpi/apirest.php
```

⚠️ **Importante:** Não coloque `/` no final da URL.

***

### 🔑 Gerar APP TOKEN

1. Clique em **Adicionar Cliente de API**

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

2. Deixe o campo **IP em branco** (ou informe o IP da sua VPS)
3. Marque como **Ativo**
4. Marque **Re-gerar**
5. Clique em **Adicionar**

Depois:

* Vá em **Clientes de API**
* Clique no cliente recém-criado
* Copie o campo **Token da Aplicação**

<figure><img src="../../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

***

## 👤 Gerar **User Token** (Usuário Global)

Este usuário será responsável por **criar chamados nas empresas desejadas via API**.

⚠️ Recomendado criar **um usuário exclusivo para integração**, com acesso às empresas que poderão abrir chamados.

### 📌 Como gerar o token

Acesse no GLPI:

**Administração → Usuários**

1. Abra o usuário que será utilizado na integração
2. Role até o final da página
3. Localize o campo **API Token**
4. Clique em **Re-gerar**
5. Salve

O token será exibido.

👉 Copie esse token e utilize no campo **`User_token`** no Whazing.

![](<../../.gitbook/assets/image (7).png>)

***

### 👥 Regras Importantes de Usuários

Além do usuário com token (global), será necessário criar **usuários específicos por empresa** para permitir a identificação correta dos clientes.

#### 🔹 1️⃣ Usuário com Token (Global)

* Terá acesso às empresas desejadas
* Será utilizado **apenas para autenticação da API**
* Deve possuir permissão para criar chamados

***

#### 🔹 2️⃣ Usuários por Empresa (Sem Token)

Para que o sistema funcione corretamente:

* Deve ser criado **um usuário para cada empresa**
* Esses usuários **não precisam de API Token**
* Devem estar vinculados à empresa (Entidade correta)

***

### 🔎 Como funciona a busca do cliente

Quando o Whazing for criar um chamado, o sistema irá:

1. 🔍 Buscar o cliente pelo **telefone (WhatsApp)**
2. Caso não encontre, buscar pelo **e-mail**
3. Se não existir, o cliente será **cadastrado automaticamente**

***

### ⚠️ Configuração Obrigatória

No usuário vinculado à empresa:

* A **Entidade padrão** deve estar configurada corretamente com a empresa correspondente
* O usuário deve possuir:
  * 📧 E-mail cadastrado **ou**
  * 📱 Telefone cadastrado

Sem essas configurações o chamado pode:

* Ser criado na entidade errada
* Não localizar o cliente corretamente
* Falhar na criação automática

***

## 🎯 Configurando a Fila

Defina uma fila para quando o cliente solicitar atendimento humano.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

Depois:

1. Crie uma fila
2. Vincule a integração GLPI
3. Marque a opção **Iniciar ao transferir**

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

***

### 🚀 Como funciona na prática

Basta o **bot transferir o atendimento para essa fila**.

Ao transferir:

* A integração será iniciada automaticamente
* O chamado será criado no GLPI
* O número do chamado poderá ser retornado ao cliente
