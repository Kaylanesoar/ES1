## Rastreabilidade com as Histórias de Usuário

---

### História de Usuário: H11
**Como paciente**, quero fazer login no aplicativo, **para que eu possa acessar minhas informações médicas de forma simples e segura**.

- **Implementação no MVP:**
  - Tela de login que permite o usuário paciente a entrar no app (nome do usuário e senha).
  - Tela de cadastro que permite o usuário paciente a fazer um cadastro (nome completo, e-mail, CPF, senha e confirma senha) para novos usuários no app.
  - Tela de menu, logo após o login bem-sucedido é redirecionado para seu perfil.

---

### História de Usuário: H08
**Como paciente**, eu quero visualizar meus compromissos médicos e exames em um calendário **para acompanhar minhas consultas e me organizar melhor**.

- **Implementação no MVP:**
  - Tela de menu que permite o usuário paciente a visualizar seus compromissos médicos logo após entrar no app.

---

### História de Usuário: H15
**Como paciente**, quero marcar um exame na UBS pelo aplicativo, **para que eu não precise ir pessoalmente apenas para agendar e garantir meu atendimento de forma mais prática**.

- **Implementação no MVP:**
  - Tela de agendamento que permite o usuário paciente a agendar consultas de maneira prática.

---

### História de Usuário: H16
**Como paciente**, quero saber se o medicamento prescrito está disponível na unidade de saúde, **para evitar deslocamentos desnecessários ou atrasos no tratamento**.

- **Implementação no MVP:**
  - Tela de medicamento permite o usuário paciente a buscar o medicamento pelo nome e informa a data/hora da última atualização da informação de estoque.

## Rastreabilidade das Funcionalidades nos Diagramas

---

Esta seção apresenta a associação entre as funcionalidades implementadas no MVP do sistema UBS Digital e os respectivos elementos presentes nos diagramas de engenharia de software. O objetivo é garantir rastreabilidade total entre os requisitos funcionais, a estrutura arquitetural e os componentes do sistema.

A rastreabilidade é organizada por funcionalidade, e cada item inclui:

- **Diagrama de Classe**: mapeia as classes envolvidas no frontend (UI e ViewModel), repositórios de dados e fontes de dados remota/local.
- **Diagrama C4 (Container)**: demonstra onde a funcionalidade se encontra dentro da arquitetura geral do sistema (aplicativo móvel, API, banco de dados, serviços externos).
- **Diagrama C4 (Componente)**: detalha os componentes de software e controladores específicos que executam a funcionalidade, evidenciando sua lógica e interação com o sistema.

---

## Funcionalidade: Login

1. **Diagrama de Classe**:  
   Utilize as classes `LoginPage`, `LoginViewModel`, `AuthRepository`, `AuthRemoteDS`, `AuthLocalDS`.

2. **Diagrama C4 (Container)**:  
   A funcionalidade faz parte do container **Aplicativo Móvel**, que se comunica com o container **API**, responsável por autenticar o usuário via **Sistema de Autenticação (Firebase Auth)** e armazenar os dados no **Banco de Dados PostgreSQL**.

3. **Diagrama C4 (Componente)**:  
   Utiliza o **Controlador de Login** que aciona o **Componente de Autenticação**. A autenticação é feita via API e validada no Firebase.

---

## Funcionalidade: Cadastro

1. **Diagrama de Classe**:  
   Utilize as classes `RegisterPage`, `RegisterViewModel`, `AuthRepository`, `AuthRemoteDS`, `AuthLocalDS`.

2. **Diagrama C4 (Container)**:  
   O cadastro acontece no **Aplicativo Móvel**, que envia os dados para a **API**, a qual salva os dados no **Banco de Dados PostgreSQL** e aciona o **Firebase** para registro e verificação.

3. **Diagrama C4 (Componente)**:  
   Usa o **Controlador de Cadastro** e o **Componente de Validação de Usuário** para preencher e validar os dados antes do envio para API.

---

## Funcionalidade: Localizar UBS

1. **Diagrama de Classe**:  
   Utilize as classes `LocationPage`, `LocationViewModel`, `GeoRepository`, `GeoRemoteDS`.

2. **Diagrama C4 (Container)**:  
   O **Aplicativo Móvel** acessa o **serviço de Geolocalização (Google Maps API)** via API e consulta a base de UBS cadastradas no **banco PostgreSQL**.

3. **Diagrama C4 (Componente)**:  
   O **Controlador de Localização** utiliza o **Componente de Mapa e Busca de UBS**, que consome as coordenadas geográficas e filtra a UBS mais próxima.

---

## Funcionalidade: Agendar Consulta

1. **Diagrama de Classe**:  
   Utilize as classes `AppointmentPage`, `AppointmentViewModel`, `AppointmentRepository`, `AppointmentRemoteDS`, `DoctorModel`.

2. **Diagrama C4 (Container)**:  
   No **Aplicativo Móvel**, o usuário escolhe data e especialidade. A **API** grava o agendamento no **Banco de Dados PostgreSQL** e confirma com o **módulo de agenda médica**.

3. **Diagrama C4 (Componente)**:  
   O **Controlador de Agendamento** interage com o **Componente de Horários e Médicos Disponíveis**, que realiza validações e envia os dados via API.

---

## Funcionalidade: Consultar Medicamentos

1. **Diagrama de Classe**:  
   Utilize as classes `MedicineSearchPage`, `MedicineViewModel`, `MedicineRepository`, `MedicineRemoteDS`.

2. **Diagrama C4 (Container)**:  
   O **Aplicativo Móvel** envia a consulta à **API**, que acessa o **estoque de medicamentos no Banco de Dados PostgreSQL**.

3. **Diagrama C4 (Componente)**:  
   O **Controlador de Busca de Medicamento** utiliza o **Componente de Consulta de Estoque**, que retorna a quantidade e localização do medicamento nas UBS.


