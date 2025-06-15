# Rastreabilidade  – Plataforma Digital das UBS

## Descrição

A rastreabilidade de requisitos é uma prática fundamental na Engenharia de Software, permitindo o acompanhamento do ciclo de vida de cada requisito, desde sua definição até a sua implementação, testes e manutenção.

No contexto da Plataforma Digital das UBS, este documento apresenta uma matriz de rastreabilidade, relacionando diretamente:

- As histórias de usuário levantadas na fase de especificação
- Os módulos/componentes do sistema responsáveis por atender aos requisitos
- As respectivas rotas de API/backend
- As entidades/tabelas utilizadas na persistência
- Os testes funcionais e técnicos associados à verificação de cada requisito

Essa rastreabilidade garante que:

- Cada requisito possui cobertura técnica e funcional
- As funcionalidades desenvolvidas podem ser validadas com clareza
- É possível manter controle sobre impactos de mudanças
- Existe transparência entre cliente, equipe de desenvolvimento e QA

O modelo adotado se baseia em boas práticas de documentação ágil e serve como instrumento de auditoria, validação de requisitos e acompanhamento de testes durante o ciclo de desenvolvimento.


| ID     | História de Usuário                                                                      | Módulo / Componente             | API / Backend              | Persistência          | Testes Relacionados                |
|--------|--------------------------------------------------------------------------------------------|----------------------------------|-----------------------------|------------------------|------------------------------------|
| #17    | Médico visualiza quantidade de pacientes agendados por data                               | Módulo de Agenda Médica          | /agenda/medico             | Tabela `agendamentos`  | Teste de filtro e autenticação    |
| #16    | Paciente consulta disponibilidade de medicamento                                           | Módulo de Medicamentos           | /medicamentos/disponiveis  | Tabela `medicamentos`  | Teste de busca e atualização      |
| #15    | Paciente agenda exame e recebe notificação                                                 | Módulo de Agendamento            | /agendamentos              | Tabela `agendamentos`  | Teste de criação e notificação    |
| #10    | Agente registra entrega de medicamentos durante visitas                                   | Módulo de Registro de Entregas   | /entregas                  | Tabela `entregas`      | Teste de validação e estoque      |
| #9     | Paciente visualiza calendário de campanhas de vacinação                                    | Módulo de Campanhas              | /campanhas                 | Tabela `campanhas`     | Teste de exibição por data/tipo   |
| -      | Autenticação de usuários                                                                   | Thunkable Auth / Firebase        | Middleware de login        | -                      | Teste de autenticação (JWT)       |
| -      | Notificações automáticas                                                                   | Sistema de Notificação Push      | Backend → Notificação      | -                      | Teste de disparo de notificação   |
| -      | Verificação de cadastro de paciente                                                        | Sistema de Cadastro da UBS       | /paciente/verificar        | -                      | Teste de resposta de integração   |

