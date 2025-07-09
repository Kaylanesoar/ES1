# FUNCIONALIDADES E HISTÓRIAS DE USUÁRIO
Funcionalidades e Histórias de Usuário

As funcionalidades do MVP do sistema UBS Digital foram desenvolvidas com base em histórias de usuário, que descrevem as necessidades e expectativas dos usuários finais de forma objetiva e centrada em suas ações.

Cada história é estruturada com a seguinte abordagem:

- História de Usuário: redigida no formato “Como [tipo de usuário], quero [ação] para [objetivo]”, define o comportamento esperado do sistema do ponto de vista do usuário.

- Implementação no MVP: detalha como a funcionalidade foi efetivamente implementada, incluindo telas, interações, integrações com serviços e tecnologias utilizadas.

## 1. Objetivo Geral

Desenvolver um sistema digital para apoiar o acesso da população às Unidades Básicas de Saúde (UBS), com funcionalidades para agendamento de consultas, controle de estoque de medicamentos, visualização de campanhas de saúde e localização das UBS.

## 2. Funcionalidades Implementadas no MVP

---

### História de Usuário: H11  
**Como paciente**, quero fazer login no aplicativo,  
**para que eu possa acessar minhas informações médicas de forma simples e segura**.

- **Implementação no MVP:**
  - Tela de login que permite o usuário paciente a entrar no app (nome do usuário e senha).
  - Tela de cadastro que permite o usuário paciente a fazer um cadastro (nome completo, e-mail, CPF, senha e confirma senha) para novos usuários no app.
  - Tela de menu, logo após o login bem-sucedido, redireciona o paciente para seu perfil.

---

### História de Usuário: H08  
**Como paciente**, eu quero visualizar meus compromissos médicos e exames em um calendário,  
**para acompanhar minhas consultas e me organizar melhor**.

- **Implementação no MVP:**
  - Tela de menu que permite o usuário paciente a visualizar seus compromissos médicos logo após entrar no app.

---

### História de Usuário: H15  
**Como paciente**, quero marcar um exame na UBS pelo aplicativo,  
**para que eu não precise ir pessoalmente apenas para agendar e garantir meu atendimento de forma mais prática**.

- **Implementação no MVP:**
  - Tela de agendamento que permite o usuário paciente a agendar consultas de maneira prática.

---

### História de Usuário: H16  
**Como paciente**, quero saber se o medicamento prescrito está disponível na unidade de saúde,  
**para evitar deslocamentos desnecessários ou atrasos no tratamento**.

- **Implementação no MVP:**
  - Tela de medicamento permite o usuário paciente a buscar o medicamento pelo nome e informa a data/hora da última atualização da informação de estoque.
