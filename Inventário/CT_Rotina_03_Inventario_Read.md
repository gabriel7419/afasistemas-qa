## Cenário 03: Rotina de Inventário (CRUD - Read).

### Caso de Teste 01: Consultar item de inventário existente (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT01 | Buscar e visualizar os detalhes de um item de inventário existente usando o campo de busca. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para acessar o menu "Inventário" ou "Produtos". |
| Deve existir um item com o Código/SKU "PROD-456" e Descrição "Item de Busca". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" |
| **E** digita "PROD-456" (ou "Item de Busca") no campo "Buscar" |
| **QUANDO** o usuário pressiona "Enter" ou clica no ícone de busca |
| **ENTÃO** a lista de inventário deve ser filtrada, exibindo apenas o item "PROD-456" |
| **E** os detalhes (Estoque, Preço) do item devem ser visíveis e corretos. |

| **Critérios de aceitação** |
| :--- |
| O item "PROD-456" deve ser o único (ou um dos) resultados exibidos na lista. |
| Os dados exibidos na lista devem corresponder aos dados do item no banco de dados. |

---

### Caso de Teste 02: Consultar item de inventário inexistente (Negativo).

| ID | Descrição |
| :--- | :--- |
| R03-CT02 | Buscar por um item de inventário que não existe no sistema. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Inventário". |
| O código "PROD-INEXISTENTE" não deve existir no banco de dados. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Inventário" |
| **E** digita "PROD-INEXISTENTE" no campo "Buscar" |
| **QUANDO** o usuário pressiona "Enter" ou clica no ícone de busca |
| **ENTÃO** o sistema deve exibir uma lista vazia |
| **E** deve exibir uma mensagem (ex: "Nenhum item encontrado"). |

| **Critérios de aceitação** |
| :--- |
| A lista de resultados da busca deve estar vazia. |
| Uma mensagem clara indicando que nenhum resultado foi encontrado deve ser exibida. |