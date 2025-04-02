<h1 align="center">
  TODO List
</h1>

<p align="center">
 <img src="https://img.shields.io/static/v1?label=Tipo&message=Desafio&color=8257E5&labelColor=000000" alt="Desafio" />
</p>

API para gerenciar tarefas (CRUD) que faz parte [desse desafio](https://github.com/simplify-liferay/desafio-junior-backend-simplify) para pessoas desenvolvedoras backend júnior, que se candidatam para a Simplify.

O projeto foi elaborado usando como Base [esse vídeo](https://youtu.be/IjProDV001o) do canal Giuliana Bezerra.

## Tecnologias

- [Spring Boot](https://spring.io/projects/spring-boot)
- [Spring MVC](https://docs.spring.io/spring-framework/reference/web/webmvc.html)
- [Spring Data JPA](https://spring.io/projects/spring-data-jpa)
- [OpenAPI 3 Library for spring-boot(Swagger)](https://springdoc.org/)
- [Mysql](https://dev.mysql.com/downloads/)

## Práticas adotadas

- API REST
- Consultas com Spring Data JPA
- Injeção de Dependências
- Tratamento de respostas de erro
- Geração automática do Swagger com a OpenAPI 3

## Como Executar

- Clonar repositório git
- Construir o projeto:
```
$ ./mvnw clean package
```
- Executar a aplicação:
```
$ java -jar target/todolist-0.0.1-SNAPSHOT.jar
```

A API poderá ser acessada em [localhost:8080](http://localhost:8080).
O Swagger poderá ser visualizado em [localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)

## API Endpoints

Para fazer as requisições HTTP abaixo, foi utilizado a ferramenta [Postman](https://www.postman.com/downloads/):

- Criar Tarefa
```
Método: POST, url: http://localhost:8080/todos
body:
{
    "nome": "Todo",
    "descricao": "Desc Todo 1",
    "prioridade": 1,
    "realizado": false
}

response:
[
    {
        "id": 5,
        "nome": "Todo",
        "descricao": "Desc Todo 1",
        "realizado": false,
        "prioridade": 1
    }
]
```

- Listar Tarefas
```
Método: GET, url: http://localhost:8080/todos

response:
[
    {
        "id": 5,
        "nome": "Todo",
        "descricao": "Desc Todo 1",
        "realizado": false,
        "prioridade": 1
    }
]
```

- Atualizar Tarefa
```
Método: PUT, url: http://localhost:8080/todos
body:
{
    "id": 5,
    "nome": "Todo 1 atualizado",
    "descricao": "Desc Todo 1 atualizada",
    "realizado": true,
    "prioridade": 2
}

response:
[
    {
        "id": 5,
        "nome": "Todo 1 atualizado",
        "descricao": "Desc Todo 1 atualizada",
        "realizado": true,
        "prioridade": 2
    }
]
```

- Remover Tarefa
```
Método: DELETE, url: http://localhost:8080/todos/5

response:
[ ]
```