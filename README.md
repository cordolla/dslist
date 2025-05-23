# 🎮 DSList - Catálogo de Jogos

Este é um projeto backend desenvolvido com Java e Spring Boot, que fornece uma API REST para um catálogo de jogos. O sistema permite listar jogos, visualizar detalhes, organizar listas e reordenar os itens dessas listas.

## 📦 Tecnologias Utilizadas

- Java 17
- Spring Boot
- Spring Data JPA
- Banco de dados H2 (para desenvolvimento)
- JPA/Hibernate
- PostgreSQL (opcional para produção)
- Maven

## 📁 Estrutura do Projeto

- `entities/` – Classes de entidades mapeadas para o banco de dados
- `dto/` – Objetos de transferência de dados entre as camadas
- `repositories/` – Interfaces JPA para acesso aos dados
- `services/` – Regras de negócio e lógica de aplicação
- `controllers/` – Endpoints REST
- `projections/` – Interfaces para consultas SQL customizadas

## 🚀 Funcionalidades

- ✅ Listar todos os jogos com informações resumidas
- ✅ Buscar jogo por ID (detalhes completos)
- ✅ Listar todas as listas de jogos
- ✅ Listar jogos de uma lista específica
- ✅ Mover posição de jogos dentro de uma lista

## 📌 Endpoints

### 🔹 `/games`
- `GET /games` – Lista todos os jogos (resumido)
- `GET /games/{id}` – Retorna os detalhes completos de um jogo

### 🔹 `/lists`
- `GET /lists` – Lista todas as listas de jogos
- `GET /lists/{listId}/games` – Retorna os jogos de uma lista
- `POST /lists/{listId}/replacement` – Altera a ordem dos jogos na lista

### 🔄 Exemplo de JSON para `replacement`:

```json
{
  "sourceIndex": 1,
  "destinationIndex": 3
}
