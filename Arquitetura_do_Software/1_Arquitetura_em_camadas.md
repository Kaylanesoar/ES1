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

## Justificativa Arquitetural
1. Modularidade: Cada camada possui responsabilidades separadas, o que facilita testes e manutenções futuras.

2. Escalabilidade: Pode-se escalar o frontend, o backend ou a base de dados separadamente.

3. Segurança: A camada de aplicação faz o controle de acesso e autenticação por meio de middleware e tokens.

4. Reutilização: Serviços e regras podem ser reaproveitados em múltiplas rotas e interfaces.

   ![esquema](https://s5.aconvert.com/convert/p3r68-cdx67/prm5f-mraj6-001.png)

## Resumo em camadas
# Arquitetura do Sistema

```mermaid
graph TD
    A[Apresentação] -->|Thunkable / React| B[Aplicação / API]
    B -->|Express / Spring Boot| C[Domínio]
    C -->|Serviços de Regras| D[Persistência]
    D -->|PostgreSQL + ORM| E[Banco de Dados]

    C --> F[Sistemas Externos]
    F -->|Autenticação| G[Serviço de Autenticação]
    F -->|Notificação| H[Serviço de Notificação]
    F -->|APIs de Saúde| I[Integração com APIs de Saúde]

