## Cenário 03: Rotina de Compra (CRUD - Read).

### Caso de Teste 01: Consultar fornecedor cadastrado (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT05 | Buscar e visualizar os dados deCompra - Delete | Caminho inFeliz 1 um fornecedor já cadastrado. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Fornecedores". |
| Existe um fornecedor cadastrado (ex: "7 - TONY RAMOS PELES LTDA"). |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Cadastro de Fornecedores" |
| **E** utiliza os botões de navegação ou a busca para localizar o fornecedor "7" |
| **QUANDO** o fornecedor "7" é carregado |
| **ENTÃO** todos os dados (Nome, Endereço, Tipo de Pessoa) devem ser exibidos corretamente na tela. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve exibir todos os dados gravados do fornecedor. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO LOOM E DRIVE**
[https://www.loom.com/share/53e9e39adf3a49e7876b576ce2bd5179]

---

### Caso de Teste 02: Visualizar desdobramento de conta (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT06 | Visualizar a tela "Desdobramento da Conta" após definir as parcelas de uma compra a prazo. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Contas a Pagar" (que abre após confirmar uma compra a prazo). |
| O usuário preencheu "Qt. Parcelas: 5". |

| **Passos** |
| :--- |
| **DADO** que o usuário preencheu "Qt. Parcelas: 5" e clicou em "Salvar" |
| **QUANDO** a tela "Desdobramento da Conta" é exibida |
| **ENTÃO** o sistema deve mostrar 5 parcelas listadas (ou a primeira de 5) |
| **E** o "Valor Parcela" deve estar calculado (Valor Total / 5) |
| **E** as datas de "Vencimento" devem estar preenchidas sequencialmente. |

| **Critérios de aceitação** |
| :--- |
| A tela deve exibir corretamente as parcelas geradas, com valores e vencimentos. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO LOOM E DRIVE**
[https://www.loom.com/share/ab23c05c3fd442abaf10ca7478112392]

---

### Caso de Teste 03: Tentar consultar fornecedor inexistente (Negativo).

| ID | Descrição |
| :--- | :--- |
| R03-CT07 | O sistema não deve carregar dados ao buscar por um código de fornecedor que não existe. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Fornecedores". |
| O código "999" não existe. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Cadastro de Fornecedores" |
| **E** digita "999" no campo "Código" |
| **QUANDO** o usuário pressiona "Enter" ou sai do campo |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Fornecedor não encontrado") |
| **E** os campos da tela devem permanecer vazios ou com os dados do registro anterior. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro "não encontrado" deve ser exibida. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO LOOM E DRIVE**
[https://www.loom.com/share/c6d8c8b0d8c841d79b88b2785016e384]

---

### Caso de Teste 04: Tentar consultar pedido de compra inexistente (Negativo).

| ID | Descrição |
| :--- | :--- |
| R03-CT08 | O sistema não deve carregar dados ao buscar por um número de compra que não existe. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Compra". |
| O número "999" não existe. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Compra" |
| **E** digita "999" no campo "Número" |
| **QUANDO** o usuário pressiona "Enter" ou sai do campo |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Compra não encontrada") |
| **E** os campos da tela (Fornecedor, Itens) devem permanecer vazios. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro "não encontrado" deve ser exibida. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO LOOM E DRIVE**
[https://www.loom.com/share/dec1fe06c1704805a6b4e2797bd15e33]