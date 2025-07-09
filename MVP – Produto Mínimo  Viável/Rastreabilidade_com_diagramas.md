# Rastreabilidade das Funcionalidades nos Diagramas – UBS Digital 

Esta seção apresenta a associação entre as funcionalidades implementadas no MVP do sistema UBS Digital (versão mobile) e os elementos arquiteturais presentes nos diagramas de engenharia de software. O objetivo é garantir rastreabilidade completa entre os requisitos funcionais, a arquitetura do sistema e os seus componentes técnicos.

Cada funcionalidade inclui:

- **Diagrama de Classe**: Identifica as classes responsáveis pela interface, lógica, repositórios e fontes de dados.
- **Diagrama C4 (Container)**: Indica o container onde a funcionalidade ocorre e quais sistemas ou serviços externos estão envolvidos.
- **Diagrama C4 (Componente)**: Mostra os componentes internos responsáveis pela execução da funcionalidade.

---

## Funcionalidade: Login

### Diagrama de Classe
**Classes envolvidas:**  
- `LoginPage` – Tela onde o usuário insere suas credenciais.  
- `LoginViewModel` – Lida com a lógica do formulário de login.  
- `AuthRepository` – Centraliza o acesso aos dados de autenticação.  
- `AuthRemoteDS` – Acesso remoto à API para autenticação.  
- `AuthLocalDS` – Armazena sessões localmente (cache).

**Indicação no diagrama:**  
Representa o fluxo completo de autenticação, desde a UI até o backend via repositório.

### Diagrama C4 (Container)
**Localização:**  
- Aplicativo Móvel → envia dados de login  
- API → realiza autenticação  
- Firebase Auth → valida as credenciais  
- Banco de Dados PostgreSQL → armazena sessão/usuário autenticado

**Indicação no diagrama:**  
A funcionalidade está no fluxo entre os containers: **Aplicativo Móvel ↔ API ↔ Firebase Auth**.

### Diagrama C4 (Componente)
**Componentes envolvidos:**  
- `AuthController`  
- `AuthService`  
- `FirebaseAuthAdapter`

**Indicação no diagrama:**  
A requisição de login aciona o **AuthController**, que utiliza o serviço de autenticação, validando com o adaptador do Firebase.

---

## Funcionalidade: Cadastro de Usuário

### Diagrama de Classe
**Classes envolvidas:**  
- `RegisterPage`  
- `RegisterViewModel`  
- `AuthRepository`  
- `AuthRemoteDS`  
- `AuthLocalDS`

**Indicação no diagrama:**  
Mostra a criação de conta com validações locais e comunicação com a API e Firebase para registro.

### Diagrama C4 (Container)
**Localização:**  
- Aplicativo Móvel → envia dados do formulário  
- API → registra o novo usuário  
- Firebase Auth → registra o usuário no sistema  
- Banco de Dados PostgreSQL → armazena os dados do novo usuário

**Indicação no diagrama:**  
Fluxo entre **Aplicativo Móvel ↔ API ↔ Firebase Auth ↔ Banco de Dados**

### Diagrama C4 (Componente)
**Componentes envolvidos:**  
- `AuthController`  
- `AuthService`  
- `FirebaseAuthAdapter`

**Indicação no diagrama:**  
A funcionalidade é tratada pelo mesmo fluxo de autenticação, mas com a operação de registro.

---

## Funcionalidade: Localizar UBS

### Diagrama de Classe
**Classes envolvidas:**  
- `LocationPage`  
- `LocationViewModel`  
- `GeoRepository`  
- `GeoRemoteDS`

**Indicação no diagrama:**  
Classes que coordenam o uso da localização e consulta das UBS próximas.

### Diagrama C4 (Container)
**Localização:**  
- Aplicativo Móvel → coleta geolocalização  
- API → consulta base de dados de UBS  
- Google Maps API → fornece localização e rotas  
- Banco de Dados PostgreSQL → armazena UBS cadastradas

**Indicação no diagrama:**  
Fluxo entre **Aplicativo Móvel ↔ API ↔ Banco de Dados ↔ Google Maps API**

### Diagrama C4 (Componente)
**Componentes envolvidos:**  
- `GeoController`  
- `GeoService`  
- `GeoRepositoryAdapter`

**Indicação no diagrama:**  
A requisição ao **GeoController** retorna as UBS ordenadas pela distância com base nas coordenadas do usuário.

---

## Funcionalidade: Agendar Consulta

### Diagrama de Classe
**Classes envolvidas:**  
- `AppointmentPage`  
- `AppointmentViewModel`  
- `AppointmentRepository`  
- `AppointmentRemoteDS`  
- `DoctorModel`

**Indicação no diagrama:**  
Fluxo de agendamento com lógica para escolha de médicos, datas e horários disponíveis.

### Diagrama C4 (Container)
**Localização:**  
- Aplicativo Móvel → envia dados do agendamento  
- API → processa e grava a consulta  
- Banco de Dados PostgreSQL → armazena agendamentos  
- Sistema de Notificação (opcional) → envia confirmação ao paciente

**Indicação no diagrama:**  
Fluxo entre **Aplicativo Móvel ↔ API ↔ Banco de Dados**, com possível integração com sistema de notificações.

### Diagrama C4 (Componente)
**Componentes envolvidos:**  
- `AgendamentoController`  
- `ServicoDeAgendamento`  
- `AgendamentoRepositoryAdapter`

**Indicação no diagrama:**  
Controlador de agendamento coordena a lógica de verificação de disponibilidade e confirmação da reserva.

---

## Funcionalidade: Consultar Medicamentos

### Diagrama de Classe
**Classes envolvidas:**  
- `MedicineSearchPage`  
- `MedicineViewModel`  
- `MedicineRepository`  
- `MedicineRemoteDS`

**Indicação no diagrama:**  
Classes responsáveis pela pesquisa, exibição e lógica de consulta de estoque.

### Diagrama C4 (Container)
**Localização:**  
- Aplicativo Móvel → pesquisa por nome do medicamento  
- API → acessa estoque atualizado  
- Banco de Dados PostgreSQL → contém os dados dos medicamentos e suas quantidades por UBS

**Indicação no diagrama:**  
Fluxo entre **Aplicativo Móvel ↔ API ↔ Banco de Dados PostgreSQL**

### Diagrama C4 (Componente)
**Componentes envolvidos:**  
- `MedicamentoController`  
- `ServicoDeMedicamentos`  
- `MedicamentoRepositoryAdapter`

**Indicação no diagrama:**  
Controlador consulta o repositório, que filtra medicamentos com base no nome e localidade do usuário.

---
