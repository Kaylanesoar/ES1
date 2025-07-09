# FUNCIONALIDADES E HISTÓRIAS DE USUÁRIO
Funcionalidades e Histórias de Usuário

As funcionalidades do MVP do sistema UBS Digital foram desenvolvidas com base em histórias de usuário, que descrevem as necessidades e expectativas dos usuários finais de forma objetiva e centrada em suas ações.

Cada história é estruturada com a seguinte abordagem:

- História de Usuário: redigida no formato “Como [tipo de usuário], quero [ação] para [objetivo]”, define o comportamento esperado do sistema do ponto de vista do usuário.

- Implementação no MVP: detalha como a funcionalidade foi efetivamente implementada, incluindo telas, interações, integrações com serviços e tecnologias utilizadas.

## 1. Objetivo Geral

Desenvolver um sistema digital para apoiar o acesso da população às Unidades Básicas de Saúde (UBS), com funcionalidades para agendamento de consultas, controle de estoque de medicamentos, visualização de campanhas de saúde e localização das UBS.

## 2. Funcionalidades Implementadas no MVP

Abaixo estão listadas as histórias de usuário do MVP, detalhadas com sua respectiva implementação:
descrevem o comportamento desejado dos usuários e como foram implementadas no MVP:

### H1 - Login

História de Usuário:
"Como usuário, quero fazer login com meu CPF e senha para acessar minha conta no aplicativo."

Implementação no MVP:
Tela de login com campos para CPF e senha, botão “Entrar” e opção de “Esqueceu a senha?”. A tela permite autenticação do usuário com Firebase Auth.

### H2 - Cadastro

História de Usuário:
"Como usuário, quero preencher minhas informações básicas para poder me cadastrar e usar o aplicativo."

Implementação no MVP:
Tela de cadastro com campos para nome completo, CPF e senha. O botão “Cadastrar” efetiva o registro do usuário no sistema usando Firebase Authentication.
História de Usuário:
"Como paciente, quero preencher minhas informações básicas para poder me cadastrar e usar o aplicativo."

Implementação no MVP:
Tela de cadastro com campos para nome completo, CPF e senha. Botão “Cadastrar” efetiva o registro do usuário no sistema com Firebase.

### História: H11 - Login com CPF e senha.

Implementação: Integração com Firebase Auth. Valida login e redireciona para tela inicial. Contém a logo do sistema.

### H3 - Localizar UBS

História de Usuário:
"Como paciente, quero localizar a UBS mais próxima da minha residência para buscar atendimento com praticidade."

Implementação no MVP:
A funcionalidade utiliza a geolocalização do dispositivo para identificar UBSs próximas, exibe nome, endereço e botão "Como chegar" com integração ao Google Maps. Exibe apenas UBSs com status ativo.

### H4 - Agendar Consulta

História de Usuário:
"Como paciente, quero agendar consultas com médicos da UBS para garantir meu atendimento."

Implementação no MVP:
Interface com seleção de especialidade, data e horário. Validação de agendamento único por especialidade. O sistema grava no banco via API Spring Boot.
História de Usuário:
"Como paciente, quero agendar consultas com médicos da UBS para garantir meu atendimento."

Implementação no MVP:
Interface para escolher especialidade, data e horário disponíveis. Registro é salvo via API e persistido no banco PostgreSQL.

### História: H02 - "Como paciente, quero agendar consultas com médicos da UBS."

Implementação: Escolha de especialidade, data e horário. Salva agendamento no banco.

### H5 - Consultar Medicamentos

História de Usuário:
"Como paciente, quero consultar se um medicamento está disponível antes de me deslocar até a UBS."

Implementação no MVP:
Campo de busca por nome do medicamento. Exibe a quantidade disponível e localização da UBS. A atualização de estoque é feita a cada 5 minutos. Visualização em tempo real com integração ao módulo de medicamentos.
