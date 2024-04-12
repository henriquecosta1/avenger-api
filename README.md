# Avengers API

Desenvolvimento de uma API utilizando SpringBoot + Kotlin com o intuito de cadastro de Vingadores.

## Tecnologias / Frameworks / IDE

- Intellij
- SpringBoot 2.4.4
- Maven
- Kotlin
- SpringData JPA
- PostgreSQL
- Flyway
- Java 8
- Heroku

  ## Contratos API

- Recurso `avenger`
- GET - 200 OK
- GET {id}/detail - 200 OK ou 404 Not Found
- POST - 201 Created ou 400 Bad Request
- PUT {id} - 202 Accepted ou 404 Not Found
- DELETE {id} - 202 Accepted ou 404 Not Found

```json
{
  "nick": "spider-man",
  "person": "Peter Parker",
  "description": "sobre poderes",
  "history": "a história"
}
```

## Design Arquitetural

- Camada de Aplicação (controllers, configs, request e response dtos, bean validations)
- Camada de Domínio (modelo avenger, interface repositório, serviço)
- Camada de Infraestrutura (jpa repository, entidade avenger, proxy implementa interface repositorio e utiliza o jpa repositorio para comunicação com banco de dados)
- Testes

### Profiles

- application.yaml
- application-dev.yaml
- application-heroku.yaml

### Script / Comandos

- `docker-compose -f backend-services.yaml up -d` (deploy) / `docker-compose -f backend-services.yaml down` (undeploy) 

- Start API 
```sh
./mvnw spring-boot:run -Dspring-boot.run.profiles=dev -Dspring-boot.run.jvmArguments="-Xmx256m -Xms128m" -Dspring-boot.run.arguments="'--DB_USER=dio.avenger' '--DB_PASSWORD=dio.avenger' '--DB_NAME=avengers'"
``` 
