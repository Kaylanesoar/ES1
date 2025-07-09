# Documentação do MVP - UBS Digital

## Projeto: UBS DIGITAL 
Equipe:

- Guilherme Mendonça Castro - 22450461
- Ivonete Balieiro de Almeida - 22450581
- Kaylane Soares Vieira -22450510
- Marcos Correa Alves -22450269
- Sérgio Fernandes mar Filho -22450190
---
## 1. Objetivo Geral

Desenvolver um sistema digital para apoiar o acesso da população às Unidades Básicas de Saúde (UBS), com funcionalidades para agendamento de consultas, controle de estoque de medicamentos, visualização de campanhas de saúde e localização das UBS.
---
## 2. Funcionalidades Implementadas no MVP

### 1. Tela de Cadastro de Usuário

História: H11 - "Como paciente, quero fazer login no aplicativo, para acessar minhas informações."

Implementação: Formulário com campos de nome, email, CPF, senha. Dados salvos no Firebase Auth.

### 2. Tela de Login

História: H11 - Login com email e senha.

Implementação: Integração com Firebase Auth. Valida login e redireciona para tela inicial. Contém a logo do sistema.

### 3. Agendamento de Consulta

História: H02 - "Como paciente, quero agendar consultas com médicos da UBS."

Implementação: Escolha de especialidade, data e horário. Salva agendamento no banco.

### 4. Consulta de Medicamentos

História: H05 - "Como paciente, quero consultar se um medicamento está disponível."

Implementação: Campo de busca por nome. Exibe quantidade e UBS correspondente. Dados atualizados do estoque.

---
## 3. Rastreabilidade com Diagramas

### Diagrama de Containers

- Aplicativo Móvel (Thunkable): Interface usada por pacientes para login, agendamento, busca de UBS e medicamentos.

- Aplicação Web (React): Acesso por agentes e médicos. Gera relatórios, registra entregas, gerencia campanhas.

- Backend API (Node.js/Spring Boot): Implementa a lógica de negócio e interage com banco de dados.

- Serviço de Autenticação: Firebase Auth (Login e validação de identidade)

- Serviço de Notificação: Firebase Messaging (envio de alertas)

- Banco de Dados (PostgreSQL): Armazena dados de pacientes, agendamentos, medicamentos, UBS e entregas.
---
### Diagrama de Componentes

- Controllers: AgendamentoController, CampanhaController, EntregaController

- Services: Servico de Agendamento, Servico de Campanha, Servico de Entregas

- Adaptadores: Auth, Notificação, Repositório

- Interações REST entre os componentes frontend e backend estão bem mapeadas e refletem as histórias do MVP.
---
### Diagrama de Classes

- Usuario: Classe base com login, logout, email, senha. 

- Paciente: Herda de Usuario, acessa relatórios, agendamentos, medicamentos.

- Médico: Visualiza agendamentos.

- AgenteDeSaude: Registra entrega de medicamentos.

- Medicamento, UBS, Agendamento, Exame, Relatorio: Relacionamentos mapeados com multiplicidade e métodos específicos.
  
---
## 4. Arquitetura do Sistema

Camadas:

Frontend: Thunkable (Mobile App)

API: Node.js com Express e Spring Boot

Banco de Dados: PostgreSQL

Serviços Externos:

Firebase Auth (autenticação)

Firebase Cloud Messaging (notificação)

Google Maps API (localização de UBS)

---
## 5. Critérios Técnicos Atendidos

Login e cadastro funcionais

Navegação entre telas implementada

Persistência de dados no banco

Interface com identidade visual

Splash screen com logo

Mensagens de feedback e validação de campos

Print e vídeo de demonstração do sistema

---

## 6. Prints das telas

### Tela de Login 

A tela de login é a porta de entrada do sistema. Nela, o usuário insere suas credenciais (e-mail e senha) para acessar as funcionalidades disponíveis. Essa etapa garante a segurança e a personalização do acesso, permitindo que cada usuário interaja com o sistema conforme seu perfil.

<div align="center">
  <img src="https://github.com/user-attachments/assets/6f3c766f-88c6-44e3-a8d0-103793a0b50d" width="275px" alt="Descrição da imagem">
</div>

### Tela de Cadastro

Na tela de cadastro, é possível registrar novos usuários no sistema. Ela solicita informações básicas como nome, e-mail, senha e outros dados relevantes para autenticação e identificação futura. Essa tela é essencial para a criação de contas e início da utilização do sistema.

<div align="center">
  <img src="https://github.com/user-attachments/assets/b6f38045-490d-40fc-9a52-a1ab191a3edf" width="275px" alt="Descrição da imagem">
</div>

### Tela de Menu

A tela de menu funciona como o painel principal do sistema. Após o login, o usuário tem acesso rápido às principais funcionalidades disponíveis, como agendamento, consulta de medicamentos, entre outras opções. Seu layout visa facilitar a navegação e a experiência do usuário.

<div align="center">
  <img src="https://github.com/user-attachments/assets/610c1d82-e88b-4819-b4e1-71865d4b45af" width="275px" alt="Descrição da imagem">
</div>

### Tela de Agendamento

Nesta tela, o usuário pode realizar agendamentos de consultas, procedimentos ou serviços oferecidos. Ela exibe campos para seleção de datas, horários e outras informações relevantes, otimizando a organização e o controle dos compromissos.

<div align="center">
  <img src="https://github.com/user-attachments/assets/dc144fec-e997-4630-9a1a-a8c3f8061fd8" width="275px" alt="Descrição da imagem">
</div>

### Tela de Consulta de Medicamento

A tela de consulta de medicamento permite ao usuário pesquisar por medicamentos disponíveis, verificar informações detalhadas e tirar dúvidas relacionadas ao uso. É uma funcionalidade importante para garantir acesso rápido e seguro a dados farmacológicos.

<div align="center">
  <img src="https://github.com/user-attachments/assets/09d55098-5dd3-45a0-a0a7-37f2da1f9b5b" width="275px" alt="Descrição da imagem">
</div>
