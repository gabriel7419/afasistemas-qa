## Cenário 03: Rotina de Inventário (CRUD - Read).

### Caso de Teste 01: Consultar item de inventário existente (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT01 | Buscar e visualizar os detalhes de um item de inventário existente usando o campo de busca. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para acessar o menu "Inventário" ou "Produtos". |
| Deve existir um item com o Código/SKU "33" e Descrição "Item de Busca". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Produtos" |
| **E** clica na lupa de busca no canto superior direito |
| **E** seleciona, em "Campo (F1), a opção "Código Alfa Numérico"|
| **E** digita "33" no campo "Contendo" |
| **QUANDO** o usuário pressiona "Enter" ou clica no ícone de busca |
| **ENTÃO** a exibição de inventário deve ser filtrada, exibindo apenas o item "33" |
| **E** os detalhes (Estoque, Preço) do item devem ser visíveis e corretos. |

| **Critérios de aceitação** |
| :--- |
| O item "33" deve ser o único resultado exibido. |
| Os dados exibidos na lista devem corresponder aos dados do item no banco de dados. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/67c0dcd402ff4be3b45e53cdff9820a4]

---

### Caso de Teste 02: Consultar item de inventário inexistente (Negativo).

| ID | Descrição |
| :--- | :--- |
| R03-CT02 | Buscar por um item de inventário que não existe no sistema. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Produtos". |
| O código "404" não deve existir no banco de dados. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Produtos" |
| **E** clica na lupa de busca no canto superior direito |
| **E** seleciona, em "Campo (F1), a opção "Código Alfa Numérico"|
| **E** digita "404" no campo "Contendo" |
| **QUANDO** o usuário pressiona "Enter" ou clica no ícone de busca |
| **ENTÃO** o sistema deve exibir uma lista vazia |
| **E** deve exibir uma mensagem (ex: "Nenhum item encontrado"). |

| **Critérios de aceitação** |
| :--- |
| A lista de resultados da busca deve estar vazia. |
| Uma mensagem clara indicando que nenhum resultado foi encontrado deve ser exibida. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/f88acd6d2806456fbd4092da56944b83]
**REPROVADO - AUSÊNCIA DE MENSAGEM CLARA INDICANDO NENHUM RESULTADO**