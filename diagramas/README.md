**Documento de Especificação de Software**

Sistema de Agendamento de Consultas Comunitárias

**1\. Tabela de Controle de Versões**

| Versão | Data | Autor | Descrição |
| :---: | :---: | :---: | :---: |
|  1.0 |  24/06/2025 | Edilson Gomes Franciele Fernandes Welen Almeida |  Versão inicial do documento |

**2\. Introdução**

Este projeto visa oferecer uma solução digital acessível para o agendamento de consultas em comunidades, eliminando filas físicas, priorizando organização e promovendo inclusão.

**3\. Mini-Mundo**

As unidades de saúde enfrentam uma série de dificuldades que comprometem a qualidade do atendimento. Filas extensas se formavam ainda de madrugada, forçando pacientes — muitos deles idosos ou em situação de vulnerabilidade — a enfrentarem horas de espera em ambientes muitas vezes desconfortáveis. O processo de agendamento era burocrático, feito presencialmente e sujeito a falhas humanas, o que frequentemente resultava em marcações perdidas ou mal registradas. Havia também uma grande falta de transparência: os pacientes desconheciam sua posição na fila e não sabiam quando ou se seriam atendidos.

Diante desse cenário, o novo sistema de agendamento digital foi desenvolvido como uma solução moderna e eficiente. Agora, pacientes acessam o aplicativo ou site, escolhem horários disponíveis e realizam agendamentos sem sair de casa. O sistema considera critérios de prioridade, permite cancelamentos e remarcações rápidas, e envia lembretes automáticos das consultas. No dia do atendimento, o check-in é feito online, eliminando as filas físicas e proporcionando uma jornada mais organizada.

Médicos acessam prontuários digitais atualizados, registram evoluções clínicas e mantêm um histórico completo de cada paciente. A equipe administrativa acompanha todos os fluxos em tempo real, gerencia agendas com precisão e garante o cumprimento das regras de atendimento. Representantes legais também têm acesso autorizado para agendar em nome de pacientes que necessitam de apoio.

O resultado é uma experiência de saúde mais humana, eficiente e acessível, construída para atender às reais necessidades da população e superar os entraves do modelo tradicional.

**4\. Requisitos Funcionais**

Lista numerada de funcionalidades que o sistema deverá realizar.

| Cód. | Requisito Funcional |
| ----- | ----- |
| RF01 | O sistema deve permitir o agendamento de consultas por pacientes ou representantes. |
| RF02 | O sistema deve permitir o cancelamento e a remarcação de consultas. |
| RF03 | O sistema deve disponibilizar busca em tempo real por horários disponíveis. |
| RF04 | O sistema deve permitir a visualização da agenda por pacientes, médicos e agentes. |
| RF05 | O sistema deve registrar e permitir a atualização de informações dos pacientes. |
| RF06 | O sistema deve definir e aplicar critérios de prioridade nos agendamentos. |
| RF07 | O sistema deve enviar notificações automáticas via WhatsApp e sistema interno. |
| RF08 | O sistema deve permitir check-in online para confirmação de presença. |
| RF09 | O sistema deve registrar e disponibilizar prontuários eletrônicos para médicos. |
| RF10 | O sistema deve organizar e monitorar a posição dos pacientes na fila de espera. |
| RF11 | O sistema deve permitir que representantes ou agentes de saúde realizem agendamentos em nome de pacientes. |
| RF12 | O sistema deve registrar as ações do administrativo (confirmação, cancelamento, ajuste de prioridade). |

### 

**5\. Requisitos Não Funcionais**

Aspectos como desempenho, segurança, usabilidade, etc.

| Cód. | Requisito Não Funcional |
| ----- | ----- |
| RNF01 | O sistema deve garantir a segurança dos dados com backups automáticos. |
| RNF02 | O sistema deve ser altamente confiável, sem falhas durante horários críticos. |
| RNF03 | O sistema deve apresentar alta performance, com buscas e confirmações em tempo real. |
| RNF04 | A interface deve ser amigável e acessível para usuários com baixa familiaridade digital. |
| RNF05 | O sistema deve estar preparado para uso em dispositivos móveis e computadores. |
| RNF06 | O sistema deve integrar-se com a API do WhatsApp para envio de notificações. |
| RNF07 | O sistema deve permitir registros manuais por agentes comunitários. |
| RNF08 | O sistema deve respeitar os critérios de prioridade baseados em urgência e perfil médico. |
| RNF09 | O sistema deve limitar o número de consultas por paciente, com base na capacidade do serviço. |

**6\. Regras de Negócio**

Regras específicas que não se enquadram como requisitos funcionais:

| Cód. | Regras de Negócios |
| ----- | ----- |
| RN01 | O sistema **não** deve realizar diagnósticos ou prescrições médicas. |
| RN02 | O sistema **não** deve permitir agendamentos sem validação da disponibilidade. |
| RN03 | O sistema **não** deve fazer controle de pagamentos ou faturamentos. |
| RN04 | O sistema **não** deve atender casos de urgência ou emergência. |
| RN05 | O sistema **não** terá integração com sistemas externos. |
| RN06 | O sistema **não** exigirá acesso direto apenas pelo paciente (representantes podem usar). |

### 

**7\. Modelo Entidade-Relacionamento (MER)**

![MER.png](https://github.com/Sistema-de-agendamento-de-consultas/documentos/blob/main/diagramas/MER.png)

**8\. Casos de Uso**

![Caso_de_Uso.png](https://github.com/Sistema-de-agendamento-de-consultas/documentos/blob/main/diagramas/Caso_de_Uso.png)  

---

### **Caso de Uso descritivo**  
### **Agendar de Consultas (RF01, RF11)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Paciente, Representante, Agente                                           |
| **Pré-condições**    | Usuário autenticado no sistema                                            |
| **Fluxo Principal**  | Usuário seleciona especialidade, médico e horário disponível              |
| **Pós-condições**    | Consulta agendada com prioridade definida, se aplicável                   |
| **Regras Aplicáveis**| RN02 (validação de disponibilidade), RN06 (representantes podem agendar)  |

---

### **Cancelar e Remarcar Consultas (RF02)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Paciente, Representante, Agente                                           |
| **Pré-condições**    | Consulta previamente agendada                                             |
| **Fluxo Principal**  | Usuário acessa a agenda, escolhe cancelar ou remarcar                    |
| **Pós-condições**    | Consulta é reagendada ou cancelada                                       |
| **Regras Aplicáveis**| RN02, RN06                                                                |

---

### **Buscar Horários Disponíveis (RF03)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Paciente, Representante, Agente                                           |
| **Pré-condições**    | Autenticação no sistema                                                   |
| **Fluxo Principal**  | Usuário informa especialidade, sistema retorna horários válidos           |
| **Pós-condições**    | Lista de horários disponíveis exibida                                     |
| **Regras Aplicáveis**| RN02                                                                      |

---

### **Visualizar Agenda (RF04)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Paciente, Médico, Agente                                                  |
| **Pré-condições**    | Autenticação e permissão adequada                                         |
| **Fluxo Principal**  | Acesso à agenda pessoal conforme o perfil                                 |
| **Pós-condições**    | Agenda visualizada com informações permitidas                             |
| **Regras Aplicáveis**| RN01, RN02                                                                |

---

### **Registrar/Atualizar Informações dos Pacientes (RF05)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Paciente, Agente                                                          |
| **Pré-condições**    | Identificação do paciente                                                 |
| **Fluxo Principal**  | Preenchimento ou atualização de dados                                     |
| **Pós-condições**    | Dados atualizados com segurança                                           |
| **Regras Aplicáveis**| RN05, RNF01                                                               |

---

### **Definir Prioridades no Agendamento (RF06)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Administrativo                                                           |
| **Pré-condições**    | Consulta pendente de confirmação                                          |
| **Fluxo Principal**  | Sistema aplica regras baseadas em urgência e perfil                       |
| **Pós-condições**    | Ordem de atendimento ajustada                                             |
| **Regras Aplicáveis**| RNF08, RN04                                                               |

---

### **Enviar Notificações (RF07)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Sistema                                                                  |
| **Pré-condições**    | Consulta agendada ou alterada                                             |
| **Fluxo Principal**  | Disparo automático via WhatsApp e sistema interno                         |
| **Pós-condições**    | Notificação enviada                                                       |
| **Regras Aplicáveis**| RNF06, RN05                                                               |

---

### **Check-in Online (RF08)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Paciente                                                                 |
| **Pré-condições**    | Agendamento confirmado                                                    |
| **Fluxo Principal**  | Paciente acessa sistema e confirma presença                               |
| **Pós-condições**    | Presença registrada                                                       |
| **Regras Aplicáveis**| RN02, RN04                                                                |

---

### **Visualizar Prontuários (RF09)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Médico                                                                    |
| **Pré-condições**    | Consulta realizada                                                        |
| **Fluxo Principal**  | Médico acessa e registra informações no prontuário                        |
| **Pós-condições**    | Dados disponíveis para consultas futuras                                  |
| **Regras Aplicáveis**| RN01 (sem diagnósticos automáticos), RN05                                |

---

### **Gerenciar Fila de Espera / Definir Prioridades (RF10)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Administrativo                                                           |
| **Pré-condições**    | Excesso de agendamentos                                                   |
| **Fluxo Principal**  | Sistema posiciona paciente conforme prioridade                            |
| **Pós-condições**    | Paciente posicionado na fila                                              |
| **Regras Aplicáveis**| RN04, RNF08                                                               |

---

### **Realizar Ações Administrativas (RF12)**

| Item                  | Descrição                                                                 |
|-----------------------|--------------------------------------------------------------------------|
| **Atores**           | Administrativo                                                           |
| **Pré-condições**    | Consulta existente                                                        |
| **Fluxo Principal**  | Confirmar, cancelar ou alterar prioridade                                 |
| **Pós-condições**    | Registro atualizado                                                       |
| **Regras Aplicáveis**| RN03, RN05                                                                |

---

**9\. Diagrama de Pacotes**

![Pacotes.png](https://github.com/Sistema-de-agendamento-de-consultas/documentos/blob/main/diagramas/Pacotes.png).

**10\. Diagrama de Classes**

![Classe.png](https://github.com/Sistema-de-agendamento-de-consultas/documentos/blob/main/diagramas/Classe.png)

**11\. Diagrama de Objetos**

![][image4]

**12\. Fluxograma**

![Objetos.png](https://github.com/Sistema-de-agendamento-de-consultas/documentos/blob/main/diagramas/Objetos.png)

**13\. Diagrama de Sequência**

![sequencia.png](https://github.com/Sistema-de-agendamento-de-consultas/documentos/blob/main/diagramas/sequencia.png)
