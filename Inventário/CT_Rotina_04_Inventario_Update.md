## Cenário 04: Rotina de Inventário (CRUD - Update).

### Caso de Teste 01: Atualizar o nome de produto (Positivo).

| ID | Descrição |
| :--- | :--- |
| R04-CT01 | Atualizar o nome de um produto existente|

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para acessar "Alterar". |
| Deve existir um item "36" com o nome de "Produto Teste Novo"". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Produto" |
| **E** busca e localiza o item "36" |
| **E** clica em "Alterar" no item 36" |
| **E** no campo "Nome do Produto", digita "Calça Jeans" |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o nome do item 36" deve ser atualizado para "Calça Jeans" |
| **E** o novo nome deve ser possível de ser visualizado na listagem. |

| **Critérios de aceitação** |
| :--- |
| Ao consultar o item 36, o nome deve estar devidamente atualizado. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/c59d4f8279ab476795b00862377568de]
---

### Caso de Teste 02: Tentar atualizar o nome de um produto com caracteres inválidos.

| ID | Descrição |
| :--- | :--- |
| R04-CT02 | O sistema não deve permitir a atualização do nome com caracteres inválidos. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Alterar" informações de um produto. |
| Deve existir um item "36". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" |
| **E** busca e localiza o item "36" |
| **E** clica em "Alterar" |
| **E** no campo "Nome do Produto", digita "{*}" (caracteres inválidos) |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Insira o nome do produto") |
| **E** o nome do item "36" não deve ser alterado. |

| **Critérios de aceitação** |
| :--- |
| O sistema não deve aceitar os caracteres inválidos inseridos, deixando o campo em branco |
| O nome do item não será alterado e o sistema deve solicitar a inserção de um novo nome. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/d97b1d5747164f3da66b8adb12f7aa00]