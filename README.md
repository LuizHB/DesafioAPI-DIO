# DIO - Trilha .NET - API e Entity Framework

## Desafio de projeto
Você precisa construir um sistema gerenciador de tarefas, onde você poderá cadastrar uma lista de tarefas que permitirá organizar melhor a sua rotina.

Essa lista de tarefas precisa ter um CRUD, ou seja, deverá permitir a você obter os registros, criar, salvar e deletar esses registros.

A sua aplicação deverá ser do tipo Web API ou MVC, fique a vontade para implementar a solução que achar mais adequado.

A sua classe principal, a classe de tarefa, deve ser a seguinte:

![Diagrama da classe Tarefa](diagrama.png)

## Métodos esperados
É esperado que você crie o seus métodos conforme a seguir:

**Swagger**

![Métodos Swagger](swagger.png)

**Endpoints**


| Verbo  | Endpoint                | Parâmetro | Body          |
|--------|-------------------------|-----------|---------------|
| GET    | /Tarefa/{id}            | id        | N/A           |
| PUT    | /Tarefa/{id}            | id        | Schema Tarefa |
| DELETE | /Tarefa/{id}            | id        | N/A           |
| GET    | /Tarefa/ObterTodos      | N/A       | N/A           |
| GET    | /Tarefa/ObterPorTitulo  | titulo    | N/A           |
| GET    | /Tarefa/ObterPorData    | data      | N/A           |
| GET    | /Tarefa/ObterPorStatus  | status    | N/A           |
| POST   | /Tarefa                 | N/A       | Schema Tarefa |

Esse é o schema (model) de Tarefa, utilizado para passar para os métodos que exigirem

```json
{
  "id": 0,
  "titulo": "string",
  "descricao": "string",
  "data": "2022-06-08T01:31:07.056Z",
  "status": "Pendente"
}
```

## Resultado

* Itens deletados: 1, 2, 3 e 5
* Busca por títulos: "string", "string atualizado", "teste", "testefinal"
* Busca por status: "Pendente", "Finalizado"
* Busca por data: formato MMddYYYY utilizado
* Busca por todos:

```json
  {
    "id": 4,
    "titulo": "string atualizado",
    "descricao": "string atualizado",
    "data": "2022-10-20T06:18:06.163",
    "status": "Finalizado"
  },
  {
    "id": 6,
    "titulo": "string",
    "descricao": "string",
    "data": "2022-10-20T06:02:02.129",
    "status": "Finalizado"
  },
  {
    "id": 7,
    "titulo": "teste",
    "descricao": "teste1",
    "data": "2022-10-20T06:07:33.045",
    "status": "Finalizado"
  },
  {
    "id": 8,
    "titulo": "testefinal",
    "descricao": "tipo",
    "data": "2022-10-20T06:07:33.045",
    "status": "Pendente"
  }
```
