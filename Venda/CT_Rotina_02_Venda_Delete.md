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
| **E** clica no botão "Excluir" na seção "Entrada de Produtos" |
| **E** confirma a exclusão (se solicitado) |
| **QUANDO** a operação é confirmada |
| **ENTÃO** o item deve desaparecer da lista |
| **E** o "Sub-Total", "Número de Itens" e "Quantidade Total" da venda devem ser recalculados. |

| **Critérios de aceitação** |
| :--- |
| O item deve ser removido da lista da venda. |
| O valor total da venda deve ser atualizado (reduzido). |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/fe74f3b3a61c46f2a789f22e64a84a80]

---

### Caso de Teste 02: Excluir (cancelar) uma venda não confirmada (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT15 | O usuário cancela/exclui uma venda inteira que foi registrada mas ainda não foi finalizada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "NÃO CONFIRMADA" salva no sistema. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda "29" ("NÃO CONFIRMADA") |
| **E** clica no botão "Excluir" (na barra de ferramentas principal, ao lado de "Alterar") |
| **E** confirma a exclusão na janela pop-up |
| **QUANDO** a operação é confirmada |
| **ENTÃO** a venda "29" deve ser removida do sistema |
| **E** não deve haver impacto no estoque ou no caixa. |

| **Critérios de aceitação** |
| :--- |
| A venda não deve mais ser encontrada no sistema. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/fb15d1a1c9f84723ad43bfda080bb491]

---

### Caso de Teste 03: Tentar excluir (cancelar) uma venda confirmada (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT16 | O sistema não deve permitir a exclusão de uma venda confirmada |

| **Pré-condições** |
| :--- |
| Existe uma venda "CONFIRMADA" salva no sistema. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda "26" ("CONFIRMADA") |
| **QUANDO** o usuário clica no botão "Excluir" (na barra de ferramentas principal) |
| **ENTÃO** o sistema deve exibir uma mensagem de erro |
| **OU** o botão "Excluir" deve estar desabilitado. |

| **Critérios de aceitação** |
| :--- |
| A venda "26" deve permanecer no sistema. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/24cc63cefcb942d6b83ba973cba51323]

---

### Caso de Teste 04: Tentar excluir item de uma venda confirmada (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT17 | O sistema não deve permitir a exclusão de um item de uma venda já confirmada. |

| **Pré-condições** |
| :--- |
| Existe uma venda "CONFIRMADA" salva no sistema. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza a venda "CONFIRMADA" |
| **E** seleciona um item na lista de produtos |
| **QUANDO** o usuário clica no botão "Excluir" (na seção "Entrada de Produtos")  |
| **ENTÃO** o sistema deve exibir uma mensagem de erro |
| **OU** o botão "Excluir" (dos itens) deve estar desabilitado. |

| **Critérios de aceitação** |
| :--- |
| O item não deve ser removido da venda. |
| A venda deve permanecer inalterada. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/4e0d1780e3254429adb0ef7d9e21b881]