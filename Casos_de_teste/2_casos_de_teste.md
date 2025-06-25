# Trabalho Prático III – Parte 2  
## Casos de Teste – Primeiras 3 Histórias de Usuário
## História #6 – Verificar disponibilidade de medicamentos

### História de Usuário
Como agente de saúde, quero verificar, no meu dispositivo, se um medicamento está disponível no posto, para orientar corretamente os pacientes durante minhas visitas.

### Tabela de Casos de Teste

| Casos de Teste | Classes de Equivalência | Entradas                                                              | Resultado Esperado |
|----------------|--------------------------|-----------------------------------------------------------------------|--------------------|
| Caso 1         | 1, 3, 5                  | Medicamento existe, dados sincronizados, conexão ativa               | Dados Válidos      |
| Caso 2         | 2, 3, 5                  | Medicamento não encontrado                                           | Dados Inválidos    |
| Caso 3         | 1, 4, 5                  | Medicamento existe, dados desatualizados                             | Dados Inválidos    |
| Caso 4         | 1, 3, 6                  | Medicamento existe, dados sincronizados, mas sem conexão             | Dados Inválidos    |

### Classes de Equivalência

| Nº | Classe                             |
|----|-------------------------------------|
| 1  | Nome de medicamento existente       |
| 2  | Nome de medicamento inexistente     |
| 3  | Estoque sincronizado                |
| 4  | Estoque desatualizado               |
| 5  | Conexão ativa                       |
| 6  | Sem conexão                         |


## História #9 – Ver calendário de vacinação

### História de Usuário
Como paciente, eu gostaria de visualizar um calendário com campanhas de vacinação, para não perder prazos importantes.

### Tabela de Casos de Teste

| Casos de Teste | Classes de Equivalência | Entradas                                                                 | Resultado Esperado |
|----------------|--------------------------|--------------------------------------------------------------------------|--------------------|
| Caso 1         | 1, 3, 5                  | Tipo de vacina conhecida, calendário acessível, ícone exibido corretamente | Dados Válidos    |
| Caso 2         | 2, 3, 5                  | Tipo de vacina desconhecida, calendário acessível, ícone exibido         | Dados Inválidos    |
| Caso 3         | 1, 4, 5                  | Vacina conhecida, falha ao acessar calendário                            | Dados Inválidos    |
| Caso 4         | 1, 3, 6                  | Vacina conhecida, calendário acessível, ícone ausente                    | Dados Inválidos    |

### Classes de Equivalência

| Nº | Classe                                  |
|----|------------------------------------------|
| 1  | Vacina conhecida (ex: covid, gripe)      |
| 2  | Vacina desconhecida                      |
| 3  | Calendário acessível                     |
| 4  | Calendário indisponível                  |
| 5  | Ícone/cor exibido corretamente           |
| 6  | Ícone/cor ausente ou incorreto           |


## História #11 – Login no aplicativo

### História de Usuário
Como paciente, quero fazer login no aplicativo, para que eu possa acessar minhas informações médicas de forma simples e segura.

### Tabela de Casos de Teste

| Casos de Teste | Classes de Equivalência | Entradas                                                  | Resultado Esperado |
|----------------|--------------------------|-----------------------------------------------------------|--------------------|
| Caso 1         | 1, 4, 7, 9                | CPF válido, senha válida, e-mail cadastrado               | Dados Válidos      |
| Caso 2         | 2, 4, 7, 9                | CPF inválido (000.000.000-00), senha válida               | Dados Inválidos    |
| Caso 3         | 3, 4, 7, 9                | Senha vazia (“ ”), CPF válido                             | Dados Inválidos    |
| Caso 4         | 5, 1, 7, 9                | CPF não cadastrado, senha válida                          | Dados Inválidos    |
| Caso 5         | 6, 1, 7, 8                | CPF válido, senha válida, e-mail/SMS ausente              | Dados Inválidos    |

### Classes de Equivalência

| Nº | Classe                                  |
|----|------------------------------------------|
| 1  | CPF válido                               |
| 2  | CPF inválido sintaticamente              |
| 3  | Senha inválida                           |
| 4  | Senha válida                             |
| 5  | CPF não cadastrado                       |
| 6  | Recuperação de senha sem e-mail/SMS      |
| 7  | CPF cadastrado                           |
| 8  | Recuperação de senha com dados ausentes  |
| 9  | E-mail/SMS válido                        |

## H14 – Localizar UBS próxima (Agente de Saúde)

**História do Usuário**  
Como agente de saúde, eu gostaria de encontrar a UBS mais próxima, para que eu possa encaminhar pacientes ao atendimento adequado e facilitar o acesso aos serviços de saúde na comunidade.

**Critérios de Aceitação**  
- O agente de saúde deve conseguir acessar informações detalhadas de cada UBS, como capacidade de atendimento, telefones de contato e estrutura disponível.

**Regras de Negócio**  
- O sistema deve exibir, de forma clara e organizada, os dados de localização necessários.

### Classes de Equivalência

| Condição de Entrada                | Classes Válidas             | Classes Inválidas           |
|-----------------------------------|-----------------------------|-----------------------------|
| Localização informada corretamente| Localização reconhecida (1) | Localização inexistente (2) |
| UBS disponível                    | UBS encontrada (3)          | Nenhuma UBS próxima (4)     |
| UBS possui dados completos        | Dados completos (5)         | Dados incompletos (6)       |

### Casos de Teste

| Caso | Classes  | Entrada                                  | Resultado Esperado                     |
|------|----------|-------------------------------------------|----------------------------------------|
| 1    | 1, 3, 5  | Localização "Centro", UBS com dados       | UBS exibida corretamente               |
| 2    | 2, 3, 5  | Localização "XYZ" (inexistente)           | Mensagem de erro: local não encontrado |
| 3    | 1, 4, 5  | Localização válida, nenhuma UBS próxima   | Mensagem: "Nenhuma UBS próxima"        |
| 4    | 1, 3, 6  | UBS encontrada, dados incompletos         | Exibe UBS com alerta de dados faltando |

## H16 – Verificar disponibilidade de medicamento (Paciente)

**História do Usuário**  
Como paciente, quero saber se o medicamento prescrito está disponível na unidade de saúde, para evitar deslocamentos desnecessários ou atrasos no tratamento.

**Critérios de Aceitação**  
- O sistema deve permitir a busca pelo nome do medicamento.

**Regras de Negócio**  
- A consulta deve exibir a data/hora da última atualização da informação de estoque.

### Classes de Equivalência

| Condição de Entrada           | Classes Válidas        | Classes Inválidas           |
|------------------------------|------------------------|-----------------------------|
| Nome do medicamento correto  | Medicamento existente (1) | Medicamento inexistente (2) |
| Disponibilidade em estoque   | Disponível (3)         | Indisponível (4)            |
| Informação de estoque atual  | Data/hora exibida (5)  | Sem atualização (6)         |

### Casos de Teste

| Caso | Classes  | Entrada                                      | Resultado Esperado                         |
|------|----------|-----------------------------------------------|--------------------------------------------|
| 1    | 1, 3, 5  | Medicamento "Paracetamol", disponível         | Exibe disponibilidade e data/hora          |
| 2    | 2, 3, 5  | Medicamento "RemédioX" (não existe)           | Mensagem: medicamento não encontrado        |
| 3    | 1, 4, 5  | "Dipirona", indisponível                      | Mensagem: medicamento fora de estoque       |
| 4    | 1, 3, 6  | "Ibuprofeno", disponível, sem atualização     | Exibe medicamento com alerta de desatualização |

## H01 – Visualizar agendamentos (Médico)

**História do Usuário**  
Como médico, quero visualizar a quantidade de pacientes agendados para um dia específico, para que eu possa me organizar melhor e planejar minha rotina de atendimentos.

**Critérios de Aceitação**  
- O sistema deve permitir selecionar uma data no calendário.  
- O sistema deve exibir o número total de pacientes agendados para a data selecionada.

**Regras de Negócio**  
- Apenas médicos autenticados podem acessar essa funcionalidade.  
- Os agendamentos exibidos devem estar associados ao médico logado.

### Classes de Equivalência

| Condição de Entrada            | Classes Válidas         | Classes Inválidas          |
|-------------------------------|--------------------------|----------------------------|
| Autenticação do usuário       | Médico autenticado (1)   | Não autenticado (2)        |
| Seleção de data               | Data válida (3)          | Data inválida/não selecionada (4) |
| Associação dos agendamentos   | Pertencem ao médico (5)  | Agendamentos de outro (6)  |

### Casos de Teste

| Caso | Classes  | Entrada                                       | Resultado Esperado                    |
|------|----------|-----------------------------------------------|---------------------------------------|
| 1    | 1, 3, 5  | Médico logado, data válida, agendamentos ok   | Exibe número de pacientes             |
| 2    | 2, 3, 5  | Usuário não autenticado                       | Acesso negado                         |
| 3    | 1, 4, 5  | Data não selecionada                          | Mensagem: selecione uma data válida   |
| 4    | 1, 3, 6  | Visualização de outro médico                  | Erro: acesso não autorizado           |

---

## H10 – Registrar entrega de medicamentos (Agente de Saúde)

**História do Usuário**  
Como agente de saúde, quero registrar a entrega de medicamentos aos pacientes durante visitas domiciliares, para manter o controle do estoque e garantir o tratamento.

**Critérios de Aceitação**  
- Interface simples para registrar entregas no local.

**Regras de Negócio**  
- O sistema deve impedir o registro de entrega se não houver estoque suficiente.

### Classes de Equivalência

| Condição de Entrada     | Classes Válidas         | Classes Inválidas           |
|-------------------------|--------------------------|------------------------------|
| Interface de registro   | Interface acessada (1)   | Interface inacessível (2)    |
| Verificação de estoque  | Estoque suficiente (3)   | Estoque insuficiente (4)     |
| Dados da entrega        | Dados válidos (5)        | Dados incompletos (6)        |

### Casos de Teste

| Caso | Classes  | Entrada                                      | Resultado Esperado                      |
|------|----------|-----------------------------------------------|-----------------------------------------|
| 1    | 1, 3, 5  | Interface acessada, estoque disponível        | Registro efetuado com sucesso           |
| 2    | 2, 3, 5  | Interface indisponível                        | Erro: não foi possível acessar a interface |
| 3    | 1, 4, 5  | Estoque insuficiente                          | Erro: estoque insuficiente              |
| 4    | 1, 3, 6  | Dados incompletos                             | Erro: dados incompletos                 |

---

## H08 – Visualizar compromissos no calendário (Paciente)

**História do Usuário**  
Como paciente, eu quero visualizar meus compromissos, médicos e exames em um calendário para acompanhar facilmente minhas consultas e me organizar melhor.

**Critérios de Aceitação**  
- Eventos exibem título, tipo, horário e local.  
- Visualização por dia, semana ou mês.  
- Clicar em evento exibe detalhes.

**Regras de Negócio**  
- Eventos passados não podem ser editados.  
- Eventos cancelados aparecem com marcação visual distinta.

### Classes de Equivalência

| Condição de Entrada          | Classes Válidas         | Classes Inválidas               |
|-----------------------------|--------------------------|----------------------------------|
| Dados exibidos no calendário| Título, tipo, horário (1)| Campos vazios (2), dados errados (3) |
| Tipo de visualização        | Dia, semana, mês (4)     | Trimestre, ano, vazio (5)        |
| Evento clicado              | Exibe detalhes (6)       | Ação inoperante (7)              |

### Casos de Teste

| Caso | Classes  | Entrada                              | Resultado Esperado          |
|------|----------|---------------------------------------|-----------------------------|
| 1    | 1, 4, 6  | Consulta às 8h, hoje                  | Exibe detalhes completos    |
| 2    | 2, 4, 6  | Campos vazios                         | Dados inválidos             |
| 3    | 3, 4, 6  | Texto sem estrutura de evento         | Dados inválidos             |
| 4    | 5, 1, 6  | Visualização por ano                  | Dados inválidos             |
| 5    | 7, 1, 4  | Falha ao clicar no evento             | Dados inválidos             |

---

## H11 – Login no aplicativo (Paciente)

**História do Usuário**  
Como paciente, quero fazer login no aplicativo, para que eu possa acessar minhas informações médicas de forma simples e segura.

**Critérios de Aceitação**  
- Login somente com CPF e senha válidos.  
- Mensagem clara em caso de erro.  
- Opção de recuperação de senha via e-mail ou SMS.  
- Redirecionamento ao perfil após login.

**Regras de Negócio**  
- Apenas pacientes cadastrados podem logar.  
- Cada CPF está vinculado a um único perfil.  
- Informações médicas só são acessadas após autenticação.

### Classes de Equivalência

| Condição de Entrada            | Classes Válidas         | Classes Inválidas                  |
|-------------------------------|--------------------------|------------------------------------|
| Autenticação com CPF e senha  | CPF + senha válidos (1)  | CPF ou senha inválidos (2, 3)      |
| Mensagem de erro              | Mensagem clara (4)       | Ausente (5), genérica (6)          |
| Recuperação de senha          | Via e-mail/SMS (7)       | Não disponível (8)                 |
| Redirecionamento após login   | Perfil do paciente (9)   | Nenhum (10), incorreto (11)        |

### Casos de Teste

| Caso | Classes         | Entrada                               | Resultado Esperado            |
|------|-----------------|----------------------------------------|-------------------------------|
| 1    | 1, 4, 7, 9      | Login com CPF correto, senha correta   | Acesso ao perfil               |
| 2    | 2, 4, 7, 9      | CPF inválido                           | Dados inválidos                |
| 3    | 3, 4, 7, 9      | Campos de login vazios                 | Dados inválidos                |
| 4    | 5, 1, 7, 9      | Login sem exibir erro                  | Dados inválidos                |
| 5    | 6, 1, 7, 9      | Mensagem confusa                       | Dados inválidos                |
| 6    | 8, 1, 4, 9      | Sem opção de recuperação               | Dados inválidos                |
| 7    | 10, 1, 4, 7     | Login sem redirecionamento             | Dados inválidos                |
| 8    | 11, 1, 4, 7     | Login direciona para local errado      | Dados inválidos                |

## H17 – Visualizar quantidade de pacientes agendados para um dia específico (Médico)

**História do Usuário**  
Como médico, quero visualizar a quantidade de pacientes agendados para um dia específico, para que eu possa me organizar melhor e planejar minha rotina de atendimentos.

### Classes de Equivalência

| Nº | Classe                                |
|----|-------------------------------------|
| 1  | Médico autenticado                   |
| 2  | Usuário não autenticado             |
| 3  | Data válida                         |
| 4  | Data inválida ou não selecionada    |
| 5  | Agendamentos pertencentes ao médico |
| 6  | Agendamentos pertencentes a outro médico |

### Casos de Teste

| Caso | Classes    | Entrada                                              | Resultado Esperado                         |
|-------|------------|-----------------------------------------------------|-------------------------------------------|
| 1     | 1, 3, 5    | Médico logado, data válida, agendamentos presentes  | Exibe número correto de pacientes agendados |
| 2     | 2, 3, 5    | Usuário não autenticado, data válida                 | Acesso negado                             |
| 3     | 1, 4, 5    | Médico logado, data inválida ou não selecionada      | Mensagem para selecionar uma data válida |
| 4     | 1, 3, 6    | Médico logado, data válida, agendamentos de outro médico | Mensagem ou erro de acesso não autorizado |
