# api-controla-carteira
Uma API desenvolvida no bootcamp da DIO sobre Spring que tem o intuito de ajudar seus usuarios a controlar os gastos e gerar insights sobre sua situação financeira

## Requisitos Funcionais

1- Adicionar Saída e Entrada de dinheiro
2- Listrar todos os registros ordenadamente
3- Classificar as saídas por tipos (ex. alimentação, transporte)
4- Permitir filtro por tipo de entrada/saída
5- Permitir filtro por periodo
6- Mostrar estatisticas gerais de gastos

## ## Requisitos Não-Funcionais

1- Autenticação por usuário (JWT) – para multiusuário
2- Deploy com PostgreSQL no Railway
3- Documentação com Swagger
4- Validação com Bean Validation (ex: valor não pode ser negativo)

## DIAGRAMA DE CLASSES

```mermaid
classDiagram
  class User {
    +Long id
    +String name
    +String email
    +String password
    +String profilePicture
  }

  class Income {
    +Long id
    +String title
    +BigDecimal value
    +String description
    +LocalDate date
  }

  class Outcome {
    +Long id
    +String title
    +BigDecimal value
    +LocalDate date
  }

  class OutcomeType {
    +Long id
    +String name
  }

  User "1" --> "0..*" Income : has
  User "1" --> "0..*" Outcome : has
  Outcome "1" --> "1" OutcomeType : classified as

