# api-controla-carteira
Uma API desenvolvida no bootcamp da DIO sobre Spring que tem o intuito de ajudar seus usuarios a controlar os gastos e gerar insights sobre sua situação financeira

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

