## Cenário 02: Rotina de Venda (CRUD - Read).

### Caso de Teste 01: Consultar venda confirmada existente (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT06 | Buscar e visualizar os detalhes de uma venda já confirmada usando os controles de navegação. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Venda". |
| Deve existir uma venda "CONFIRMADA" (ex: Número "3"). |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Venda" |
| **E** utiliza os botões de navegação (setas) ou busca para localizar a venda "3"  |
| **QUANDO** a venda "5" é carregada na tela |
| **ENTÃO** o "Status da Venda" deve ser "CONFIRMADA" |
| **E** todos os campos (Cliente, Itens, Total) devem estar devidamente preenchidos. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve exibir todos os dados da venda 3. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/262ad894e55944e68335657713a0a1fc]


---

### Caso de Teste 02: Validar fechamento de caixa (conciliação) (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT07 |  Conferir os totais no Livro Caixa após a realização de vendas |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Livro Caixa". |
| Pelo menos uma venda com "DINHEIRO" e "CHEQUE" foi confirmada |

| **Passos** |
| :--- |
| **DADO** que o usuário realizou vendas durante o dia |
| **E** navega para a tela "Livro Caixa" |
| **E** clica em "Fechar Caixa" e depois em "Fazer Conferência" |
| **QUANDO** o usuário visualiza a tela de "Conferência de Caixa" |
| **ENTÃO** o "Valor no Caixa" para "DINHEIRO" e "CHEQUE" deve corresponder exatamente aos valores recebidos nas vendas|

| **Critérios de aceitação** |
| :--- |
| Os valores "Valor no Caixa" por tipo de documento devem bater com os valores das vendas confirmadas |
| A conciliação do relatório deve ser validada com o caixa |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/adce91bdd7c74a5d9a331e3ecf585e88]

---

### Caso de Teste 03: Tentar consultar venda inexistente (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT08 | Tentar buscar por um número de venda que não existe no sistema. |

| **Pré-condições** |
| :--- |
| O usuário está na tela de "Venda". |
| O número de venda "9999" não existe. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Venda" |
| **E** digita "9999" no campo "Código" |
| **QUANDO** o usuário pressiona "Enter" ou sai do campo |
| **ENTÃO** o sistema não deve retornar nenhuma venda |
| **E** a tabela de retorno deve estar em branco |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro informando que o registro não foi localizado deve ser exibida. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/a775731e30164ccf8a4f79102d8f437a]

---

### Caso de Teste 04: Tentar ler dados de conferência com caixa fechado (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT09 | O sistema não deve permitir a visualização da conferência de caixa se o caixa não estiver aberto. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa". |
| O "Caixa Aberto" está "Não". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Livro Caixa" e o caixa está fechado |
| **QUANDO** o usuário clica em "Fechar Caixa" (para tentar acessar a conferência) |
| **ENTÃO** o sistema deve exibir uma mensagem (ex: "Caixa já está fechado") |
| **E** não deve permitir o acesso à tela de "Conferência de Caixa". |

| **Critérios de aceitação** |
| :--- |
| O sistema deve impedir o acesso à funcionalidade de conferência. |
| O usuário só pode "Abrir Caixa". |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/f15d5db9fbec46f19829fc5a13d544a8]