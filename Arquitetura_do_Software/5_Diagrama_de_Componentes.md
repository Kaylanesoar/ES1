# Diagrama de Componentes - Sistema UBS Digital

Representação visual que detalha a estrutura interna de um sistema de software. Ele mostra como os diferentes módulos, classes ou serviços (os "componentes") dentro de um contêiner (como um aplicativo ou uma API) estão organizados e como eles interagem entre si. No contexto do modelo c4 ele aprofunda a visão de um Diagrama de Contêineres, focando nas partes internas de um contêiner específico.



Explicação detalhada dos elementos chave do diagrama de componentes:

### 1. Interfaces Externas

As interfaces externas representam os sistemas ou usuários que interagem diretamente com a sua aplicação, mas que estão fora do seu controle direto. No seu diagrama, elas são os pontos de entrada para o sistema.

| Interface Externa | Descrição | Tecnologia |
|---|---|---|
| **Portal Web (Funcionário UBS)** | Interface do usuário acessada por funcionários da UBS. Permite gerenciar agendamentos, entregas, campanhas e notificações. | React.js |
| **UBSdigital (App Móvel)** | Aplicativo móvel utilizado por pacientes. Permite agendar consultas, receber notificações de campanhas e registrar retiradas de medicamentos. | Thunkable (No-code/Low-code) |

### 2. Componentes da Aplicação (Backend API)

Esta seção detalha os componentes internos do seu contêiner principal, o "Backend API", que é construído com Node.js e Express. Eles são responsáveis pela lógica de negócio, processamento de dados e comunicação com outros serviços.

| Componente | Descrição |
|---|---|
| **AgendamentoController** | Controlador REST que gerencia requisições de agendamento de consultas e encaminha para o Serviço de Agendamento. |
| **CampanhaController** | Controlador REST que administra as operações de campanhas e dispara notificações para os pacientes. |
| **EntregaController** | Controlador REST que processa requisições de entregas de medicamentos, integrando o sistema. |
| **Serviço de Agendamento** | Implementa as regras de negócio para criação, gerenciamento e validação de agendamentos. Interage com o Adaptador de Repositório. |
| **Serviço de Campanha** | Contém a lógica e o gerenciamento de campanhas de saúde, aplicando validações. Interage com o Adaptador de Repositório. |
| **Serviço de Entregas** | Gerencia a lógica de controle das entregas de medicamentos, incluindo regras e validações. Interage com o Adaptador de Repositório. |
| **Adaptador de Autenticação** | Valida a autenticidade dos usuários consumindo o serviço externo de autenticação (Firebase Authentication). |
| **Adaptador de Notificação (HTTP Client)** | Dispara notificações push para aplicativos móveis usando Firebase Cloud Messaging (FCM). |
| **Adaptador de Repositório (ORM Sequelize-PG)** | Faz a ponte entre os serviços de negócio e o Banco de Dados. Responsável pela leitura e escrita de dados. |

### 3. Serviços e Recursos Externos

Esses são sistemas de terceiros ou recursos de infraestrutura que sua aplicação utiliza, mas que são gerenciados externamente.

| Serviço/Recurso Externo | Descrição | Tecnologia |
|---|---|---|
| **Serviço de Autenticação** | Sistema externo utilizado para autenticação segura dos usuários, com suporte a múltiplos métodos de login. | Firebase Authentication API |
| **Serviço de Notificação** | Permite o envio de lembretes e alertas aos pacientes sobre campanhas e consultas. | Firebase Cloud Messaging |
| **Banco de Dados** | Armazena todas as informações do sistema, como usuários, agendamentos, estoque de medicamentos, prontuários e campanhas. | PostgreSQL |

### Diagrama de Componentes

<div align="center">

  <img src="https://github.com/user-attachments/assets/cefcbe93-e8b0-4b08-b2d2-2cdce466d6e6" width="1100px" alt="Descrição da imagem">
</div>




