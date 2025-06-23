# 🏥 Sistema de Agendamento de Consultas Comunitárias

Este projeto visa oferecer uma solução digital acessível para o agendamento de consultas em comunidades, eliminando filas físicas, priorizando organização e promovendo inclusão.

Abaixo estão os **principais diagramas UML e ER** utilizados para documentar a estrutura e comportamento do sistema.

---

## 📘 Diagramas do Projeto

### 1. 🧱 Diagrama de Classes com Métodos (PlantUML)

Representa a estrutura de classes do sistema, incluindo **atributos** e **métodos públicos** essenciais de cada entidade. Esse diagrama é útil para desenvolvedores entenderem as **responsabilidades e ações permitidas** por cada classe.

#### Exemplos de métodos incluídos:
- `Paciente.solicitarConsulta()`
- `Consulta.confirmar()`
- `Fila.atualizarPosicao()`
- `Notificacao.enviar()`

> ⚙️ Arquivo: `MER.puml`  
> 🖼 Geração recomendada: [plantuml.com](https://www.plantuml.com/plantuml/)

---

### 2. 🗃️ Diagrama Entidade-Relacionamento (ERD - PlantUML)

Apresenta as entidades e seus relacionamentos no banco de dados. Ideal para orientar a modelagem relacional da base de dados.

#### Destaques:
- Um representante pode agendar para vários pacientes  
- Uma consulta está ligada a um paciente, profissional e prontuário  
- Prontuários são registrados após cada atendimento

> ⚙️ Arquivo: `MER.puml`

---

### 3. 🖼 Diagrama de Classes (Graphviz - PNG)

Versão visual do diagrama de classes básica, útil para apresentações e documentação técnica. Contém os atributos principais e os relacionamentos entre classes.

> 📷 Arquivo gerado: `Classe.png`

---


## 🧩 Estrutura de Arquivos Sugerida

```plaintext
/docs
  ├─ diagramas/
  │   ├─ Classe.puml
  │   ├─ MER.puml

