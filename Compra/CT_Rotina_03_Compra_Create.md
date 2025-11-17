## Cenário 03: Rotina de Compra (CRUD - Create).

### Caso de Teste 01: Cadastrar novo fornecedor (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT01 | Cadastrar um novo Fornecedor (Pessoa Física) no sistema. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para acessar o "Cadastro de Fornecedores" (ícone de fábrica). |
| Os dados do fornecedor (Nome, Endereço, etc.) não devem existir no sistema. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela inicial |
| **E** clica no ícone "Cadastro de Fornecedores" |
| **E** clica no botão "Novo" |
| **E** preenche o "Fornecedor" (Nome), "Endereço", "Cidade" e demais campos obrigatórios |
| **E** seleciona "Tipo de Pessoa: FISICA" |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o novo fornecedor será registrado (ex: "7 - TONY RAMOS PELES LTDA") |
| **E** o sistema exibirá os dados do fornecedor recém-cadastrado na tela. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve salvar o fornecedor e atribuir um novo "Código". |
| O fornecedor deve aparecer na lista ao ser pesquisado. |

---

### Caso de Teste 02: Criar novo pedido de compra (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT02 | Gerar um novo pedido de compra (à prazo) com 10 itens, deixando-o "NÃO CONFIRMADA". |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para acessar "Compra" (ícone de pasta). |
| Deve existir um Fornecedor cadastrado (ex: "TONY RAMOS PELES LTDA"). |
| Devem existir 10 produtos cadastrados para compra. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela inicial e clica no ícone de "Compra" |
| **E** clica em "Novo" |
| **E** seleciona o "Fornecedor" (ex: TONY RAMOS PELES LTDA) |
| **E** define a "Condição: PRAZO" e clica em "Salvar" |
| **E** adiciona o primeiro item (Produto, Quant., Preço) e clica em "Salvar" |
| **E** repete o passo anterior até adicionar 10 itens |
| **QUANDO** o usuário fechar a tela de adição de itens |
| **ENTÃO** o sistema deve exibir a tela de Compra com os 10 itens listados |
| **E** o "Status da Compra" deve ser "NÃO CONFIRMADA". |

| **Critérios de aceitação** |
| :--- |
| O pedido de compra deve ser salvo com status "NÃO CONFIRMADA". |
| O "Número de Itens" e "Quantidade Total" (ex: 10) devem estar corretos. |
| O estoque ainda não deve ser atualizado. |

---

### Caso de Teste 03: Tentar cadastrar fornecedor sem nome (Negativo).

| ID | Descrição |
| :--- | :--- |
| R03-CT03 | O sistema não deve permitir o cadastro de um fornecedor sem o campo "Fornecedor" (Nome). |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Fornecedores", no modo "Novo". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela de cadastro de novo fornecedor |
| **E** o campo "Fornecedor" (Nome) está vazio |
| **E** preenche outros campos (ex: Endereço, Cidade) |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Campo Fornecedor é obrigatório") |
| **E** o fornecedor não deve ser salvo. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro de validação de campo deve ser exibida. |
| O fornecedor não deve ser registrado no banco de dados. |

---

### Caso de Teste 04: Tentar criar pedido de compra sem fornecedor (Negativo).

| ID | Descrição |
| :--- | :--- |
| R03-CT04 | O sistema não deve permitir salvar um novo pedido de compra sem um "Fornecedor" selecionado. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Compra". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Compra" e clica em "Novo" |
| **E** o campo "Fornecedor" está vazio |
| **E** define a "Condição: PRAZO" |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Selecione um Fornecedor") |
| **E** o pedido de compra não deve ser criado. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro de validação de campo deve ser exibida. |
| O sistema não deve prosseguir para a tela de adição de itens. |