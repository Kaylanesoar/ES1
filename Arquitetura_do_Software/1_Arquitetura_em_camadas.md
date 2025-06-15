#  Arquitetura em Camadas – Sistema SUS Digital
##  Visão Geral

O sistema é dividido em quatro camadas principais:

1. **Camada de Apresentação**
2. **Camada de Aplicação**
3. **Camada de Domínio**
4. **Camada de Persistência**

Além disso, há **integrações com serviços externos**, como Firebase e Google Maps API.

##  1. Camada de Apresentação (Frontend)

- **Responsabilidade**: Interação com os usuários finais (Paciente, Médico, Agente de Saúde).
- **Tecnologia**: React.js, HTML5
- **Principais Funcionalidades**:
  - Interfaces de login, agendamento, consulta de medicamentos e campanhas
  - Requisições REST para a API
  - Exibição de mensagens, formulários e notificações

##  2. Camada de Aplicação (API / Controladores)
- **Responsabilidade**: Intermediação entre a interface do usuário e a lógica de negócio.
- **Tecnologia**: Node.js (Express) ou Spring Boot
- **Principais Funcionalidades**:
  - Receber e validar requisições HTTP
  - Acionar serviços da camada de domínio
  - Gerar respostas estruturadas (JSON)

##  3. Camada de Domínio (Lógica de Negócio)

- **Responsabilidade**: Processamento das **regras de negócio**.
- **Tecnologia**: Serviços/Classes de domínio (Service Layer)
- **Principais Funcionalidades**:
  - Validação de agendamentos e limites por especialidade
  - Processamento de estoques e campanhas de saúde
  - Geração de relatórios analíticos
  - Integração com APIs externas como Google Maps e Firebase
##  4. Camada de Persistência (Banco de Dados)

- **Responsabilidade**: Armazenamento e recuperação de dados do sistema.
- **Tecnologia**: PostgreSQL , Sequelize (Node) ou JPA/Hibernate (Java)
- **Principais Funcionalidades**:
  - CRUD completo de entidades como usuários, consultas, medicamentos, campanhas e prontuários
  - Mapeamento objeto-relacional (ORM)
  - Conexão com o banco por repositórios especializados



##  Integrações Externas

| Serviço Externo | Função |
|-----------------|--------|
| **Firebase Auth** | Autenticação de usuários |
| **Google Maps API** | Localização de UBSs e rotas |
| **Firebase Cloud Messaging (opcional)** | Envio de notificações push |

