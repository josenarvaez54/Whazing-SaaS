# Api

A API do **KanbanPro** permite integrar seu sistema com o funil de atendimento (Kanban), possibilitando listar, criar, mover e gerenciar cards automaticamente.

Segue arquivo do postman para baixar

{% file src="../../.gitbook/assets/KanbanPro_API_Postman.json" %}

***

### 🔐 Autenticação

Todas as requisições utilizam **Bearer Token**:

```
Authorization: Bearer SEU_TOKEN
```

***

### 🌐 URL Base

```
{{BASE_URL}}/v1/api/external/{{API_ID}}/kanbanpro
```

#### Variáveis:

| Variável  | Descrição                 |
| --------- | ------------------------- |
| BASE\_URL | URL do seu sistema        |
| API\_ID   | ID da configuração da API |
| TOKEN     | Token de autenticação     |

***

## 📋 Listagens

### 🔹 Listar Boards

**GET**

```
/boards
```

Retorna todos os boards ativos.

#### Resposta:

```json
{
  "boards": [
    {
      "id": 1,
      "name": "Vendas",
      "description": "Funil comercial",
      "color": "#FF0000",
      "icon": "📊",
      "sortOrder": 1
    }
  ]
}
```

***

### 🔹 Listar Colunas de um Board

**GET**

```
/boards/{boardId}/columns
```

#### Exemplo:

```
/boards/1/columns
```

Retorna as etapas (colunas) do board.

***

### 🔹 Listar Cards de um Board

**GET**

```
/boards/{boardId}/cards
```

#### Filtros opcionais:

| Parâmetro       | Descrição                       |
| --------------- | ------------------------------- |
| columnId        | Filtrar por coluna              |
| priority        | none, low, medium, high, urgent |
| contactId       | Filtrar por contato             |
| search          | Busca por título/descrição      |
| includeArchived | true para incluir arquivados    |

#### Exemplo:

```
/boards/1/cards?columnId=3
```

***

### 🔹 Detalhe de um Card

**GET**

```
/cards/{cardId}
```

Retorna todas as informações do card:

* Board
* Coluna
* Contato
* Responsável
* Histórico

***

### 🔹 Cards de um Contato

**GET**

```
/contact/{contactId}/cards
```

Retorna todos os cards do contato em todos os boards.

***

## ⚡ Criar e Manipular Cards

### 🔹 Criar ou Atualizar Card

**POST**

```
/card
```

#### Body:

```json
{
  "boardId": 1,
  "columnId": 2,
  "contactId": 10,
  "action": "create_or_move",
  "title": "Lead qualificado — João",
  "priority": "medium",
  "note": "Entrou pelo site"
}
```

***

### 🎯 Ações disponíveis

| Action             | Comportamento              |
| ------------------ | -------------------------- |
| create\_or\_move   | Cria ou move o card        |
| create\_or\_update | Cria ou atualiza sem mover |
| create\_only       | Sempre cria novo card      |
| move\_only         | Apenas move se existir     |

***

### 🔹 Casos de uso

#### ✔️ Avançar no funil

```json
{
  "boardId": 1,
  "columnId": 5,
  "contactId": 10,
  "action": "create_or_move",
  "priority": "high"
}
```

***

#### ✔️ Atualizar sem mover

```json
{
  "boardId": 1,
  "columnId": 2,
  "contactId": 10,
  "action": "create_or_update",
  "priority": "urgent"
}
```

***

#### ✔️ Criar múltiplos cards

```json
{
  "boardId": 1,
  "columnId": 2,
  "contactId": 10,
  "action": "create_only"
}
```

***

## ✏️ Atualizar Card

### 🔹 Atualizar dados

**PUT**

```
/card/{cardId}
```

#### Exemplo:

```json
{
  "title": "Lead prioridade alta",
  "priority": "high"
}
```

***

### 🔹 Mover Card

```json
{
  "columnId": 6,
  "note": "Movido para fechado"
}
```

***

### 🔹 Definir responsável e prazo

```json
{
  "assigneeId": 3,
  "dueDate": "2026-05-30"
}
```

***

## 🗑️ Arquivar ou Deletar Card

### 🔹 Arquivar (soft delete)

**DELETE**

```
/card/{cardId}
```

O card pode ser restaurado depois.

***

### ⚠️ Deletar permanentemente

**DELETE**

```
/card/{cardId}?permanent=true
```

Remove definitivamente o card.

***

## 🧠 Observações Importantes

* Toda ação via API gera histórico com prefixo **\[API]**
* Cards são vinculados a contatos
* Um contato pode ter múltiplos cards dependendo da ação usada
* Ideal para automações de:
  * CRM
  * Funil de vendas
  * Atendimento automático
  * Integrações externas

***

## 🚀 Exemplo Completo

```bash
curl -X POST "{{BASE_URL}}/v1/api/external/{{API_ID}}/kanbanpro/card" \
-H "Authorization: Bearer {{TOKEN}}" \
-H "Content-Type: application/json" \
-d '{
  "boardId": 1,
  "columnId": 2,
  "contactId": 10,
  "action": "create_or_move",
  "title": "Novo lead",
  "priority": "medium"
}'
```
