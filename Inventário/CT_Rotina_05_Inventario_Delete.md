## Cenário 05: Rotina de Inventário (CRUD - Delete).

### Caso de Teste 01: Excluir item de inventário sem dependências (Positivo).

| ID | Descrição |
| :--- | :--- |
| R05-CT01 | Excluir um item de inventário que não possui histórico de vendas e está com estoque zerado. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão de "Administrador" ou "Excluir Produto". |
| Deve existir um item "PRODUTO TESTE DELETE" com estoque "0" e sem vínculo com pedidos de venda ou compra. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" |
| **E** busca e localiza o item "PRODUTO TESTE DELETE" |
| **E** clica em "Excluir" no item "PRODUTO TESTE DELETE" |
| **E** o sistema exibe um modal de confirmação "Deseja realmente excluir este registro?" |
| **QUANDO** o usuário clicar em "Confirmar" (ou "Sim") |
| **ENTÃO** o item "PRODUTO TESTE DELETE" deve ser removido do sistema |

| **Critérios de aceitação** |
| :--- |
| O item "PRODUTO TESTE DELETE" não deve mais aparecer nas buscas ou na lista de inventário. |

**CENÁRIO TESTADO E EVIDENCIADO, DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/ef061b4f69414154b7512a9d78172d5b]

---

### Caso de Teste 02: Tentar excluir item com estoque ou histórico (Negativo).

| ID | Descrição |
| :--- | :--- |
| R05-CT02 | O sistema não deve permitir a exclusão de um item que tenha estoque ou esteja vinculado a vendas. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão de "Administrador". |
| Deve existir um item com estoque ou com histórico de vendas. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" |
| **E** busca e localiza o item com estoque/histórico de vendas |
| **E** clica em "Excluir" no item com estoque/histórico de vendas  |
| **E** o sistema exibe um modal de confirmação |
| **QUANDO** o usuário clicar em "Confirmar" (ou "Sim") |
| **ENTÃO** o sistema deve exibir uma mensagem de erro |
| **E** o item com estoque/histórico de vendas não deve ser excluído. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro informando a restrição deve ser exibida. |
| O item com estoque/histórico de vendas deve permanecer no inventário. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/c24821c7df604fe4ac5c1a1deb960ef9]