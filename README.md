# 📦 DSCommerce - API REST com Spring Boot

API REST desenvolvida com Java + Spring Boot para gerenciamento de produtos, categorias, usuários e pedidos, incluindo autenticação e controle de acesso com JWT.

Este projeto foi desenvolvido como parte de um desafio prático, com foco em arquitetura em camadas, segurança e boas práticas no desenvolvimento backend.

---

## 🚀 Tecnologias utilizadas
* Java 17+;
* Spring Boot;
* Spring Data JPA;
* Spring Security;
* OAuth2 / JWT;
* Banco de dados H2;
* Maven;
* Postman (para testes da API).

---

## 📂 Estrutura do projeto

O projeto segue o padrão de arquitetura em camadas:

```
src/main/java/com/devsuperior/dscommerce
├── config         # Configurações (security, JWT, etc)
├── controllers    # Camada de API (REST controllers)
├── dto            # Data Transfer Objects
├── entities       # Entidades JPA
├── repositories   # Interfaces de acesso a dados
├── services       # Regras de negócio
└── resources      # Configurações (application.properties, import.sql)
```

## 🔐 Autenticação e autorização

A aplicação utiliza autenticação baseada em JWT (JSON Web Token).

Perfis de usuário:
* ADMIN;
* CLIENT.

Regras de acesso:
* Endpoints públicos:
  * GET /products;
  * GET /products/{id}.

* Endpoints restritos:
  * Produtos (POST, PUT, DELETE) → apenas ADMIN;
  * Pedidos → usuário autenticado;
  * Usuário só pode acessar seus próprios pedidos.

## 📌 Endpoints principais
🔓 Públicos
* GET /products → Lista todos os produtos;
* GET /products/{id} → Busca produto por ID;
* GET /categories → Lista todas as categorias.

## 🔐 Autenticação
* POST /oauth/token → Realiza login e retorna token JWT.

## 👤 Usuário
* GET /users/me → Retorna dados do usuário autenticado.

## 📦 Produtos (ADMIN)
* POST /products;
* PUT /products/{id};
* DELETE /products/{id}.

## 🛒 Pedidos
* GET /orders/{id} → Busca pedido (restrito ao dono ou ADMIN);
* POST /orders → Cria novo pedido.

## 🧪 Banco de dados H2

O projeto utiliza banco em memória H2 para facilitar testes.

Acesso ao console:

```
http://localhost:8080/h2-console
```

Configuração padrão:
1. JDBC URL: jdbc:h2:mem:testdb;
2. User: sa;
3. Password: (vazio).


## ✅ Critérios atendidos

* Endpoints públicos funcionando sem autenticação;
* Login com geração de token JWT;
* Controle de acesso por perfil (ADMIN / CLIENT);
* Proteção de rotas privadas;
* Usuário acessa apenas seus próprios pedidos;
* CRUD de produtos restrito a ADMIN;
* Endpoint /users/me funcionando;
* Endpoint de pedidos implementado;
* Listagem de categorias disponível;
* Projeto versionado com múltiplos commits.

## 👨‍💻 Autor

Desenvolvido por **Lucas Tandy do Nascimento Silva**
 https://www.linkedin.com/in/lucas-tandy/

💼 Analista de Sistemas
🎓 Pós-graduado em Engenharia de Software





