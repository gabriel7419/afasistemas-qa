## Cenário 03: Rotina de Compra (CRUD - Delete).

### Caso de Teste 01: Excluir fornecedor sem vínculos (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT13 | Excluir um fornecedor que não possui pedidos de compra vinculados. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Fornecedores". |
| Existe um fornecedor cadastrado (ex: "Fornecedor Teste") sem histórico de compras. |

| **Passos** |
| :--- |
| **DADO** que o usuário localizou o "Fornecedor Teste" |
| **E** clica no botão "Excluir" |
| **E** confirma a exclusão na janela pop-up |
| **QUANDO** a operação é confirmada |
| **ENTÃO** o fornecedor deve ser removido do sistema. |

| **Critérios de aceitação** |
| :--- |
| O fornecedor não deve mais ser encontrado na busca. |

---

### Caso de Teste 02: Excluir pedido de compra não confirmado (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT14 | Cancelar (excluir) um pedido de compra que ainda está "NÃO CONFIRMADA". |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Compra". |
| Existe um pedido de compra "NÃO CONFIRMADA". |

| **Passos** |
| :--- |
| **DADO** que o usuário localizou o pedido de compra "NÃO CONFIRMADA" |
| **E** clica no botão "Excluir" |
| **E** confirma a exclusão na janela pop-up |
| **QUANDO** a operação é confirmada |
| **ENTÃO** o pedido de compra deve ser removido do sistema |
| **E** nenhum lançamento de estoque ou financeiro deve ocorrer. |

| **Critérios de aceitação** |
| :--- |
| O pedido de compra deve ser excluído do banco de dados. |

---

### Caso de Teste 03: Tentar excluir fornecedor com vínculo (Negativo).

| ID | Descrição |
| :--- | :--- |
| R03-CT15 | O sistema não deve permitir a exclusão de um fornecedor que possua pedidos de compra (histórico). |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Fornecedores". |
| O fornecedor "7 - TONY RAMOS PELES LTDA" possui um pedido de compra vinculado. |

| **Passos** |
| :--- |
| **DADO** que o usuário localizou o fornecedor "7" |
| **E** clica no botão "Excluir"   |
| **QUANDO** o usuário confirma a exclusão |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Fornecedor possui movimentação e não pode ser excluído") |
| **E** o fornecedor não deve ser removido. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro de integridade referencial deve ser exibida. |
| O fornecedor deve permanecer no sistema. |

---

### Caso de Teste 04: Tentar excluir pedido de compra confirmado (Negativo).

| ID | Descrição |
| :--- | :--- |
| R03-CT16 | O sistema não deve permitir a exclusão de um pedido de compra que já foi "CONFIRMADO". |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Compra". |
| Existe um pedido de compra com status "CONFIRMADA". |

| **Passos** |
| :--- |
| **DADO** que o usuário localizou o pedido de compra "CONFIRMADA" |
| **QUANDO** o usuário clica no botão "Excluir" |
| **ENTÃO** o botão deve estar desabilitado |
| **OU** o sistema deve exibir uma mensagem de erro (ex: "Compra confirmada não pode ser excluída"). |

| **Critérios de aceitação** |
| :--- |
| O pedido de compra deve permanecer no sistema. |
| O estoque e o "Contas a Pagar" não devem ser afetados. |