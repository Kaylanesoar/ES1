# Funcionalidade: Login

## Diagrama de Classe:
Utilize as classes LoginPage, LoginViewModel, AuthRepository, AuthRemoteDS, AuthLocalDS.

## Diagrama C4 (Container):
A funcionalidade faz parte do container Aplicativo Móvel, que se comunica com o container API, responsável por autenticar o usuário via Sistema de Autenticação (Firebase Auth) e armazenar os dados no Banco de Dados PostgreSQL.

## Diagrama C4 (Componente):
Utiliza o Controlador de Login que aciona o Componente de Autenticação. A autenticação é feita via API e validada no Firebase.

Funcionalidade: Cadastro
Diagrama de Classe:
Utilize as classes RegisterPage, RegisterViewModel, AuthRepository, AuthRemoteDS, AuthLocalDS.

## Diagrama C4 (Container):
O cadastro acontece no Aplicativo Móvel, que envia os dados para a API, a qual salva os dados no Banco de Dados PostgreSQL e aciona o Firebase para registro e verificação.

## Diagrama C4 (Componente):
Usa o Controlador de Cadastro e o Componente de Validação de Usuário para preencher e validar os dados antes do envio para API.

Funcionalidade: Localizar UBS
Diagrama de Classe:
Utilize as classes LocationPage, LocationViewModel, GeoRepository, GeoRemoteDS.

Diagrama C4 (Container):
O Aplicativo Móvel acessa o serviço de Geolocalização (Google Maps API) via API e consulta a base de UBS cadastradas no banco PostgreSQL.

## Diagrama C4 (Componente):
O Controlador de Localização utiliza o Componente de Mapa e Busca de UBS, que consome as coordenadas geográficas e filtra a UBS mais próxima.

Funcionalidade: Agendar Consulta
Diagrama de Classe:
Utilize as classes AppointmentPage, AppointmentViewModel, AppointmentRepository, AppointmentRemoteDS, DoctorModel.

## Diagrama C4 (Container):
No Aplicativo Móvel, o usuário escolhe data e especialidade. A API grava o agendamento no Banco de Dados PostgreSQL e confirma com o módulo de agenda médica.

## Diagrama C4 (Componente):
O Controlador de Agendamento interage com o Componente de Horários e Médicos Disponíveis, que realiza validações e envia os dados via API.

Funcionalidade: Consultar Medicamentos
Diagrama de Classe:
Utilize as classes MedicineSearchPage, MedicineViewModel, MedicineRepository, MedicineRemoteDS.

## Diagrama C4 (Container):
O Aplicativo Móvel envia a consulta à API, que acessa o estoque de medicamentos no Banco de Dados PostgreSQL.

## Diagrama C4 (Componente):
O Controlador de Busca de Medicamento utiliza o Componente de Consulta de Estoque, que retorna a quantidade e localização do medicamento nas UBS.


