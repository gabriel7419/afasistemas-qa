## Cenário 02: Rotina de Venda (CRUD - Update).

### Caso de Teste 01: Adicionar item a uma venda não confirmada (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT10 | O usuário adiciona um novo produto a uma venda que foi salva mas ainda não finalizada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "NÃO CONFIRMADA" (ex: Número "5") salva no sistema[cite: 941]. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda "5" ("NÃO CONFIRMADA") |
| **E** clica no botão "Novo" na seção "Entrada de Produtos" [cite: 912, 947] |
| **E** adiciona um novo produto e clica em "Salvar" [cite: 887] |
| **QUANDO** o usuário retorna à tela principal da Venda "5" [cite: 911] |
| **ENTÃO** o novo produto deve estar listado junto aos anteriores |
| **E** o "Sub-Total", "Número de Itens" e "Quantidade Total" da venda devem ser recalculados[cite: 943, 958]. |

| **Critérios de aceitação** |
| :--- |
| O novo item deve aparecer na lista de produtos da venda. |
| O valor total da venda deve ser atualizado. |

---

### Caso de Teste 02: Alterar quantidade de um item em venda não confirmada (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT11 | O usuário altera a quantidade de um item em uma venda que ainda não foi finalizada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "NÃO CONFIRMADA" (ex: Número "5") com pelo menos um item. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda "5" ("NÃO CONFIRMADA") |
| **E** seleciona o item que deseja alterar na lista |
| **E** clica no botão "Alterar" na seção "Entrada de Produtos" [cite: 948] |
| **E** na tela "Entrada de Produtos para Venda", muda o campo "Quant." [cite: 891] |
| **E** clica em "Salvar" [cite: 887] |
| **QUANDO** o usuário retorna à tela principal da Venda "5" |
| **ENTÃO** a quantidade do item deve estar atualizada na lista |
| **E** o "Sub-Total" e "Quantidade Total" da venda devem ser recalculados. |

| **Critérios de aceitação** |
| :--- |
| A quantidade do item e o total da venda devem ser atualizados. |

---

### Caso de Teste 03: Tentar alterar uma venda confirmada (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT12 | O sistema não deve permitir a alteração (adição de itens ou mudança de valores) em uma venda já confirmada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "CONFIRMADA" (ex: Número "5") salva no sistema[cite: 1210]. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda "5" ("CONFIRMADA") |
| **QUANDO** o usuário clica no botão "Alterar" (na seção de produtos) [cite: 1227] |
| **ENTÃO** o sistema deve exibir uma mensagem (ex: "Venda já confirmada, não pode ser alterada") |
| **OU** os botões de alteração devem estar desabilitados[cite: 1227]. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve impedir qualquer modificação nos itens ou valores de uma venda confirmada. |

---

### Caso de Teste 04: Tentar aplicar desconto maior que o valor total (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT13 | O sistema não deve permitir a aplicação de um desconto que torne o valor total negativo. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Confirmar Venda". |
| O "Sub-Total" é de R$1.200,00[cite: 1025]. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Confirmar Venda" |
| **E** no campo "Desconto %", digita "110" |
| **QUANDO** o usuário sai do campo ou tenta salvar |
| **ENTÃO** o sistema deve reverter o valor para "0" ou "100" |
| **OU** deve exibir uma mensagem de erro (ex: "Desconto inválido"). |

| **Critérios de aceitação** |
| :--- |
| O "Total" da venda não pode ser menor que R$0,00. |
| O sistema deve validar o campo de desconto. |