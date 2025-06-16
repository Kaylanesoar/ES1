# Descrição do Diagrama de Contexto – UBS Digital
O diagrama de contexto apresentado descreve a arquitetura de alto nível da UBS Digital, uma aplicação móvel voltada à digitalização dos serviços de saúde oferecidos pelas Unidades Básicas de Saúde (UBS). A plataforma centraliza e facilita a interação entre três tipos de usuários: pacientes, médicos clínicos gerais e agentes de saúde.

Todos os usuários acessam inicialmente o Subsistema de Autenticação, responsável por validar a identidade e conceder acesso à aplicação. Após a autenticação, os usuários interagem com a Plataforma UBS Digital, que oferece funcionalidades específicas conforme o perfil de cada usuário.
A plataforma é composta por vários subsistemas, entre eles:

- Módulo de Agendamento – permite marcar consultas e exames.

- Módulo de Medicamentos – permite consultar disponibilidade e registrar entregas.

- Módulo de Agenda Médica – exibe os pacientes agendados por data.

- Módulo de Registro de Entregas – usado por agentes para registrar distribuição de medicamentos.

- Sistema de Estoque – subsistema interno que gerencia o controle e fornecimento de dados sobre medicamentos.

- Sistema de Notificações – serviço externo usado para envio de mensagens por SMS ou e-mail.

O diagrama segue o padrão do Modelo C4 (Nível de Contexto), identificando os principais atores externos, os limites do sistema e a forma como os usuários e sistemas interagem com a UBS Digital.

<br>
<br>
<br>



![Image](https://github.com/user-attachments/assets/c98e26df-0f15-4993-a500-d994ff98f305)2

<br>
<br>
<br>





# Diagrama mais detalhado:

<br>

## Persona Paciente


![Image](https://github.com/user-attachments/assets/6e256e2b-e3a7-47b0-ad1f-e270ea3c2e99)


<br>

## Persona Agente de Médico Clínico Geral
nico Geral 

![Image](https://github.com/user-attachments/assets/3d42b904-a044-44d3-982a-28f82b9f2635)


<br>

## Persona Agente de Saúde

![Image](https://github.com/user-attachments/assets/03a5c108-fa78-4da8-ae79-f6b436d55922)
