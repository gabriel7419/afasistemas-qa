## Cenário 04: Rotina de Cliente (CRUD - Create).

### Caso de Teste 01: Cadastrar novo cliente Pessoa Física (Positivo).

| ID | Descrição |
| :--- | :--- |
| R04-CT01 | Cadastrar um novo cliente do "Tipo Pessoa: FÍSICA" com dados válidos. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para acessar o "Cadastro de Clientes" (ícone de pessoas). |
| Os dados (CPF, Nome) do novo cliente não devem existir no sistema. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela inicial e clica no ícone "Cadastro de Clientes"
| **E** clica no botão "Novo"|
| **E** preenche "Cliente" (Nome), "Dt. Nasc.", "CPF", "Endereço" e "Cidade" |
| **E** o "Tipo Pessoa" está definido como "FÍSICA"|
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o novo cliente será registrado (ex: "3 - JOSE SILVA") |
| **E** o sistema exibirá os dados do cliente recém-cadastrado na tela. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve salvar o cliente e atribuir um novo "Código". |
| O cliente deve aparecer na lista ao ser pesquisado. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/7ee792b30ebe4c7fb56d5a5a8200e826]

---

### Caso de Teste 02: Cadastrar novo cliente Pessoa Jurídica (Positivo).

| ID | Descrição |
| :--- | :--- |
| R04-CT02 | Cadastrar um novo cliente do "Tipo Pessoa: JURÍDICA". |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Clientes". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Cadastro de Clientes" e clica em "Novo" |
| **E** muda o "Tipo Pessoa" para "JURÍDICA" |
| **E** preenche "Cliente" (Nome Fantasia), "CNPJ", "Razão Social" e "Endereço" |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o novo cliente será registrado (ex: "4 - SILVA JOSÉ") |
| **E** o sistema exibirá os dados do cliente PJ cadastrado. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve salvar o cliente com os campos de PJ (CNPJ, Razão Social) corretos. |
| O "Tipo Pessoa" deve estar salvo como "JURÍDICA". |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/d6690741a60f4f928c31d0a2b04e1b1a]

---

### Caso de Teste 03: Tentar cadastrar cliente sem nome (Negativo).

| ID | Descrição |
| :--- | :--- |
| R04-CT03 | O sistema não deve permitir o cadastro de um cliente sem o campo "Cliente" (Nome). |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Clientes", no modo "Novo". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela de cadastro de novo cliente |
| **E** o campo "Cliente" (Nome) está vazio |
| **E** preenche outros campos (ex: CPF, Endereço) |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Campo Cliente é obrigatório") |
| **E** o cliente não deve ser salvo. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro de validação de campo deve ser exibida. |
| O cliente não deve ser registrado no banco de dados. |

**CENÁRIO EVIDENCIADO E TESTADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/a3454f55acbd49998a60360fc24b2f63]

---

### Caso de Teste 04: Tentar cadastrar dependente sem dados (Negativo).

| ID | Descrição |
| :--- | :--- |
| R04-CT04 | O sistema não deve permitir salvar um dependente sem preencher os campos obrigatórios. |

| **Pré-condições** |
| :--- |
| O usuário está na guia "Dependentes" de um cliente. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na guia "Dependentes" e clica em "Novo" |
| **E** o campo "Nome" do dependente está vazio |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Nome do dependente é obrigatório") |
| **E** o dependente não deve ser salvo. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro de validação de campo deve ser exibida. |
| O dependente não deve ser associado ao cliente. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/c27000a822884d85b11a1ffa1c6732ca]