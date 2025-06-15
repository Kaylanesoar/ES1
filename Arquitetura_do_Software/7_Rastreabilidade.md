# Rastreabilidade  – Plataforma Digital das UBS

## Descrição da Rastreabilidade 

A rastreabilidade de requisitos é uma atividade fundamental no desenvolvimento de software, pois estabelece a ligação entre os requisitos especificados (como histórias de usuário) e os artefatos de implementação, teste e documentação.

No contexto do sistema **Plataforma Digital das UBS**, a rastreabilidade foi organizada de forma a cobrir:

* As **histórias de usuário** priorizadas no backlog do produto;
* Os **módulos e componentes** do sistema que implementam essas funcionalidades;
* Os **endpoints da API REST** responsáveis pela lógica de negócio;
* As **entidades de persistência** envolvidas no armazenamento dos dados;
* Os **testes funcionais, unitários e de integração** planejados ou executados para garantir a qualidade da implementação.

Essa matriz de rastreabilidade permite identificar, com clareza, **onde cada requisito é atendido na arquitetura do sistema**, além de servir como referência para:

* Auditorias de requisitos
* Validação e verificação funcional
* Manutenção evolutiva e corretiva
* Controle de impactos de mudanças futuras

## Tabela de Rastreabilidade

| ID  | História de Usuário                                                                             | Módulo / Componente               | API / Backend               | Persistência          | Testes Relacionados                      |
| --- | ----------------------------------------------------------------------------------------------- | --------------------------------- | --------------------------- | --------------------- | ---------------------------------------- |
| #17 | Como médico, quero visualizar a quantidade de pacientes agendados para um dia específico...     | Módulo de Agenda Médica           | `/agenda/medico`            | Tabela `agendamentos` | Teste de filtro por data e autenticação  |
| #16 | Como paciente, quero saber se o medicamento prescrito está disponível na unidade de saúde...    | Módulo de Medicamentos            | `/medicamentos/disponiveis` | Tabela `medicamentos` | Teste de consulta e estoque              |
| #15 | Como paciente, quero marcar um exame na UBS pelo aplicativo...                                  | Módulo de Agendamento de Exames   | `/exames/agendar`           | Tabela `agendamentos` | Teste de criação de exame e notificações |
| #11 | Como paciente, quero fazer login no aplicativo para acessar minhas informações médicas...       | Módulo de Autenticação            | `/auth/login`               | Usuário / Firebase    | Teste de login e geração de token JWT    |
| #10 | Como agente de saúde, quero registrar a entrega de medicamentos durante visitas domiciliares... | Módulo de Entrega de Medicamentos | `/entregas`                 | Tabela `entregas`     | Teste de criação e estoque               |

## Mapeamento nos Diagramas C4

| História de Usuário | Containers Envolvidos           | Componentes Envolvidos                     | Diagramas de Referência        |
| ------------------- | ------------------------------- | ------------------------------------------ | ------------------------------ |
| #17                 | Backend API, Banco de Dados     | AgendaController, AgendaService            | Container, Componentes, Código |
| #16                 | Backend API, Banco de Dados     | MedicamentoController, MedicamentoRepo     | Container, Componentes, Código |
| #15                 | App Mobile, Backend API, Banco  | ExameController, ExameService, Notificador | Container, Componentes, Código |
| #11                 | App Mobile, Middleware de Login | AuthController, AuthService                | Container, Componentes, Código |
| #10                 | Backend API, Banco de Dados     | EntregaController, EntregaService          | Container, Componentes, Código |

## Observações Técnicas

* Tecnologias Backend: Node.js com Express
* Frontend: Thunkable (App Mobile)
* Banco de Dados: PostgreSQL
* Autenticação: Firebase Authentication
* Notificações: Firebase Cloud Messaging (FCM) / Sistema de Notificações Push
* Testes: Unitários (Jest), Funcionais (Postman/Newman), Integração (Jest + Supertest)

## Justificativa Arquitetural

O sistema adota uma **Arquitetura em Camadas + RESTful API**, com um **Backend centralizado**, um **Frontend mobile** (Thunkable) e um **banco de dados relacional** (PostgreSQL). A **segurança** é tratada por **middleware JWT** e autenticação via **Firebase**. A rastreabilidade garante cobertura entre **requisitos**, **implementação** e **validação**.
