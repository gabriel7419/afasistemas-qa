## Cenário 02: Rotina de Venda (CRUD - Create).

### Caso de Teste 01: Criar venda à vista com pagamento misto (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT01 |  Registrar uma nova venda à vista com 5 itens, aplicar desconto e finalizar com pagamento misto (Cartão + Dinheiro)[cite: 770]. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para acessar o menu "Venda"[cite: 775]. |
| O caixa deve estar aberto[cite: 1257]. |
| Devem existir 5 produtos com estoque positivo. |

| **Passos** |
| :--- |
|  **DADO** que o usuário está na tela "Venda" e clica em "Novo" [cite: 810] |
|  **E** preenche o "Cliente", "Funcionário" e "Condição: VISTA" e clica em "Salvar" [cite: 866-868, 884] |
|  **E** adiciona 5 produtos diferentes à venda [cite: 912, 968] |
|  **E** clica em "Finalizar" [cite: 969] |
|  **E** na tela "Confirmar Venda", aplica um "Desconto" (ex: 10%) [cite: 1019-1020] |
|  **E** adiciona um "Tipo de Documento" (ex: CARTÃO CREDITO) com 70% do valor [cite: 1114] |
|  **E** adiciona um segundo "Tipo de Documento" (ex: DINHEIRO) com os 30% restantes [cite: 1143, 1146] |
|  **E** muda o "Status" para "CONFIRMADA" [cite: 1159, 1185] |
|  **QUANDO** o usuário clicar em "Salvar" [cite: 1162, 1202] |
|  **ENTÃO** a venda será registrada como "CONFIRMADA" [cite: 1208, 1210] |
|  **E** o estoque dos 5 produtos será debitado. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve exibir "Status da Venda: CONFIRMADA" na tela principal[cite: 1241]. |
| A "Diferença" na tela de confirmação deve ser "R$0,00"[cite: 1195]. |
| O estoque dos itens vendidos deve ser reduzido. |

---

### Caso de Teste 02: Criar venda a prazo (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT03 | Registrar uma nova venda com a "Condição Venda: PRAZO", gerando uma conta a receber. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Venda". |
| Deve existir um cliente com limite de crédito habilitado (conforme Rotina 4)[cite: 2208]. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Venda" e clica em "Novo" [cite: 810] |
| **E** preenche o "Cliente", "Funcionário" e define a "Condição: PRAZO" [cite: 2380] |
| **E** clica em "Salvar" |
| **E** adiciona um ou mais produtos à venda |
| **E** clica em "Finalizar" [cite: 969] |
| **E** na tela "Confirmar Venda", muda o "Status" para "CONFIRMADA" [cite: 2380] |
| **E** não adiciona "Tipo de Documento" (pois é a prazo) |
| **QUANDO** o usuário clicar em "Salvar" [cite: 2380, 2407] |
| **ENTÃO** a venda será registrada como "CONFIRMADA" |
| **E** o sistema deve abrir a tela de "Contas a Receber" para gerar a pendência[cite: 2411]. |

| **Critérios de aceitação** |
| :--- |
| A venda deve ser confirmada. |
| O sistema deve automaticamente direcionar para a tela "Contas a Receber"[cite: 2411]. |
| O valor da venda deve constar como "Total a Receber" para o cliente[cite: 2444]. |

---

### Caso de Teste 03: Tentar criar venda sem preencher campos obrigatórios (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT04 | O sistema não deve permitir salvar uma nova venda sem um Cliente selecionado. |

| **Pré-condições** |
| :--- |
| O usuário está na tela de Venda. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Venda" e clica em "Novo" [cite: 810] |
| **E** o campo "Cliente" está vazio |
| **E** preenche o "Funcionário" [cite: 866-867] |
| **QUANDO** o usuário clicar em "Salvar" [cite: 884] |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Cliente é obrigatório") |
| **E** a venda não deve ser criada. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro de validação de campo deve ser exibida. |
| A venda não deve ser salva e o "Status" deve permanecer "NÃO CONFIRMADA". |

---

### Caso de Teste 04: Tentar finalizar venda sem adicionar produtos (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT05 | O sistema não deve permitir finalizar uma venda que não contenha nenhum item. |

| **Pré-condições** |
| :--- |
| O usuário está na tela de Venda. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Venda" e clica em "Novo" [cite: 810] |
| **E** preenche o "Cliente" e "Funcionário" e clica em "Salvar" [cite: 884] |
| **E** a lista "Entrada de Produtos" está vazia |
| **QUANDO** o usuário clicar em "Finalizar" [cite: 969] |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Venda sem itens") |
| **E** a tela "Confirmar Venda" não deve ser aberta. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro informando a falta de itens deve ser exibida. |
| A venda deve permanecer "NÃO CONFIRMADA". |