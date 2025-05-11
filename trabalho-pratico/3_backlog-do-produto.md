# **Histórias Especificadas (10)**
---
### **1. \[Paciente] Localizar UBS mais próxima**

**História:**
Como paciente, quero localizar a UBS mais próxima da minha residência, para poder buscar atendimento com mais praticidade.

**Critérios de Aceitação:**

* O sistema deve identificar a localização atual do usuário.
* O sistema deve listar as UBSs ordenadas por distância.
* Deve haver botão “Como chegar” com integração ao Google Maps.

**Regras de Negócio:**

* Exibir apenas UBSs com status “Ativa”.
* A localização deve ser pedida apenas com permissão do usuário.

**Assignees:** João, Maria, Pedro

---

### **2. \[Paciente] Agendar consulta com médico**

**História:**
Como paciente, quero agendar consultas com médicos da UBS para garantir meu atendimento.

**Critérios de Aceitação:**

* O paciente deve selecionar especialidade, data e hora disponíveis.
* O sistema deve confirmar o agendamento via notificação.

**Regras de Negócio:**

* Só é possível um agendamento ativo por especialidade.
* Datas passadas não devem ser exibidas.

**Assignees:** Ana, João

---

### **3. \[Médico] Visualizar agenda de atendimentos**

**História:**
Como médico, quero visualizar meus atendimentos agendados para planejar meu dia de trabalho.

**Critérios de Aceitação:**

* Mostrar lista por data/hora e paciente.
* Permitir filtro por dia ou semana.

**Regras de Negócio:**

* Apenas médicos logados podem ver a própria agenda.
* Exibir nome e número do cartão SUS do paciente.

**Assignees:** Pedro, Maria

---

### **4. \[Agente de saúde] Cadastrar estoque de medicamentos**

**História:**
Como agente de saúde, quero cadastrar a quantidade disponível de medicamentos para controle interno e aviso à população.

**Critérios de Aceitação:**

* Campo para nome do medicamento, lote e quantidade.
* Atualização de estoque refletida em tempo real.

**Regras de Negócio:**

* Apenas agentes logados podem editar.
* Não permitir quantidades negativas.

**Assignees:** João, Ana

---

### **5. \[Paciente] Consultar disponibilidade de medicamentos**

**História:**
Como paciente, quero consultar se um medicamento está disponível antes de me deslocar até a UBS.

**Critérios de Aceitação:**

* Campo de busca por nome do medicamento.
* Exibir quantidade disponível e local.

**Regras de Negócio:**

* Apenas medicamentos com quantidade > 0 são exibidos.
* Atualização a cada 5 minutos no app.

**Assignees:** Pedro, João

---

### **6. \[Paciente] Receber notificações de campanhas de saúde**

**História:**
Como paciente, quero receber avisos sobre campanhas de vacinação e prevenção para me manter informado.

**Critérios de Aceitação:**

* Exibir notificações push e no app.
* Listar campanhas com título, descrição e datas.

**Regras de Negócio:**

* Campanhas expiradas devem ser arquivadas.
* Notificações ativadas apenas se o paciente permitir.

**Assignees:** Maria, Ana

---

### **7. \[Agente de saúde] Criar campanhas de saúde**

**História:**
Como agente, quero cadastrar campanhas de saúde para informar a população da área de cobertura.

**Critérios de Aceitação:**

* Inserir título, descrição, data, UBS envolvida.
* Possibilidade de anexar banner/imagem.

**Regras de Negócio:**

* Não permitir campanhas com data de término anterior à atual.
* Apenas agentes logados podem criar campanhas.

**Assignees:** João, Pedro

---

### **8. \[Médico] Atualizar prontuário eletrônico do paciente**

**História:**
Como médico, quero registrar informações do atendimento no prontuário eletrônico para manter o histórico médico atualizado.

**Critérios de Aceitação:**

* Permitir adicionar sintomas, diagnóstico e conduta.
* Histórico deve ser visível em consultas futuras.

**Regras de Negócio:**

* Apenas médicos logados podem editar.
* Campos obrigatórios: data, diagnóstico e conduta.

**Assignees:** Ana, Maria

---

### **9. \[Paciente] Consultar histórico de consultas**

**História:**
Como paciente, quero consultar meu histórico de consultas para acompanhar meu tratamento.

**Critérios de Aceitação:**

* Mostrar lista com data, especialidade e médico.
* Permitir download em PDF.

**Regras de Negócio:**

* Histórico só acessível com login do paciente.
* Mostrar apenas consultas realizadas.

**Assignees:** Pedro, Ana

---

### **10. \[Agente de saúde] Gerar relatórios de atendimentos**

**História:**
Como agente, quero gerar relatórios de atendimentos por UBS para análise de desempenho.

**Critérios de Aceitação:**

* Permitir filtros por período e tipo de atendimento.
* Exportar em PDF e Excel.

**Regras de Negócio:**

* Acesso restrito a agentes e gestores.
* Dados devem ser anonimizados.

**Assignees:** João, Pedro

---

###  **Histórias Não Especificadas (5)**

(Estas vão para a coluna **Backlog**)

11. **\[Paciente] Editar dados do perfil**
12. **\[Médico] Visualizar histórico do paciente antes da consulta**
13. **\[Paciente] Receber lembretes de consulta agendada**
14. **\[Agente de saúde] Gerenciar equipe de campo**
15. **\[Médico] Solicitar exames laboratoriais pelo sistema**

---

