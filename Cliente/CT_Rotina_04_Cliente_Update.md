## Cenário 04: Rotina de Cliente (CRUD - Update).

### Caso de Teste 01: Habilitar guias (Dados Financeiros, Dependentes) (Positivo).

| ID | Descrição |
| :--- | :--- |
| R04-CT09 | Habilitar a exibição das guias "Dados Financeiros" e "Dependentes" no cadastro de clientes. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Cadastro de Clientes". |
| O usuário tem a senha de administrador. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Cadastro de Clientes" |
| **E** clica no ícone "Opções" (duas chaves) |
| **E** na tela "Exibir guias", marca "Dados financeiros" e "Dependentes" |
| **E** clica em "Salvar" e insere a senha de administrador |
| **QUANDO** o usuário retorna à tela de "Cadastro de Clientes" |
| **ENTÃO** as guias "Dados Financeiros" e "Dependentes" devem estar visíveis. |

| **Critérios de aceitação** |
| :--- |
| As novas guias devem aparecer no cadastro do cliente, permitindo acesso às funções. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO GOOGLE DRIVE**

---

### Caso de Teste 02: Atualizar limite de crédito (Positivo).

| ID | Descrição |
| :--- | :--- |
| R04-CT10 | Definir e depois atualizar o "Limite de Crédito" de um cliente. |

| **Pré-condições** |
| :--- |
| A guia "Dados Financeiros" está habilitada. |
| O usuário está visualizando um cliente (ex: "3 - JOSE SILVA"). |

| **Passos** |
| :--- |
| **DADO** que o usuário está na guia "Dados Financeiros" do cliente |
| **E** define o "Limite de Crédito" inicial (ex: R$500,00) e clica em "Salvar" |
| **E** localiza o mesmo cliente novamente |
| **E** altera o "Limite de Crédito" para um novo valor (ex: R$700,00) |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o novo limite de crédito (R$700,00) deve ser salvo para o cliente. |

| **Critérios de aceitação** |
| :--- |
| O valor do "Limite de Crédito" deve ser atualizado e persistido no cadastro. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO GOOGLE DRIVE**

---

### Caso de Teste 03: Tentar habilitar guias sem senha (Negativo).

| ID | Descrição |
| :--- | :--- |
| R04-CT11 | O sistema não deve permitir habilitar as guias extras se a senha de administrador estiver incorreta. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Exibir guias" após clicar em "Opções". |

| **Passos** |
| :--- |
| **DADO** que o usuário marca as guias "Dados financeiros" e "Dependentes" |
| **E** clica em "Salvar" |
| **QUANDO** o sistema solicita "Usuário e Senha" e o usuário insere uma senha incorreta |
| **ENTÃO** o sistema deve exibir uma mensagem de "Usuário ou Senha inválidos" |
| **E** as guias não devem ser habilitadas. |

| **Critérios de aceitação** |
| :--- |
| A alteração de configuração deve ser bloqueada sem a autenticação correta. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO GOOGLE DRIVE**
 -> O sistema não apresenta o comportamento esperado, congelando após as 3 tentaitivas. ALém disso, não há espeficação na entrada o usuário - se está vazia ou incorreta. 

---