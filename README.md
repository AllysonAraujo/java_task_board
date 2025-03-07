# Board de Tarefas em Java

Este projeto é um **Board de Tarefas** desenvolvido em **Java**, com o objetivo de proporcionar uma aplicação simples e eficiente para gerenciamento de tarefas. O sistema permite criar, editar, remover e listar tarefas, além de gerenciar o estado das mesmas (ex: "pendente", "em andamento", "concluída").

## Sumário

- [Visão Geral](#visão-geral)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Etapas do Desenvolvimento](#etapas-do-desenvolvimento)
  - [Planejamento e Estruturação](#planejamento-e-estruturação)
  - [Gerenciamento de Dados](#gerenciamento-de-dados)
  - [Integração entre Camadas](#integração-entre-camadas)

## Visão Geral

O **Board de Tarefas** é uma aplicação em Java com o objetivo de gerenciar as tarefas de um usuário. Ele possibilita a criação de tarefas, atribuição de status, e a exibição de tarefas organizadas. O projeto foi desenvolvido de maneira modular e com boas práticas de programação para garantir a qualidade e a escalabilidade do código.

## Tecnologias Utilizadas

- **Java**: Linguagem de programação principal utilizada para desenvolver o sistema.
- **Liquibase**: Framework para controle de versões do banco de dados e migrações.
- **Gradle**: Ferramenta de automação de build e gerenciamento de dependências.

## Estrutura do Projeto

A estrutura do projeto foi organizada de maneira a manter a separação de responsabilidades e garantir a escalabilidade.

- **`dto/`**: Contém os objetos de transferência de dados (DTOs) que são utilizados para transportar dados entre as camadas.

- **`exception/`**: Contém exceções personalizadas que são lançadas em situações específicas de erro.

- **`persistence/`**: Camada de persistência que lida com a comunicação com o banco de dados.

  - **`migration/`**: Contém a estratégia de migração de banco de dados.

- **`service/`**: Contém a lógica de negócios do sistema.

- **`ui/`**: Contém a interface do usuário, onde as interações com o usuário acontecem.

## Etapas do Desenvolvimento

### Planejamento e Estruturação

Antes de começar a codificação, foram realizadas as seguintes etapas de planejamento:

1. **Definição dos Requisitos**: Listamos as funcionalidades essenciais, como:
   - Criação de tarefas.
   - Atribuição de status às tarefas.
   - Edição e exclusão de tarefas.
   - Visualização de todas as tarefas, com possibilidade de filtragem por status.
   
2. **Desenho da Arquitetura**: A arquitetura foi planejada para seguir uma estrutura em camadas:
   - **Camada de Apresentação (UI)**: Responsável pela interação com o usuário.
   - **Camada de Lógica de Negócio (Service)**: Contém a lógica de processamento.
   - **Camada de Persistência (Persistence)**: Realiza a comunicação com o banco de dados.
   
3. **Escolha das Tecnologias**: Optamos por Java como a linguagem principal e Liquibase para gerenciar as migrações de banco de dados.

### Gerenciamento de Dados

- Utilizamos **Liquibase** para o gerenciamento e versionamento do banco de dados. Liquibase é uma ferramenta que permite gerenciar alterações no banco de dados de forma controlada, garantindo que as modificações sejam aplicadas corretamente ao longo do tempo.
  
- O Liquibase facilita a migração entre diferentes versões do banco de dados. As migrações são descritas em arquivos XML ou YAML, permitindo que qualquer alteração no esquema do banco de dados seja aplicada de maneira automatizada.

### Integração entre Camadas

- A camada **Service** interage com a camada **DAO** para realizar operações de leitura e gravação dos dados.
- A camada **UI** envia as requisições à camada de Service, que, por sua vez, comunica-se com o DAO para manipular os dados.

Essa separação em camadas garante uma maior flexibilidade e facilita a manutenção do sistema no futuro.