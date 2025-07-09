# Rastreabilidade das Funcionalidades nos Diagramas – UBS Digital 

Esta seção apresenta a associação entre as funcionalidades implementadas no MVP do sistema UBS Digital (versão mobile) e os respectivos elementos presentes nos diagramas de engenharia de software. O objetivo é garantir **rastreabilidade total** entre os requisitos funcionais, a estrutura arquitetural e os componentes do sistema.

Cada funcionalidade é documentada com:

- **Diagrama de Classe**: Classes da interface, lógica de apresentação (ViewModel), repositórios e fontes de dados (remota/local).
- **Diagrama C4 (Container)**: Localização da funcionalidade na arquitetura geral do sistema, incluindo comunicação entre front-end, API, banco de dados e serviços externos.
- **Diagrama C4 (Componente)**: Controladores e componentes específicos que realizam a funcionalidade, evidenciando interações e lógica de execução.

---

## Funcionalidade: Login

### 1. Diagrama de Classe
Classes utilizadas:
- LoginPage
- LoginViewModel
- AuthRepository
- AuthRemoteDS
- AuthLocalDS

### 2. Diagrama C4 (Container)
- Executada no Aplicativo Móvel (Thunkable).
- A API recebe os dados e valida via Firebase Authentication.
- As informações são registradas no Banco de Dados PostgreSQL.

### 3. Diagrama C4 (Componente)
- O Controlador de Login aciona o Componente de Autenticação.
- A comunicação ocorre via API, e a validação é feita no Firebase.

---

## Funcionalidade: Cadastro de Usuário

### 1. Diagrama de Classe
Classes utilizadas:
- RegisterPage
- RegisterViewModel
- AuthRepository
- AuthRemoteDS
- AuthLocalDS

### 2. Diagrama C4 (Container)
- A funcionalidade está no Aplicativo Móvel.
- Os dados são enviados à API, que os armazena no PostgreSQL.
- O Firebase é utilizado para registrar e validar a identidade do usuário.

### 3. Diagrama C4 (Componente)
- O Controlador de Cadastro aciona o Componente de Validação de Usuário.
- O componente valida os dados e realiza o envio para a API.

---

## Funcionalidade: Localizar UBS

### 1. Diagrama de Classe
Classes utilizadas:
- LocationPage
- LocationViewModel
- GeoRepository
- GeoRemoteDS

### 2. Diagrama C4 (Container)
- O Aplicativo Móvel obtém a localização do usuário.
- A API se comunica com a Google Maps API.
- As UBS são listadas a partir do banco PostgreSQL.

### 3. Diagrama C4 (Componente)
- O Controlador de Localização aciona o Componente de Mapa e Busca de UBS.
- Este componente consome as coordenadas e retorna as UBS mais próximas.

---

## Funcionalidade: Agendar Consulta

### 1. Diagrama de Classe
Classes utilizadas:
- AppointmentPage
- AppointmentViewModel
- AppointmentRepository
- AppointmentRemoteDS
- DoctorModel

### 2. Diagrama C4 (Container)
- O usuário agenda pelo Aplicativo Móvel.
- A API valida o agendamento e grava no banco PostgreSQL.
- Integração com o módulo de agenda médica.

### 3. Diagrama C4 (Componente)
- O Controlador de Agendamento interage com o Componente de Horários e Médicos Disponíveis.
- O componente realiza as validações e envia os dados à API.

---

## Funcionalidade: Consultar Medicamentos

### 1. Diagrama de Classe
Classes utilizadas:
- MedicineSearchPage
- MedicineViewModel
- MedicineRepository
- MedicineRemoteDS

### 2. Diagrama C4 (Container)
- O Aplicativo Móvel envia a consulta à API.
- A API acessa os dados no PostgreSQL e retorna a disponibilidade.

### 3. Diagrama C4 (Componente)
- O Controlador de Busca de Medicamento aciona o Componente de Consulta de Estoque.
- O componente exibe as informações do medicamento e sua localização nas UBS.

---
