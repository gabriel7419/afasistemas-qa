## Cenário 04: Rotina de Cliente (CRUD - Read).

### Caso de Teste 01: Consultar cliente PF cadastrado (Positivo).

| ID | Descrição |
| :--- | :--- |
| R04-CT05 | Buscar e visualizar os dados de um cliente Pessoa Física já cadastrado. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Clientes". |
| Existe um cliente PF cadastrado (ex: "3 - JOSE SILVA"). |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Cadastro de Clientes" |
| **E** utiliza os botões de navegação ou a busca para localizar o cliente "3" |
| **QUANDO** o cliente "3" é carregado |
| **ENTÃO** todos os dados (Nome, CPF, Endereço) devem ser exibidos corretamente na tela. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve exibir todos os dados gravados do cliente "3 - JOSE SILVA". |

---

### Caso de Teste 02: Gerar relatório de Contas a Receber (Positivo).

| ID | Descrição |
| :--- | :--- |
| R04-CT06 | Gerar o relatório de "Contas a Receber" para um cliente. |

| **Pré-condições** |
| :--- |
| O usuário tem permissão para o menu "Financeiro" > "Contas a Receber". |
| Existe um cliente com vendas a prazo (ex: "JOSE SILVA"). |

| **Passos** |
| :--- |
| **DADO** que o usuário navega para "Financeiro" > "Contas a Receber" |
| **E** localiza a conta do cliente "JOSE SILVA" |
| **E** clica em "Imprimir" |
| **E** seleciona as opções de impressão (ex: "Modo Texto") e clica em "Confirmar" |
| **QUANDO** o relatório é gerado |
| **ENTÃO** o sistema deve exibir o Gerenciador de Impressão |
| **E** o relatório deve conter os dados do cliente e os valores das parcelas a receber. |

| **Critérios de aceitação** |
| :--- |
| O relatório de "Contas a Receber" deve ser gerado com os dados corretos do cliente e da dívida. |

---

### Caso de Teste 03: Tentar consultar cliente inexistente (Negativo).

| ID | Descrição |
| :--- | :--- |
| R04-CT07 | O sistema não deve carregar dados ao buscar por um código de cliente que não existe. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Clientes". |
| O código "999" não existe. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Cadastro de Clientes" |
| **E** digita "999" no campo "Código" |
| **QUANDO** o usuário pressiona "Enter" ou sai do campo |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Cliente não encontrado") |
| **E** os campos da tela devem permanecer vazios ou com os dados do registro anterior. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro "não encontrado" deve ser exibida. |

---

### Caso de Teste 04: Tentar consultar guias desabilitadas (Negativo).

| ID | Descrição |
| :--- | :--- |
| R04-CT08 | O sistema não deve exibir as guias "Dados Financeiros" e "Dependentes" por padrão. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Clientes". |
| As guias extras ainda não foram habilitadas. |

| **Passos** |
| :--- |
| **DADO** que o usuário localiza um cliente cadastrado |
| **QUANDO** o usuário inspeciona as guias disponíveis |
| **ENTÃO** as guias "Dados Gerais", "Outros Dados" e "Referências" devem estar visíveis |
| **E** as guias "Dados Financeiros" e "Dependentes" não devem estar visíveis. |

| **Critérios de aceitação** |
| :--- |
| O acesso às guias de crédito e dependentes deve estar oculto até a configuração. |