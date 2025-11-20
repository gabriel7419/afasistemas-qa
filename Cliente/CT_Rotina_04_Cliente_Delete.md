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

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE**
[https://drive.google.com/file/d/15JSBbEgYwtT8Vv6gCcsuNN4zW-yGw_X7/view?usp=drive_link]

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

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE**
[https://drive.google.com/file/d/1XEL0Y387b3l3YF2QZwG2lIGgpAq038Hi/view?usp=sharing]


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

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE**
[https://drive.google.com/file/d/1tioB-QMmxYxCJALWrRGqKBIsVpyZeFUF/view?usp=sharing]

---