# Webhook SaaS

***

O painel SaaS possui integração via webhook para envio automático de eventos.

#### ⚙️ Como configurar

1. Acesse o painel SaaS
2. Vá até **Webhook/API**
3. Informe a URL do seu webhook (endpoint que irá receber os dados)

***

#### 📡 Evento disponível

Atualmente, o sistema envia apenas **1 evento**:

* ✅ **Novo cliente de teste cadastrado**
* Disparado quando um cadastro é feito pela página de teste (teste aberto)

***

#### 📦 Exemplo de Payload

```json
{
  "name": "Nome do cliente",
  "email": "email@exemplo.com",
  "tenantName": "Nome da empresa",
  "phone": "559999999999",
  "plano": "Plano escolhido",
  "referralId": "ID de indicação",
  "dueDate": "2026-04-10",
  "recurrence": "monthly",
  "newTenantTest": true
}
```

***

#### 🧠 Observações

* O campo `newTenantTest: true` identifica que é um cadastro de teste
* O webhook será enviado automaticamente após o cadastro
* Certifique-se que sua URL aceita requisições **POST em JSON**

***
