# Mapa de Tecnologia

## O que é um Mapa de Tecnologia

Um **Mapa de Tecnologia** é uma representação visual das tecnologias e ferramentas utilizadas no desenvolvimento de um sistema ou aplicação. Ele organiza os componentes do projeto em camadas (frontend, backend, banco de dados, etc.) ou de acordo com suas funções dentro da solução, permitindo uma visão clara das interdependências e do fluxo de informações.

---

## Legenda e Estrutura do Mapa de Tecnologias

No projeto **UBS Conecta**, o **Tech Stack Map** foi criado para ilustrar as tecnologias utilizadas e como elas interagem para atender às funcionalidades de gestão de consultas e medicamentos. A estrutura está organizada nas seguintes camadas:

* **Frontend:** Refere-se à parte da aplicação com a qual o usuário interage diretamente (interface do usuário).
* **Backend (API):** Trata da lógica de negócios, do processamento de dados e da comunicação com o banco de dados, geralmente expondo uma API (Interface de Programação de Aplicações) para o frontend.
* **Banco de Dados:** Sistemas responsáveis por armazenar, organizar e recuperar os dados da aplicação.
* **Autenticação:** Serviços ou métodos para verificar a identidade dos usuários.
* **Serviços Auxiliares & Comunicação:** Tecnologias que fornecem funcionalidades adicionais ou facilitam a interação com serviços externos.
* **DevOps/CI/CD (Controle de Versão / Documentação e Gestão):** Ferramentas e práticas para automação de processos de desenvolvimento, integração contínua, entrega contínua, controle de código-fonte e gestão de projetos.

---

## Mapa de Tecnologia

<div align="center">

  <img src="https://github.com/user-attachments/assets/3bc24658-2b67-4b64-804d-e980481d95ee" width="700px" alt="Descrição da imagem">
</div>

### Tabela Descritiva

A seguir, apresentamos a tabela de tecnologias utilizadas no desenvolvimento do Sistema de Gestão de UBS, organizadas conforme sua função dentro da arquitetura do sistema. Cada tecnologia foi escolhida com base em critérios como compatibilidade com a proposta do projeto, facilidade de uso, suporte da comunidade e adequação ao contexto de um sistema de saúde.

| Tecnologia                            | Camada                              | Justificativa                                                                                                                                                                                                                                                                                            |
| :------------------------------------ | :---------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Java (com Vaadin GWT ou JavaFX)       | Frontend                            | Vaadin / GWT (Google Web Toolkit): Permitem desenvolver interfaces web ricas e interativas usando apenas Java. O código Java é transpilado para JavaScript, HTML e CSS para rodar no navegador, permitindo que a equipe trabalhe puramente em Java. JavaFX: Para a construção de aplicações desktop nativas e modernas em Java, caso o frontend seja uma aplicação de desktop e não web. |
| Java (com Spring Boot)                | Backend (API)                       | Java: Linguagem robusta, madura e amplamente utilizada em sistemas corporativos e de saúde, conhecida por sua performance e escalabilidade. Spring Boot: Framework líder em Java, que acelera o desenvolvimento de APIs RESTful e microserviços, garantindo estabilidade, segurança e um grande ecossistema de bibliotecas. Ideal para sistemas críticos como o da UBS. |
| Firebird                              | Banco de Dados                      | Banco de dados relacional leve, de código aberto, ideal para aplicações que exigem um banco de dados embarcável ou para uso em cenários de pequeno a médio porte, como sistemas desktop ou soluções locais.                                                                                    |
| PostgreSQL                            | Banco de Dados                      | Banco de dados relacional robusto, opensource e ideal para sistemas com múltiplas entidades e dados sensíveis de saúde (pacientes, histórico, medicamentos), garantindo integridade e conformidade.                                                                                              |
| Redis (cache)                         | Banco de Dados                      | Banco de dados em memória de alta performance, utilizado para caching de dados frequentemente acessados (ex: disponibilidade de horários), acelerando a resposta do sistema.                                                                                                        |
| Firebase Authentication               | Autenticação                        | Fácil de integrar, confiável, oferece login via e-mail, Google, redes sociais, etc.                                                                                                                                                                                                  |
| Integração de Mapas (Google Maps API) | Serviços Auxiliares & Comunicação | Para a funcionalidade de localizar a UBS mais próxima, permitindo exibir no mapa e traçar rotas.                                                                                                                                                                                      |
| GitHub                                | DevOps/CI/CD (Controle de Versão)   | Versionamento colaborativo e documentação em repositório remoto, garantindo rastreabilidade e colaboração.                                                                                                                                                                            |
| Notion + GitHub                       | DevOps/CI/CD (Documentação e Gestão) | Ferramentas para planejamento ágil com sprints, backlog e dailys documentadas.                                                                                                                                                                                                      |
