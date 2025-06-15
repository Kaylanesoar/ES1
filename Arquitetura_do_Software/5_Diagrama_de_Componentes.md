# Diagrama de Componentes - Sistema UBS Digital

## Visão Geral da Arquitetura

O sistema UBS Digital é composto por múltiplos containers que interagem entre si para permitir que pacientes e funcionários da UBS realizem operações como agendamentos, controle de entregas, campanhas de saúde e notificações.

A arquitetura segue uma separação em camadas:

- Frontend (Usuário Web e Mobile)
- Backend API (Controladores REST, Serviços de Negócio)
- Adapters/Infraestrutura (Autenticação, Notificação, Repositório)
- Banco de Dados
- Serviços Externos (Firebase Authentication, Firebase Cloud Messaging)

## Containers e Suas Funções

### 1. Usuário Web (Frontend - React.js)

- Interface acessível via navegador.
- Permite que os funcionários da UBS gerenciem agendamentos, entregas, campanhas e notificações.
- Comunicação com a API Backend via chamadas REST.

### 2. Usuário Mobile (Aplicativo - Thunkable)

- Aplicativo móvel utilizado pelos pacientes.
- Permite agendar consultas, receber notificações de campanhas e registrar retiradas de medicamentos.
- Comunicação com a API Backend via chamadas REST.

## Backend API (Camada de Aplicação)

### 3. ControleDeAgendamento (Rest Controller)

- Responsável por receber requisições de agendamento.
- Valida os dados e encaminha para o **Serviço de Agendamento**.

### 4. ControleDeCampanha (Rest Controller)

- Recebe requisições para criação, edição e consulta de campanhas de saúde.
- Aciona o **Serviço de Campanha**.

### 5. ControleDeEntrega (Rest Controller)

- Processa requisições relacionadas à entrega de medicamentos.
- Encaminha as requisições para o **Serviço de Entregas**.

## Serviços (Camada de Negócio)

### 6. Serviço de Agendamento (Business Service)

- Implementa as regras de negócio para agendamentos.
- Garante integridade de horários e disponibilidade.
- Realiza comunicação com o **Adaptador de Repositório** para operações de banco de dados.

### 7. Serviço de Campanha (Business Service)

- Gerencia a criação e manutenção de campanhas de saúde.
- Realiza validações e aciona o **Adaptador de Notificação** para envio de mensagens aos pacientes.

### 8. Serviço de Entregas (Business Service)

- Controla todo o fluxo de entregas de medicamentos.
- Inclui registro, atualização de status e verificação de regras de entrega.


## Adapters / Infraestrutura

### 9. Adaptador de Autenticação (OAuth Client)

- Responsável por validar a identidade dos usuários.
- Integra-se ao serviço externo de autenticação (**Firebase Authentication**).
- Garante que apenas usuários autenticados possam acessar as funcionalidades da API.

### 10. Adaptador de Notificação (HTTP Client)

- Faz a ponte entre os serviços de negócio e o serviço externo de notificações (**Firebase Cloud Messaging - FCM**).
- Responsável por disparar notificações push aos dispositivos dos pacientes.

### 11. Adaptador de Repositório (ORM - Sequelize/Node.js)

- Realiza operações de banco de dados: **Criação**, **Leitura**, **Atualização** e **Exclusão de dados** (CRUD).
- Faz a comunicação entre os serviços da aplicação e o **Banco de Dados PostgreSQL**.

## Serviços Externos

### 12. Serviço de Autenticação (Firebase Authentication)

- Serviço externo de autenticação.
- Realiza o controle de login, geração de tokens e validação de usuários.

### 13. Serviço de Notificação (Firebase Cloud Messaging - FCM)

- Serviço externo de envio de notificações push.
- Recebe requisições do **Adaptador de Notificação** e entrega mensagens aos aplicativos dos pacientes.

## Persistência de Dados

### 14. Banco de Dados UBS (PostgreSQL)

- Container responsável pelo armazenamento persistente de dados.
- Armazena informações como:

  - Pacientes
  - Agendamentos
  - Entregas de medicamentos
  - Campanhas de saúde
  - Histórico de notificações

- As operações de banco de dados (CRUD) são feitas via o **Adaptador de Repositório**.


## Fluxo de Comunicação Entre os Componentes

- **Usuários Web e Mobile** enviam requisições REST para os **Controllers** da Backend API.
- Os **Controllers** repassam as requisições para os **Serviços de Negócio**, que contêm a lógica da aplicação.
- Os **Serviços** acessam o **Banco de Dados** via o **Adaptador de Repositório**.
- Para autenticação, os **Adaptadores de Autenticação** validam tokens junto ao **Firebase Authentication**.
- Para notificações, os **Adaptadores de Notificação** enviam mensagens para o **Firebase Cloud Messaging**.



  ![diagrma de componentes](https://s5.aconvert.com/convert/p3r68-cdx67/dv98l-432v7-001.png)

