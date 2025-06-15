# Descrição do Diagrama de Código – UBS Digital

  O Diagrama de Código detalha a implementação de um componente específico, mostrando as principais classes, interfaces, objetos e suas interações que realizam a funcionalidade descrita. Este diagrama corresponde ao nível 4 do modelo C4, o nível mais granular, e serve como uma ponte entre o desenho da arquitetura e o código-fonte real. Ele é utilizado para ilustrar as partes mais importantes ou complexas de um componente, facilitando o entendimento da implementação para os desenvolvedores.

Aqui, vemos os diferentes tipos de pessoas que interagem com o aplicativo.

A Base: A Classe Usuário

- É a classe fundamental, como um "modelo geral" para qualquer pessoa que use o sistema.
- Ela define o que é comum a todos: um ID, nome, email e senha para fazer login e sair.
- No diagrama, os métodos fazerLogin() e fazerLogout() mostram que qualquer usuário pode entrar ou sair do sistema.
- As Especializações: Paciente, Médico, AgenteDeSaúde

- A seta vazia (<|--) que sai de Paciente, Médico e AgenteDeSaúde e aponta para Usuário significa Herança.
- Isso quer dizer que um Paciente é um tipo de Usuário, um Médico é um tipo de Usuário, e assim por diante.
- Eles automaticamente ganham as características e ações básicas do Usuário (como login).
- Além disso, cada um tem suas próprias características e ações específicas: pacientes gerenciam exames, médicos veem agendas, e agentes de saúde registram entregas.

<div align="center">
  <img src="https://github.com/user-attachments/assets/8a45e88f-45df-4573-883e-0ecd41321fc6" width="800px" alt="Descrição da imagem">
</div>
