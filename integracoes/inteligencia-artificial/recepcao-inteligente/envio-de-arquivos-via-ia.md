---
icon: paperclip-vertical
---

# Envio de Arquivos via IA

O sistema permite que a IA envie arquivos automaticamente durante o atendimento utilizando o comando:

```json
{ "sendFile": ID }
```

Esse comando faz com que o sistema envie um arquivo previamente cadastrado.

***

### 📎 Correspondência Semântica de Arquivos

Agora o sistema também pode **encontrar e enviar arquivos automaticamente** com base na mensagem do cliente, utilizando busca por similaridade (semântica).

Isso permite que documentos relevantes sejam enviados mesmo quando o cliente não usa exatamente o mesmo termo.

***

### ⚙️ Configurações

#### 🎯 Similaridade Mínima

Define o nível mínimo para considerar um arquivo como relevante.

Valor entre **0.5 e 1.0**

* **0.72** → equilíbrio ideal (recomendado)
* Valores menores → mais resultados, porém menos precisos
* Valores maiores → mais preciso, porém mais restrito

***

#### 🚀 Limiar de Envio Automático

Define quando o arquivo será enviado automaticamente, sem depender da decisão da IA.

Valor entre **0.5 e 1.0**

* **0.88** → recomendado para envio seguro
* Acima desse valor → arquivo é enviado automaticamente
* Abaixo disso → a IA decide se deve enviar ou não

***

### 🧠 Como funciona

* O sistema analisa a mensagem do cliente
* Compara com os arquivos disponíveis
* Calcula a similaridade
* Se atingir o nível configurado:
  * Pode sugerir o arquivo para a IA
  * Ou enviar automaticamente (dependendo da configuração)

***

### 💡 Dica

Use um valor de envio automático mais alto para evitar envios indevidos e garantir que apenas arquivos realmente relevantes sejam enviados 👍

***

## 🧠 Como Funciona

Quando a IA incluir no retorno:

```json
{ "sendFile": ID }
```

O sistema irá:

* 📎 Localizar o arquivo correspondente ao **ID**
* 📤 Enviar o arquivo automaticamente para o cliente

⚠️ Importante:\
Você deve substituir **ID** pelo ID real do arquivo cadastrado no sistema.

***

## 🎯 Quando Usar?

Você pode configurar o envio de arquivo de duas formas:

#### ✅ 1. Por Etapa Específica

Quando o atendimento chegar em determinada etapa, o arquivo é enviado.

#### ✅ 2. Por Palavra-chave

A IA analisa a conversa e decide enviar o arquivo quando detectar determinado assunto.

***

## 📌 Exemplo Prático – Disparo em Massa / Campanha

<figure><img src="../../../.gitbook/assets/image (92).png" alt=""><figcaption></figcaption></figure>

#### 🧩 Regra configurada:

Se o cliente perguntar sobre:

* disparo em massa
* campanha
* envio em massa
* marketing

***

#### 🤖 Exemplo prompt

```
Quando o cliente perguntar sobre DISPARO EM MASSA ou CAMPANHA:

Responda:
"Sim, é possível fazer disparo em massa! Temos suporte para 
campanhas com API oficial e não oficial, com botões ou texto 
normal.

Mais informações: https://doc.whazing.com.br/funcionalidades/automacao/campanha"

E envie comando "ENVIAR ARQUIVO": "tela da campanha" usando comando { "sendFile": 12 }
```

Onde:

```
ID = ID real do arquivo "tela da campanha"
```

***

## ⚠️ Regras Importantes

* O comando `{ "sendFile": ID }` deve estar exatamente nesse formato.
* O ID precisa ser válido e existir no sistema.
* A IA deve enviar o comando separado ou conforme padrão definido pelo sistema.
* Teste sempre antes de colocar em produção.

***

## 🚀 Benefícios

* 📎 Envio automático de manuais, imagens ou PDFs
* 🎯 Material enviado no momento certo
* 🤖 Atendimento mais profissional
* ⏱️ Reduz trabalho manual do operador

***

## ✅ Resultado Final

Com essa configuração:

1. Cliente menciona tema específico
2. IA identifica intenção
3. Responde normalmente
4. Sistema envia arquivo automaticamente

Isso transforma o atendimento em um processo **mais automatizado, visual e eficiente** 🚀
