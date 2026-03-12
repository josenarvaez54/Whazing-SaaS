---
description: Como Configurar Proxy para Conexões do WhatsApp
icon: network-wired
---

# Configurar Proxy para Conexões do WhatsApp

O sistema permite configurar **proxy para conexões do WhatsApp**, aumentando a segurança e permitindo melhor controle de rede.

O proxy pode ser configurado de **duas formas**:

1. **Globalmente no arquivo `.env`**
2. **Individualmente por canal nas configurações**

Suporte para:

* Baileys
* Wuzapi

***

## 📌 Informações importantes sobre Proxy

⚠️ **Sempre reinicie a conexão após alterar proxy**

O sistema possui mecanismos automáticos de segurança:

🔒 **Proxy inválido**

* Se o proxy configurado for inválido, o sistema **desativa automaticamente**.

🔄 **Erro de conexão**

* Se houver falha de conexão usando proxy, o sistema:
  1. remove o proxy automaticamente
  2. tenta conectar **sem proxy**

Isso evita que a conexão do WhatsApp fique offline.

***

## 📍 Quando usar Proxy

Recomendado quando:

* você usa **servidores em cloud**
* quer **reduzir risco de bloqueio**
* precisa **gerenciar múltiplos números**
* deseja **separar IP das conexões**

***

## ⚙️ Método 1 — Configurar Proxy no `.env`

Esta configuração aplica **proxy global para todas as conexões**.

***

## 1️⃣ Acessar o servidor

Conecte no servidor usando SSH ou SFTP.

Um cliente comum é o **Bitvise SSH Client**.

***

## 2️⃣ Localizar o arquivo `.env`

Caminho padrão:

```
/home/deploy/whazing/backend/.env
```

***

## 3️⃣ Editar o arquivo `.env`

Abra o arquivo e adicione:

```env
# Configurar proxy para conexões do WhatsApp
PROXY_URL=socks5://127.0.0.1:9150

# Validar se proxy do .env é válido
PROXY_URL_VALID=true
```

***

## 📌 Explicação dos parâmetros

| Configuração      | Função                     |
| ----------------- | -------------------------- |
| PROXY\_URL        | endereço do proxy          |
| PROXY\_URL\_VALID | ativa validação automática |

***

## 📌 Exemplos de Proxy

#### SOCKS5

```
socks5://127.0.0.1:9150
```

#### Proxy com usuário e senha

```
socks5://usuario:senha@127.0.0.1:9150
```

#### HTTP Proxy

```
http://127.0.0.1:8080
```

***

## 4️⃣ Salvar alterações

Depois de editar o `.env`, salve o arquivo.

***

## 5️⃣ Reiniciar backend

Execute:

```bash
docker container restart whazing-backend
```

***

## ⚙️ Método 2 — Configurar Proxy por Canal

Outra opção é configurar **proxy individualmente em cada canal**.

Isso permite usar **IPs diferentes para cada número de WhatsApp**.

***

## 1️⃣ Acessar painel do sistema

Abra o painel administrativo.

Caminho:

```
Configurações → Canais-API
```

***

## 2️⃣ Configurações

Selecione o canal desejado e clique em **configurações**.

***

## 3️⃣ Adicionar proxy

No campo de proxy adicione o endereço.

Exemplo:

```
socks5://127.0.0.1:9150
```

***

## ⚠️ Importante

Após alterar proxy no canal:

🔄 **É necessário reiniciar a conexão do WhatsApp**

Isso aplica a nova configuração.

***

## 🔎 Validação automática do Proxy

O sistema possui proteção automática.

Se o proxy apresentar erro:

1️⃣ o sistema detecta falha\
2️⃣ remove o proxy\
3️⃣ tenta conectar sem proxy

Isso evita que o WhatsApp fique desconectado.

***

## 🧪 Como testar se proxy está funcionando

Após configurar:

1. reinicie a conexão do WhatsApp
2. observe os logs do sistema

Execute:

```bash
docker logs --tail 100 -f whazing-backend
```

***

## ⚠️ Problemas comuns

#### Proxy não conecta

Verifique:

* IP
* Porta
* Usuário e senha
* Tipo de proxy

***

#### WhatsApp não conecta com proxy

Pode ser:

* proxy bloqueando websocket
* proxy lento
* proxy inválido

O sistema irá **remover automaticamente o proxy**.

***

## ✔️ Resumo da Configuração

#### Proxy global

```env
PROXY_URL=socks5://127.0.0.1:9150
PROXY_URL_VALID=true
```

***

#### Reiniciar backend

```bash
docker container restart whazing-backend
```

***

#### Proxy por canal

Painel:

```
Configurações → Canais → Configurações
```

Adicionar proxy.

***

## 💡 Boas práticas

* utilize **proxy SOCKS5**
* evite proxies gratuitos
* use **IPs dedicados**
* monitore logs regularmente
* use proxy residencial

Alguns fornecedores proxy

{% embed url="https://iproyal.com/" %}

{% embed url="https://brightdata.com/" %}

{% embed url="https://www.webshare.io/" %}

***

✅ Com proxy configurado corretamente você terá:

* maior estabilidade
* melhor controle de IP
* redução de bloqueios do WhatsApp

***
