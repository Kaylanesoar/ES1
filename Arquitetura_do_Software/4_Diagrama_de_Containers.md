# Descrição do Diagrama de Containers – UBS Digital

O Diagrama de Containers representa os principais blocos de execução do sistema SUS Digital, suas tecnologias, responsabilidades e como eles se comunicam entre si e com sistemas externos. Este diagrama corresponde ao nível 2 do modelo C4, sendo fundamental para visualizar a estrutura lógica e tecnológica da solução.

##  Personas (Atores Externos) 

1. Paciente: Acessa o sistema via aplicativo ou navegador para agendar consultas, consultar disponibilidade de medicamentos, acompanhar campanhas de saúde e verificar histórico médico.

2. Médico: Utiliza o sistema para consultar sua agenda e atualizar os prontuários eletrônicos dos pacientes.

3. Agente de Saúde: Responsável por registrar campanhas, controlar o estoque de medicamentos e gerar relatórios de atendimentos.

##  Containers e suas responsabilidades
| Container | Descrição | Tecnologia |
|-----------|-----------|------------|
| Frontend Web | Interface do usuário acessada por pacientes, médicos e agentes. Permite realizar consultas, agendamentos e interações gerais com o sistema | React.js, HTML5, CSS3 |
| Backend API | Camada responsável pela lógica de negócio. Trata requisições, aplica regras, valida dados e interage com os sistemas externos e banco de dados. | Node.js (Express) ou SpringBoot |
| Banco de Dados | Armazena todas as informações do sistema, como usuários, agendamentos, estoque de medicamentos, prontuários e campanhas | PostgreSQL |
| Serviço de Autenticação | Sistema externo utilizado para autenticação segura dos usuários, com suporte a múltiplos métodos de login | Firebase Authentication |  
| Serviço de Geolocalização | API externa utilizada para localizar UBSs próximas e traçar rotas até elas | Google Maps API | 
| (Opcional) Sistema de Notificação | Permite o envio de lembretes e alertas aos pacientes sobre campanhas e consultas | Firebase Cloud Messaging | 
# Protocolos de Comunicação
•	A comunicação entre o Frontend e o Backend ocorre via REST API usando HTTPS/JSON.

•	O Backend acessa o banco de dados através de comandos SQL via JDBC ou ORM.

•	O Frontend interage diretamente com o serviço de autenticação (Firebase) para login.

•	O Backend se comunica com a Google Maps API para fornecer localização de UBSs.

•	O sistema opcional de notificações pode ser acionado pelo backend via requisições assíncronas.

## Diagrama de Container

![Diagrama](https://s5.aconvert.com/convert/p3r68-cdx67/yps61-43ck1-001.png)


