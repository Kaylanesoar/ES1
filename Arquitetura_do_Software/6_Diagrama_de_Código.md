# Descrição do Diagrama de Código – UBS Digital

  O Diagrama de Código detalha a implementação de um componente específico, mostrando as principais classes, interfaces, objetos e suas interações que realizam a funcionalidade descrita. Este diagrama corresponde ao nível 4 do modelo C4, o nível mais granular, e serve como uma ponte entre o desenho da arquitetura e o código-fonte real. Ele é utilizado para ilustrar as partes mais importantes ou complexas de um componente, facilitando o entendimento da implementação para os desenvolvedores.

1. Aqui, vemos os diferentes tipos de pessoas que interagem com o aplicativo.

A Base: A Classe Usuário

- É a classe fundamental, como um "modelo geral" para qualquer pessoa que use o sistema.
- Ela define o que é comum a todos: um ID, nome, email e senha para fazer login e sair.
- No diagrama, os métodos fazerLogin() e fazerLogout() mostram que qualquer usuário pode entrar ou sair do sistema.

As Especializações: Paciente, Médico, AgenteDeSaúde

- A seta vazia (<|--) que sai de Paciente, Médico e AgenteDeSaúde e aponta para Usuário significa Herança.
- Isso quer dizer que um Paciente é um tipo de Usuário, um Médico é um tipo de Usuário, e assim por diante.
- Eles automaticamente ganham as características e ações básicas do Usuário (como login).
- Além disso, cada um tem suas próprias características e ações específicas: pacientes gerenciam exames, médicos veem agendas, e agentes de saúde registram entregas.

<div align="center">
  <img src="https://github.com/user-attachments/assets/8a45e88f-45df-4573-883e-0ecd41321fc6" width="800px" alt="Descrição da imagem">
</div>


2. As Relações e Cardinalidades

As linhas entre as classes mostram como elas se conectam. Os números nas pontas das linhas (as Cardinalidades) nos dizem "quantos" de uma peça se relacionam com "quantos" da outra.

Relações do Paciente:

- Um Paciente possui InformacaoMedica (1 para *): Isso significa que um paciente pode ter muitas informações médicas (histórico, resultados), mas cada informação pertence a apenas um paciente.
- Um Paciente agenda Agendamento (1 para 1): Um paciente pode fazer apenas um agendamento por vez.
- Um Paciente pode ter Medicamento prescrito (1 para 0..*): Um paciente pode ter vários (ou nenhum) medicamentos prescritos.

Relação do Médico:

- Um Médico gerencia Agendamento (1 para 0..*): Um médico pode ser responsável por vários (ou nenhum) agendamentos em sua agenda.

Relação do AgenteDeSaúde:

- Um AgenteDeSaúde registra a entrega de Medicamento (1 para 0..*): Um agente pode registrar a entrega de vários medicamentos.

Relações da UBS (Unidade Básica de Saúde):

- Uma UBS possui Medicamento em estoque (1 para 0..*): Uma UBS pode ter vários (ou nenhum) tipos de medicamentos em seu estoque.
- Uma UBS oferece Exame (1 para 0..*): Uma UBS pode oferecer vários (ou nenhum) tipos de exames.

Relações do Agendamento (A Peça Central):

- Um Agendamento pertence a Paciente (1 para 1): Cada agendamento está ligado a um único paciente.
- Um Agendamento pertence a Médico (1 para 1): Cada agendamento está ligado a um único médico.
- Um Agendamento é parte de um Exame (1 para 1): Se for um agendamento de exame, ele está ligado a um único exame específico.

<div align="center">
  <img src="https://github.com/user-attachments/assets/c39e71d0-758b-4d92-bd99-849b25e58eb4" width="800px" alt="Descrição da imagem">
</div>


Conclusão
Este diagrama nos mostra como projetamos o sistema:

- Usando Herança, evitamos repetir informações básicas de usuário.
- Com as Relações, definimos como pacientes se conectam a informações e agendamentos, como médicos gerenciam suas agendas, e como as UBSs controlam seus recursos.
- As Cardinalidades são as "regras" que nos dizem quantos de cada item podem se conectar, garantindo que o sistema funcione de forma lógica e coerente.
- É um mapa de como todas as partes do aplicativo se interligam para atender às necessidades dos pacientes, médicos e agentes de saúde.

<div align="center">

  <img src="https://github.com/user-attachments/assets/e7ae875d-68c4-475f-9686-42750ce32a33" width="850px" alt="Descrição da imagem">
</div>
