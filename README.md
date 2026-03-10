# ForumHub API

API REST desenvolvida com **Spring Boot** para gerenciamento de tópicos de um fórum.
O projeto implementa autenticação com **JWT**, persistência com **MySQL** e controle de versão do banco com **Flyway**.

## Tecnologias utilizadas

* Java
* Spring Boot
* Spring Security
* JWT (JSON Web Token)
* Spring Data JPA
* MySQL
* Flyway
* Maven
* Lombok

---

# Configuração do ambiente

##  Clonar o repositório

```
git clone https://github.com/seu-usuario/forumhub2.git
```

```
cd forumhub2
```

---

##  Criar o banco de dados

No MySQL:

```sql
CREATE DATABASE forumhub2;
```

---

## Configurar `application.properties`

Localização:

```
src/main/resources/application.properties
```

Exemplo:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/forumhub
spring.datasource.username=SEU_USUARIO
spring.datasource.password=SUA_SENHA

spring.jpa.hibernate.ddl-auto=none
spring.jpa.show-sql=true

spring.flyway.enabled=true

jwt.secret=12345678912345678912345678912345
jwt.expiration=86400000
```

---

##  Rodar o projeto

Pelo terminal:

```
mvn spring-boot:run
```

Ou execute a classe:

```
ForumhubApplication.java
```

A API ficará disponível em:

```
http://localhost:8080
```

---

#  Endpoints da API

## Criar tópico

### POST

```
/topicos
```

Body:

```json
{
  "titulo": "Dúvida sobre Spring",
  "mensagem": "Como funciona JWT?",
  "curso": "Spring Boot"
}
```

---

## Listar tópicos

### GET

```
/topicos
```

---

## Buscar tópico por id

### GET

```
/topicos/{id}
```

---

## Atualizar tópico

### PUT

```
/topicos/{id}
```

Body:

```json
{
  "titulo": "Título atualizado",
  "mensagem": "Mensagem atualizada",
  "curso": "Spring Boot"
}
```

---

## Deletar tópico

### DELETE

```
/topicos/{id}
```

---

# Testes

Os endpoints podem ser testados utilizando:

* Postman
* Insomnia
* curl

Para endpoints protegidos, utilize o token JWT:

```
Authorization: Bearer SEU_TOKEN
```

---

# Autor

Projeto desenvolvido como parte de um desafio de API REST utilizando Spring Boot.

---
