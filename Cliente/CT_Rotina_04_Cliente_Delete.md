## Cenário 04: Rotina de Cliente (CRUD - Delete).

### Caso de Teste 01: Excluir cliente sem histórico (Positivo).

| ID | Descrição |
| :--- | :--- |
| R04-CT13 | Excluir um cliente recém-cadastrado que não possui histórico de vendas ou financeiro. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Clientes". |
| Existe um cliente (ex: "Cliente Teste") sem vendas, dependentes ou contas a receber. |

| **Passos** |
| :--- |
| **DADO** que o usuário localizou o "Cliente Teste" |
| **E** clica no botão "Excluir" |
| **E** confirma a exclusão na janela pop-up |
| **QUANDO** a operação é confirmada |
| **ENTÃO** o cliente deve ser removido do sistema. |

| **Critérios de aceitação** |
| :--- |
| O cliente não deve mais ser encontrado na busca. |

---

### Caso de Teste 02: Excluir dependente de um cliente (Positivo).

| ID | Descrição |
| :--- | :--- |
| R04-CT14 | Excluir um dependente do cadastro de um cliente. |

| **Pré-condições** |
| :--- |
| O usuário está na guia "Dependentes" de um cliente. |
| Existe um dependente cadastrado (ex: "SILVIA JOSE"). |

| **Passos** |
| :--- |
| **DADO** que o usuário está na guia "Dependentes" |
| **E** seleciona o dependente "SILVIA JOSE" na lista |
| **E** clica no botão "Excluir" (na guia Dependentes, não o principal) |
| **E** confirma a exclusão |
| **QUANDO** a operação é confirmada |
| **ENTÃO** o dependente "SILVIA JOSE" deve ser removido da lista do cliente. |

| **Critérios de aceitação** |
| :--- |
| O dependente não deve mais estar associado ao cliente. |

---

### Caso de Teste 03: Tentar excluir cliente com histórico (Negativo).

| ID | Descrição |
| :--- | :--- |
| R04-CT15 | O sistema não deve permitir a exclusão de um cliente que possua histórico de vendas. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Clientes". |
| O cliente "3 - JOSE SILVA" possui vendas registradas (conforme Rotina 4). |

| **Passos** |
| :--- |
| **DADO** que o usuário localizou o cliente "3 - JOSE SILVA" |
| **E** clica no botão "Excluir" |
| **QUANDO** o usuário confirma a exclusão |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Cliente possui movimentação e não pode ser excluído") |
| **E** o cliente não deve ser removido. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro de integridade referencial deve ser exibida. |
| O cliente deve permanecer no sistema. |

---

### Caso de Teste 04: Tentar excluir cliente com Contas a Receber (Negativo).

| ID | Descrição |
| :--- | :--- |
| R04-CT16 | O sistema não deve permitir a exclusão de um cliente que possua saldo em "Contas a Receber". |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Clientes". |
| O cliente "SILVA JOSE" possui uma dívida registrada em Contas a Receber. |

| **Passos** |
| :--- |
| **DADO** que o usuário localizou o cliente |
| **E** clica no botão "Excluir" |
| **QUANDO** o usuário confirma a exclusão |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Cliente possui pendências financeiras") |
| **E** o cliente não deve ser removido. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve impedir a exclusão de clientes com saldo devedor. |