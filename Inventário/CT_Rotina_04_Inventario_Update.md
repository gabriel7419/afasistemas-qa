## Cenário 04: Rotina de Inventário (CRUD - Update).

### Caso de Teste 01: Ajustar manualmente o estoque (Positivo).

| ID | Descrição |
| :--- | :--- |
| R04-CT01 | Atualizar a quantidade em estoque de um item existente (ex: ajuste de balanço). |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Ajuste de Inventário" ou "Editar Produto". |
| Deve existir um item "PROD-789" com estoque atual de "50". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" |
| **E** busca e localiza o item "PROD-789" |
| **E** clica em "Editar" (ou "Ajustar Estoque") no item "PROD-789" |
| **E** no campo "Nova Quantidade" (ou "Ajuste"), digita "55" |
| **E** preenche o campo "Motivo" (ex: "Contagem de balanço") |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o estoque do item "PROD-789" deve ser atualizado para "55" |
| **E** um registro de log de movimentação de estoque deve ser criado. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve exibir "Estoque atualizado com sucesso". |
| Ao consultar o item "PROD-789" novamente, o estoque exibido deve ser "55". |

---

### Caso de Teste 02: Tentar atualizar estoque com valor inválido (Negativo).

| ID | Descrição |
| :--- | :--- |
| R04-CT02 | O sistema não deve permitir a atualização do estoque com dados não numéricos. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Ajuste de Inventário". |
| Deve existir um item "PROD-789". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" |
| **E** busca e localiza o item "PROD-789" |
| **E** clica em "Editar" (ou "Ajustar Estoque") |
| **E** no campo "Nova Quantidade", digita "ABC" (um valor não numérico) |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Valor inválido. Insira apenas números") |
| **E** o estoque do item "PROD-789" não deve ser alterado. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro de validação de campo deve ser exibida. |
| O estoque do item deve permanecer inalterado. |