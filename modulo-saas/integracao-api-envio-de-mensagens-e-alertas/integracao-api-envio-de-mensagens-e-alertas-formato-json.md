# Integração API — Envio de Mensagens e Alertas (Formato JSON)

O sistema permite integrar o envio automático de mensagens via API utilizando o formato **JSON**.

Esse recurso é ideal para integração com:

* APIs de botões interativos
* API Oficial do WhatsApp (Templates Meta)

***

## Configurações Disponíveis

### Habilitar envio WhatsApp solicitar teste

Quando ativado, o sistema envia automaticamente uma mensagem de boas-vindas após o cadastro do teste.

Exemplos de uso:

* Enviar acesso do sistema
* Enviar botão de acesso
* Enviar template oficial
* Enviar link do painel
* Enviar dados de login

***

### Habilitar envio WhatsApp aviso fatura em aberto

Quando ativado, o sistema envia alertas automáticos de cobrança:

* 7 dias antes do vencimento
* 3 dias antes
* 1 dia antes
* No dia do vencimento

Pode ser utilizado com:

* Link botões

***

### Habilitar envio WhatsApp confirmando pagamento

Quando ativado, o sistema envia automaticamente uma mensagem após a confirmação do pagamento da fatura.

Exemplos:

* Confirmação do pagamento
* Liberação do sistema
* Agradecimento
* Renovação automática

***

## Ativar envio no formato JSON

Ative a opção:

### Habilitar envio no formato JSON

Com essa opção ativada, os dados serão enviados para sua API exatamente no formato JSON configurado.

Esse modo é recomendado para:

* APIs com botões
* API Oficial do WhatsApp
* Templates Meta

***

## URL da API

Informe a URL correta do endpoint da integração.

### Exemplos

#### API Plus

```
https://urldaapi/apiplus
```

#### API Oficial

```
https://urldaapi/apioficial
```

***

## Uso de Variáveis

O sistema suporta variáveis dinâmicas utilizando o formato:

```
{{variavel}}
```

As variáveis serão substituídas automaticamente pelas informações reais no momento do envio da mensagem.

***

## Variáveis disponíveis — Solicitação de Teste / Boas-vindas

| Variável              | Descrição           |
| --------------------- | ------------------- |
| `{{number}}`          | Número do WhatsApp  |
| `{{senha}}`           | Senha de acesso     |
| `{{email}}`           | E-mail cadastrado   |
| `{{nomeresponsavel}}` | Nome do responsável |
| `{{nomeempresa}}`     | Nome da empresa     |

***

## Variáveis disponíveis — Cobrança e Pagamento

| Variável          | Descrição          |
| ----------------- | ------------------ |
| `{{nomeempresa}}` | Nome da empresa    |
| `{{value}}`       | Valor da cobrança  |
| `{{dueDate}}`     | Data de vencimento |
| `{{plan}}`        | Nome do plano      |
| `{{number}}`      | Número do WhatsApp |

***

## Exemplo JSON — Mensagem de Boas-vindas com Botão

```json
{
    "number": "{{number}}",
    "contents": {
        "type": "cta_url",
        "header": {
            "type": "text",
            "text": "Olá {{nomeresponsavel}}"
        },
        "body": {
            "text": "Seu cadastro de teste da empresa {{nomeempresa}} foi concluído com sucesso.\n\nE-mail: {{email}}\nSenha: {{senha}}"
        },
        "footer": {
            "text": "Bom teste"
        },
        "action": {
            "name": "cta_url",
            "parameters": {
                "display_text": "Acessar teste",
                "url": "https://teste.whazing.com.br"
            }
        }
    }
}
```

***

## Exemplo JSON — Aviso de Fatura em Aberto

```json
{
    "number": "{{number}}",
    "contents": {
        "type": "cta_url",
        "header": {
            "type": "text",
            "text": "Aviso de vencimento"
        },
        "body": {
            "text": "Olá.\n\nIdentificamos uma fatura em aberto da empresa {{nomeempresa}}.\n\nPlano: {{plan}}\nValor: R$ {{value}}\nVencimento: {{dueDate}}"
        },
        "footer": {
            "text": "Evite bloqueios realizando o pagamento."
        },
        "action": {
            "name": "cta_url",
            "parameters": {
                "display_text": "Pagar agora",
                "url": "https://teste.whazing.com.br/#/financeiro"
            }
        }
    }
}
```

***

## Exemplo JSON — Template Oficial WhatsApp (Meta)

Também é possível utilizar templates oficiais aprovados pela Meta.

### Exemplo — Template Confirmação de Pagamento

```json
{
  "number": "{{number}}",
  "contents": {
    "name": "z_pago",
    "components": [
      {
        "type": "body",
        "parameters": [
          {
            "type": "text",
            "text": "{{plan}}"
          },
          {
            "type": "text",
            "text": "{{nomeempresa}}"
          },
          {
            "type": "text",
            "text": "{{value}}"
          }
        ]
      }
    ],
    "language": {
      "code": "pt_BR"
    }
  }
}
```

***

## Exemplo JSON — Template de Cobrança

```json
{
  "number": "{{number}}",
  "contents": {
    "name": "fatura_aberta",
    "components": [
      {
        "type": "body",
        "parameters": [
          {
            "type": "text",
            "text": "{{nomeempresa}}"
          },
          {
            "type": "text",
            "text": "{{value}}"
          },
          {
            "type": "text",
            "text": "{{dueDate}}"
          }
        ]
      }
    ],
    "language": {
      "code": "pt_BR"
    }
  }
}
```

***

## Informações Importantes

* O JSON deve ser válido.
* As variáveis devem ser escritas exatamente no formato `{{variavel}}`.
* Compatível com APIs próprias e integrações externas.
* Pode ser utilizado para mensagens simples, botões ou templates oficiais do WhatsApp.
* Os templates utilizados na API Oficial precisam estar previamente aprovados na Meta.
* É possível personalizar totalmente o JSON conforme a estrutura aceita pela API.
