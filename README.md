
# API de Autenticação com Spring Boot + JWT

Projeto backend com autenticação JWT, controle de usuários (ADMIN/USER)

---

## Funcionalidades

- Registro de usuários com role (ADMIN ou USER)
- Login com retorno de token JWT
- Acesso seguro com base no tipo de usuário (token de segurança)
- Cadastro e listagem
- Gerenciamento de usuários (listar, editar, deletar)


---

## Tecnologias

- Java 17
- Spring Boot
- Spring Security
- JWT
- H2 database
- Maven
- JPA

---

## Como rodar o projeto

1. **Clone o projeto**

```bash
git clone https://github.com/GusOli/prova-poo-gustavo.git
cd seu-projeto
```

2. **Configure o banco de dados** no arquivo `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/seu_banco
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.jpa.hibernate.ddl-auto=update
```

3. **Execute a aplicação**

Via terminal:

```bash
./mvnw spring-boot:run
```

Ou pela sua IDE (IntelliJ, Eclipse, VSCode).

---

## Endpoints principais

### Autenticação

| Método | Rota             | Descrição         |
|--------|------------------|-------------------|
| POST   | `/auth/register` | Cadastro de usuário |
| POST   | `/auth/login`    | Login e retorno do token |

### Usuários

| Método | Rota              | Descrição                |
|--------|-------------------|--------------------------|
| GET    | `/user`           | Listar todos os usuários (ADMIN) |
| GET    | `/user/{id}`      | Buscar usuário por ID    |
| DELETE | `/user/{id}`      | Deletar usuário (ADMIN)  |
| PUT    | `/user/edit`      | Atualizar próprio perfil |
| PUT    | `/user/{id}`      | Atualizar qualquer usuário (ADMIN) |

## Exemplo de autenticação com token JWT

1. Faça login em `/auth/login`
2. Copie o token recebido
3. Envie nas requisições protegidas no header:

```
Authorization: Bearer SEU_TOKEN_AQUI
```

---

## Exemplo de JSON para registro
``json
{
  "login": "admin@email.com",
  "password": "123456",
  "role": "ADMIN"
}
```

