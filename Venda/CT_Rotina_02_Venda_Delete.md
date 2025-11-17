## Cenário 02: Rotina de Venda (CRUD - Delete).

### Caso de Teste 01: Excluir item de uma venda não confirmada (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT14 | O usuário remove um produto de uma venda que foi salva mas ainda não finalizada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "NÃO CONFIRMADA" (ex: Número "5") com pelo menos dois itens. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda "5" ("NÃO CONFIRMADA") |
| **E** seleciona um item na lista "Entrada de Produtos" |
| **E** clica no botão "Excluir" na seção "Entrada de Produtos" [cite: 953] |
| **E** confirma a exclusão (se solicitado) |
| **QUANDO** a operação é confirmada |
| **ENTÃO** o item deve desaparecer da lista |
| **E** o "Sub-Total", "Número de Itens" e "Quantidade Total" da venda devem ser recalculados. |

| **Critérios de aceitação** |
| :--- |
| O item deve ser removido da lista da venda. |
| O valor total da venda deve ser atualizado (reduzido). |

---

### Caso de Teste 02: Excluir (cancelar) uma venda não confirmada (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT15 | O usuário cancela/exclui uma venda inteira que foi registrada mas ainda não foi finalizada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "NÃO CONFIRMADA" (ex: Número "5") salva no sistema[cite: 941]. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda "5" ("NÃO CONFIRMADA") |
| **E** clica no botão "Excluir" (na barra de ferramentas principal, ao lado de "Alterar") [cite: 915] |
| **E** confirma a exclusão na janela pop-up |
| **QUANDO** a operação é confirmada |
| **ENTÃO** a venda "5" deve ser removida do sistema |
| **E** não deve haver impacto no estoque ou no caixa. |

| **Critérios de aceitação** |
| :--- |
| A venda não deve mais ser encontrada no sistema. |
| O estoque dos produtos que estavam na venda não deve ser alterado (pois nunca foi debitado). |

---

### Caso de Teste 03: Tentar excluir (cancelar) uma venda confirmada (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT16 | O sistema não deve permitir a exclusão de uma venda confirmada (o fluxo correto seria uma Devolução). |

| **Pré-condições** |
| :--- |
| Existe uma venda "CONFIRMADA" (ex: Número "5") salva no sistema[cite: 1210]. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda "5" ("CONFIRMADA") |
| **QUANDO** o usuário clica no botão "Excluir" (na barra de ferramentas principal) [cite: 1215] |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Venda confirmada não pode ser excluída. Use Devolução.") |
| **OU** o botão "Excluir" deve estar desabilitado[cite: 1215]. |

| **Critérios de aceitação** |
| :--- |
| A venda "5" deve permanecer no sistema. |
| O estoque e o caixa não devem sofrer alterações. |

---

### Caso de Teste 04: Tentar excluir item de uma venda confirmada (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT17 | O sistema não deve permitir a exclusão de um item de uma venda já confirmada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "CONFIRMADA" (ex: Número "5") salva no sistema[cite: 1210]. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda "5" ("CONFIRMADA") |
| **E** seleciona um item na lista de produtos |
| **QUANDO** o usuário clica no botão "Excluir" (na seção "Entrada de Produtos") [cite: 1228] |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Venda confirmada, não pode alterar itens") |
| **OU** o botão "Excluir" (dos itens) deve estar desabilitado[cite: 1228]. |

| **Critérios de aceitação** |
| :--- |
| O item não deve ser removido da venda. |
| A venda "5" deve permanecer inalterada. |