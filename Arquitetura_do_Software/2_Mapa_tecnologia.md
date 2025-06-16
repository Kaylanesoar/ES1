# Mapa de Tecnologia

## O que é um Mapa de Tecnologia

Um **Mapa de Tecnologia** é uma representação visual das tecnologias e ferramentas utilizadas no desenvolvimento de um sistema ou aplicação. Ele organiza os componentes do projeto em camadas (frontend, backend, banco de dados, etc.) ou de acordo com suas funções dentro da solução, permitindo uma visão clara das interdependências e do fluxo de informações.

---

## Legenda e Estrutura do Mapa de Tecnologias

No projeto **UBS Digital**, o **Tech Stack Map** foi criado para ilustrar as tecnologias utilizadas e como elas interagem para atender às funcionalidades de gestão de consultas e medicamentos. A estrutura está organizada nas seguintes camadas:

* **Frontend:** Refere-se à parte da aplicação com a qual o usuário interage diretamente (interface do usuário).
* **Backend (API):** Trata da lógica de negócios, do processamento de dados e da comunicação com o banco de dados, geralmente expondo uma API (Interface de Programação de Aplicações) para o frontend.
* **Banco de Dados:** Sistemas responsáveis por armazenar, organizar e recuperar os dados da aplicação.
* **Autenticação:** Serviços ou métodos para verificar a identidade dos usuários.
* **Serviços Auxiliares & Comunicação:** Tecnologias que fornecem funcionalidades adicionais ou facilitam a interação com serviços externos.
* **DevOps/CI/CD (Controle de Versão / Documentação e Gestão):** Ferramentas e práticas para automação de processos de desenvolvimento, integração contínua, entrega contínua, controle de código-fonte e gestão de projetos.

---

## Mapa de Tecnologia

<div align="center">

  <img src="https://github.com/user-attachments/assets/e4645a76-3c69-4e35-a405-5e79a2c7b405" width="700px" alt="Descrição da imagem">
</div>

### Tabela Descritiva

A seguir, apresentamos a tabela de tecnologias utilizadas no desenvolvimento do Sistema de Gestão de UBS, organizadas conforme sua função dentro da arquitetura do sistema. Cada tecnologia foi escolhida com base em critérios como compatibilidade com a proposta do projeto, facilidade de uso, suporte da comunidade e adequação ao contexto de um sistema de saúde.

## Tabela Descritiva do Stack de Tecnologia

A seguir, apresentamos a tabela de tecnologias propostas para o desenvolvimento do sistema, organizadas conforme sua função dentro da arquitetura. Cada tecnologia foi selecionada considerando sua adequação, performance e benefícios para o projeto.

| Camada            | Tecnologia         | Justificativa                                                                                                                                                                                                                                                                                             |
| :------------------------ | :------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Frontend (Mobile)** | Thunkable                       | Plataforma visual (low-code) que permite desenvolver apps mobile de forma rápida, sem exigir conhecimento avançado em programação. Ideal para MVPs e sistemas públicos.                                                                                                                                       |
| **Backend - API** | Node.js + Express               | Plataforma leve, moderna e baseada em JavaScript. Ideal para criar APIs RESTful com alta produtividade e fácil manutenção.                                                                                                                                                                                |
| **Banco de Dados** | PostgreSQL                      | Banco relacional robusto, seguro, com suporte a SQL e ótimo para integridade de dados em sistemas críticos de saúde.                                                                                                                                                                                          |
| **Banco de Dados** | Firebird                        | Alternativa leve e tradicional, com uso consolidado em ambientes com poucos recursos e sistemas locais.                                                                                                                                                                                                  |
| **Banco de Dados (Cache)**| Redis                           | Armazenamento em memória para cache de dados temporários, melhorando o tempo de resposta em consultas frequentes (ex: horários disponíveis).                                                                                                                                                               |
| **Autenticação** | Firebase Authentication         | Solução moderna e segura para autenticação de usuários. Suporta login via e-mail, redes sociais, com boa integração mobile/web.                                                                                                                                                                         |
| **Serviços Auxiliares** | Google Maps API                 | Permite exibir mapas e localizar UBS mais próximas. Útil para visualização geográfica e cálculo de rotas.                                                                                                                                                                                                |
| **Serviços Auxiliares** | Notificações por SMS / Email    | Ferramenta complementar para comunicação direta com pacientes via e-mail ou SMS.                                                                                                                                                                                                                         |
| **Controle de Versão** | GitHub                          | Plataforma amplamente usada para versionamento de código, integração com equipes e colaboração em tempo real.                                                                                                                                                                                           |
| **Documentação e Gestão** | Notion + GitHub Projects        | Ferramentas de produtividade para organização ágil de tarefas, backlog, dailys e documentação técnica acessível.                                                                                                                                                                                        |
| Notion + GitHub                       | DevOps/CI/CD (Documentação e Gestão) | Ferramentas para planejamento ágil com sprints, backlog e dailys documentadas.                                                                                                                                                                                                      |
