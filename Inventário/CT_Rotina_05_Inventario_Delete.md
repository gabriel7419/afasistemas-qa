## Cenário 05: Rotina de Inventário (CRUD - Delete).

### Caso de Teste 01: Excluir item de inventário sem dependências (Positivo).

| ID | Descrição |
| :--- | :--- |
| R05-CT01 | Excluir um item de inventário que não possui histórico de vendas e está com estoque zerado. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão de "Administrador" ou "Excluir Produto". |
| Deve existir um item "PROD-DEL" com estoque "0" e sem vínculo com pedidos de venda ou compra. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" |
| **E** busca e localiza o item "PROD-DEL" |
| **E** clica em "Excluir" no item "PROD-DEL" |
| **E** o sistema exibe um modal de confirmação "Deseja realmente excluir este item?" |
| **QUANDO** o usuário clicar em "Confirmar" (ou "Sim") |
| **ENTÃO** o item "PROD-DEL" deve ser removido do sistema |
| **E** o sistema deve exibir a mensagem "Item excluído com sucesso". |

| **Critérios de aceitação** |
| :--- |
| O item "PROD-DEL" não deve mais aparecer nas buscas ou na lista de inventário. |

---

### Caso de Teste 02: Tentar excluir item com estoque ou histórico (Negativo).

| ID | Descrição |
| :--- | :--- |
| R05-CT02 | O sistema não deve permitir a exclusão de um item que tenha estoque ou esteja vinculado a vendas. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão de "Administrador". |
| Deve existir um item "PROD-ATIVO" com estoque "10" (ou com histórico de vendas). |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" |
| **E** busca e localiza o item "PROD-ATIVO" |
| **E** clica em "Excluir" no item "PROD-ATIVO" |
| **E** o sistema exibe um modal de confirmação |
| **QUANDO** o usuário clicar em "Confirmar" (ou "Sim") |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Não é possível excluir. Item possui estoque/histórico de vendas") |
| **E** o item "PROD-ATIVO" não deve ser excluído. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro informando a restrição deve ser exibida. |
| O item "PROD-ATIVO" deve permanecer no inventário. |