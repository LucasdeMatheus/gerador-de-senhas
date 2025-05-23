# gerador de senhas
O projeto é criar um geranciador simples e completo de senhas como uma fila.

## Estrutura do Projeto 🗂️
```
src/
└── main/
    └── java/
        └── com.myproject.queueSystem/
            ├── config/
            │   └── ConfigCors.java
            │
            ├── controller/
            │   └── QueueController.java
            │
            ├── domain
            │   ├── queue/
            │   │   └── Queue.java
            │   │   ├── QueueRepository.java
            │   │   ├── STATUS.java
            │   │   └── TYPE.java
            │   │       └── dto/
            │   │           └── QueueDTO.java
            │   ├── service/
            │       └── QueueService.java

```
## 1 🗂️ Entidades do Sistemas

### 👤 Queue
```json
{
  "id": "long",
  "code": "string (ex: A001, P002)",
  "type": "NORMAL | PREFERENCIAL",
  "status": "PENDING | CALLED | CANCELLED",
  "timestamp": "datetime"
}
```
## 2 🃏 Funcionalidades

### 2.1 gerar uma senha
- **Endpoint**: `POST /queue`
- **Corpo da requisição (JSON)**
```json
{
  "type": "NORMAL" // ou PREFERENCIAL
}
```
- **Retorno**:
 ```json
{
"queue": "N001" // NORMAL
"queue": "P001" // PREFERENCIAL
 }
```
### 2.2 Chamar próxima senha
- **Endpoint**: `POST /queue/call`
- **Irá chamar a ultima senha e remover-la da fila**
  
### 2.3 cancelar senha
- **Endpoint**: `POST /queue/cancel/:id`
- **Irá cancelar uma senha recebida no endpoint**

### 2.4 Listar senhas em fila
- **Endpoint**: `GET /queue/list`
- **Retorno**:
 ```json
{
"queues":[
    "queue": "A001",
    "queue": "A002"
    ...
    ]
}
```
### 2.5 Resetar senhas do dia
- **Endpoint**: `POST /queue/reset`



## 🛠️ Ferramentas
- Intellij
- Java/SpringBoot
- Mysql
- Insomnia(postman)
