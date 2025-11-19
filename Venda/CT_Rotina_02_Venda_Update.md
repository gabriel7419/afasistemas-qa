## Cenário 02: Rotina de Venda (CRUD - Update).

### Caso de Teste 01: Adicionar item a uma venda não confirmada (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT10 | O usuário adiciona um novo produto a uma venda que foi salva mas ainda não finalizada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "NÃO CONFIRMADA" salva no sistema. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda NÃO CONFIRMADA |
| **E** clica no botão "Novo" na seção "Entrada de Produtos"  |
| **E** adiciona um novo produto e clica em "Salvar"  |
| **QUANDO** o usuário retorna à tela principal da Venda |
| **ENTÃO** o novo produto deve estar listado junto aos anteriores |
| **E** o "Sub-Total", "Número de Itens" e "Quantidade Total" da venda devem ser recalculados |

| **Critérios de aceitação** |
| :--- |
| O novo item deve aparecer na lista de produtos da venda. |
| O valor total da venda deve ser atualizado. |

**Cenário Testado e Evidenciado - Disponível no Drive e no Loom**
[https://www.loom.com/share/e52b907f9ebb4d62ac44e77fbb286373]

---

### Caso de Teste 02: Alterar quantidade de um item em venda não confirmada (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT11 | O usuário altera a quantidade de um item em uma venda que ainda não foi finalizada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "NÃO CONFIRMADA"com pelo menos um item. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda ("NÃO CONFIRMADA") |
| **E** seleciona o item que deseja alterar na lista |
| **E** clica no botão "Alterar" na seção "Entrada de Produtos" |
| **E** na tela "Entrada de Produtos para Venda", muda o campo "Quant." |
| **E** clica em "Salvar" |
| **QUANDO** o usuário retorna à tela principal da Venda|
| **ENTÃO** a quantidade do item deve estar atualizada na lista |
| **E** o "Sub-Total" e "Quantidade Total" da venda devem ser recalculados. |

| **Critérios de aceitação** |
| :--- |
| A quantidade do item e o total da venda devem ser atualizados. |

**Cenário Testado e Evidenciado - Disponível no Drive e no Loom**
[https://www.loom.com/share/c7188ec90ab54cc9aaf83daf939aefb7]

---

### Caso de Teste 03: Tentar alterar uma venda confirmada (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT12 | O sistema não deve permitir a alteração (adição de itens ou mudança de valores) em uma venda já confirmada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "CONFIRMADA" salva no sistema |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda CONFIRMADA |
| **QUANDO** o usuário clica no botão "Alterar" (na seção de produtos)  |
| **ENTÃO** o sistema deve exibir uma mensagem (ex: "Venda já confirmada, não pode ser alterada") |
| **OU** os botões de alteração devem estar desabilitados |

| **Critérios de aceitação** |
| :--- |
| O sistema deve impedir qualquer modificação nos itens ou valores de uma venda confirmada. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/e42ba98317cf409398fd5a70204414f5]

---

### Caso de Teste 04: Tentar aplicar desconto maior que o valor total (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT13 | O sistema não deve permitir a aplicação de um desconto que torne o valor total negativo. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Confirmar Venda". |
| O "Sub-Total" é de R$1.200,00 |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Confirmar Venda" |
| **E** no campo "Desconto %", digita "110" |
| **QUANDO** o usuário sai do campo ou tenta salvar |
| **ENTÃO** o sistema deve reverter o valor para "0" ou "100" |
| **OU** deve exibir uma mensagem de erro |

| **Critérios de aceitação** |
| :--- |
| O "Total" da venda não pode ser menor que R$0,00. |
| O sistema deve validar o campo de desconto. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/a5091c6bba2844b5b065b0f298e8b706]
- Parcialmente aprovado. O sistema bloqueia, mas não deixa claro que o desconto é maior do que devia.