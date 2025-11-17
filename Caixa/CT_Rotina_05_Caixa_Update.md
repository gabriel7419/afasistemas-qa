## Cenário 05: Rotina de Caixa (CRUD - Update).

### Caso de Teste 01: Fazer conferência de caixa (Positivo).

| ID | Descrição |
| :--- | :--- |
| R05-CT09 | Realizar a conferência de valores por "Tipo de Documento" antes de fechar o caixa. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa", com o caixa aberto. |
| Vendas foram feitas com "DINHEIRO" e "CHEQUE". |

| **Passos** |
| :--- |
| **DADO** que o usuário está no "Livro Caixa" e clica em "Fechar Caixa" |
| **E** seleciona "Fazer Conferência" no menu pop-up |
| **E** o sistema exibe a tela de "Conferência de Caixa" |
| **E** o usuário conta o dinheiro físico e insere o "Valor Real" (ex: 2525,00) |
| **QUANDO** o sistema calcula a "Diferença" |
| **ENTÃO** o "Valor no Caixa" (sistema) deve bater com o "Valor Real" (físico) |
| **E** a "Diferença" deve ser "0,00". |

| **Critérios de aceitação** |
| :--- |
| O sistema deve exibir os valores corretos por tipo de documento ("CHEQUE", "DINHEIRO"). |
| O usuário deve conseguir inserir o "Valor Real" para validar a diferença. |

---

### Caso de Teste 02: Fechar o caixa (Positivo).

| ID | Descrição |
| :--- | :--- |
| R05-CT10 | Atualizar o status do caixa de "Aberto" para "Fechado", finalizando as operações do dia. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa", com o caixa aberto. |
| A conferência de valores foi realizada. |

| **Passos** |
| :--- |
| **DADO** que o usuário está no "Livro Caixa" |
| **E** clica em "Fechar Caixa" |
| **E** seleciona "Fechar Caixa" no menu pop-up |
| **E** o sistema exibe a tela "Fechamento de Caixa" com os saldos |
| **QUANDO** o usuário clica em "Salvar" |
| **ENTÃO** o status do "Livro Caixa" deve mudar para "Caixa Aberto: Não" |
| **E** o "Histórico" deve registrar uma linha de "FECHAMENTO DO CAIXA NO DIA". |

| **Critérios de aceitação** |
| :--- |
| O status do caixa deve ser atualizado para "Não". |
| O fechamento deve ser registrado no histórico. |
| O saldo do dia deve ser zerado. |

---

### Caso de Teste 03: Tentar retirar valor maior que o saldo em caixa (Negativo).

| ID | Descrição |
| :--- | :--- |
| R05-CT11 | O sistema não deve permitir uma retirada ("sangria") de "DINHEIRO" maior do que o valor disponível em "DINHEIRO" no caixa. |

| **Pré-condições** |
| :--- |
| O usuário está no "Livro Caixa", caixa aberto. |
| A conferência mostra R$2525,00 em "DINHEIRO". |

| **Passos** |
| :--- |
| **DADO** que o saldo de "DINHEIRO" é R$2525,00 |
| **E** o usuário clica em "Retirar Valores" |
| **E** tenta registrar uma nova retirada com "Valor" R$3000,00 e "Tipo: DINHEIRO" |
| **QUANDO** o usuário clica em "Salvar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Saldo insuficiente para esta retirada") |
| **E** a retirada não deve ser registrada no histórico. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve validar o saldo por tipo de documento antes de permitir a retirada. |
| A retirada não deve ser concluída. |

---

### Caso de Teste 04: Tentar fechar um caixa que já está fechado (Negativo).

| ID | Descrição |
| :--- | :--- |
| R05-CT12 | O sistema não deve permitir que o usuário execute a ação "Fechar Caixa" se ele já estiver "Aberto: Não". |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa". |
| O status é "Caixa Aberto: Não". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Livro Caixa" e o caixa está fechado |
| **QUANDO** o usuário clica no botão "Fechar Caixa" |
| **ENTÃO** o botão deve estar desabilitado (ou exibir status "Fechar Caixa" em vez de "Fechar Caixa") |
| **OU** o sistema deve exibir uma mensagem de erro (ex: "O caixa já está fechado"). |

| **Critérios de aceitação** |
| :--- |
| O sistema deve impedir a ação de fechar um caixa já fechado. |