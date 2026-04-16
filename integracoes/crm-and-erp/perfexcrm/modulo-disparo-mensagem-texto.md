---
description: >-
  Este módulo permite o envio de notificações automáticas de faturas do
  PerfexCRM via WhatsApp, utilizando a API do Whazing. É ideal para lembretes de
  cobrança, avisos de vencimento e comunicação direta
---

# Modulo disparo mensagem texto

## ✅ Compatibilidade

* **PerfexCRM:** versão **3.3.1**
* **PHP:** versão **8.2**

> ⚠️ O módulo foi testado exclusivamente nessas versões. Em versões diferentes, recomenda-se validar antes de usar em produção.

## 📦 Download do módulo

Clique no link abaixo para baixar o módulo de notificação via WhatsApp para o PerfexCRM:

👉 [https://github.com/cleitonme/Whazing-SaaS/raw/refs/heads/main/docs/perfexcrm/modulo%20notificacao%20para%20PerfexCRM%20%20compativel%20com%20api%20do%20whazing.zip](https://github.com/cleitonme/Whazing-SaaS/raw/refs/heads/main/docs/perfexcrm/modulo%20notificacao%20para%20PerfexCRM%20%20compativel%20com%20api%20do%20whazing.zip)

<figure><img src="../../../.gitbook/assets/image (5) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

***

## ⚙️ Instalação e configuração no PerfexCRM

Após instalar o módulo no PerfexCRM, siga os passos abaixo:

1. Acesse o menu: **Configurações → SMS → WhatsApp API Whazing**

<figure><img src="../../../.gitbook/assets/image (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

2. Preencha os dados solicitados com as informações da **API do Whazing**.

***

## 🔑 Obtendo os dados da API Whazing

Para configurar corretamente o módulo, você precisa gerar suas credenciais no Whazing:

1. Acesse o **Painel Whazing**
2. Vá em **Configurações → Canais / API**
3. Crie ou utilize um canal existente
4. Copie os dados de acesso (URL da API, Token, etc.)

Esses dados devem ser informados no campo de configuração do módulo no PerfexCRM.

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

***

## 👤 Cadastro de clientes e contatos

Para que o envio de mensagens funcione corretamente:

* O cliente deve possuir **ao menos um contato cadastrado**
* O contato precisa ter:
  * **Nome**
  * **E-mail**
  * **Telefone (WhatsApp válido)**

📌 O PerfexCRM permite que um cliente tenha **mais de um contato**. O sistema utilizará o telefone cadastrado para o envio das notificações.

***

## ⏱️ Envio automático de mensagens (CRON)

O envio automático das notificações depende da configuração do **CRON do PerfexCRM**.

1. Acesse no PerfexCRM: **Configurações → Cron Job**
2. Configure o CRON conforme orientações oficiais

📖 Documentação oficial do PerfexCRM sobre CRON:

> ⚠️ Sem o CRON configurado corretamente, os envios automáticos não serão executados.
