## Cenário 02: Rotina de Inventário (CRUD - Create).

### Caso de Teste 01: Criar novo item de inventário (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT01 | Cadastrar manualmente um novo produto no inventário que ainda não existe no sistema. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para acessar o menu "Inventário" ou "Produtos". |
| O código (SKU) do novo produto não deve existir no banco de dados. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" (ou "Cadastro de Produtos") |
| **E** clica no botão "Novo Item" |
| **E** preenche o "Código/SKU" (ex: "PROD-123") |
| **E** preenche a "Descrição" (ex: "Produto Teste Novo") |
| **E** preenche a "Quantidade em Estoque" (ex: "10") |
| **E** preenche o "Preço de Custo" (ex: "50.00") |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o sistema deve registrar o novo item no inventário |
| **E** o item "PROD-123" deve estar visível na lista de inventário. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve exibir uma mensagem de "Item salvo com sucesso". |
| O produto "PROD-123" deve constar no banco de dados com estoque "10". |

---

### Caso de Teste 02: Tentar criar item com código duplicado (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT02 | O sistema não deve permitir o cadastro de um novo item se o Código/SKU já existir. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Inventário". |
| Deve existir um item com o Código/SKU "PROD-EXISTENTE" no sistema. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" |
| **E** clica no botão "Novo Item" |
| **E** preenche o "Código/SKU" com "PROD-EXISTENTE" |
| **E** preenche os demais campos obrigatórios (Descrição, Quantidade) |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Código/SKU já cadastrado") |
| **E** o novo item não deve ser salvo. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro informando a duplicidade deve ser exibida. |
| O sistema não deve criar um segundo registro para "PROD-EXISTENTE". |