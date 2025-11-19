## Cenário 02: Rotina de Venda (CRUD - Create).

### Caso de Teste 01: Criar venda à vista com pagamento misto (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT01 |  Registrar uma nova venda à vista com 5 itens, aplicar desconto geral e finalizar com pagamento misto (Cartão + Dinheiro). |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para acessar o menu "Venda". |
| O caixa deve estar aberto. |
| Devem existir 5 produtos com estoque positivo. |

| **Passos** |
| :--- |
|  **DADO** que o usuário está na tela "Venda" e clica em "Novo" |
|  **E** preenche o "Cliente", "Funcionário" e "Condição: VISTA" e clica em "Salvar" |
|  **E** adiciona 5 produtos diferentes à venda |
|  **E** clica em "Finalizar" |
|  **E** na tela "Confirmar Venda", aplica um "Desconto" (ex: 10%) |
|  **E** adiciona um "Tipo de Documento" (ex: CARTÃO CREDITO) com 70% do valor |
|  **E** adiciona um segundo "Tipo de Documento" (ex: DINHEIRO) com os 30% restantes |
|  **E** muda o "Status" para "CONFIRMADA" |
|  **QUANDO** o usuário clicar em "Salvar" |
|  **ENTÃO** a venda será registrada como "CONFIRMADA" |
|  **E** o estoque dos 5 produtos será debitado. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve exibir "Status da Venda: CONFIRMADA" na tela principal. |
| A "Diferença" na tela de confirmação deve ser "R$0,00". |
| O estoque dos itens vendidos deve ser reduzido. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/da983cd84de54f6ea1f4a90e20f64dfb]

---

### Caso de Teste 02: Criar venda a prazo (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT03 | Registrar uma nova venda com a "Condição Venda: PRAZO", gerando uma conta a receber. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Venda". |
| Deve existir um cliente com limite de crédito habilitado. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Venda" e clica em "Novo" |
| **E** preenche o "Cliente", "Funcionário" e define a "Condição: PRAZO" |
| **E** clica em "Salvar" |
| **E** adiciona um ou mais produtos à venda |
| **E** clica em "Finalizar" |
| **E** na tela "Confirmar Venda", muda o "Status" para "CONFIRMADA" |
| **E** não adiciona "Tipo de Documento" (pois é a prazo) |
| **QUANDO** o usuário clicar em "Salvar"|
| **ENTÃO** a venda será registrada como "CONFIRMADA" |
| **E** o sistema deve abrir a tela de "Contas a Receber" para gerar a pendência. |

| **Critérios de aceitação** |
| :--- |
| A venda deve ser confirmada. |
| O sistema deve automaticamente direcionar para a tela "Contas a Receber". |
| O valor da venda deve constar como "Total a Receber" para o cliente. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/a914e43ec76d40e48edb9aed86910818]

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
| **DADO** que o usuário está na tela "Venda" e clica em "Novo" |
| **E** o campo "Cliente" está vazio |
| **E** preenche o "Funcionário" |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro  |
| **E** a venda não deve ser criada. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro de validação de campo deve ser exibida. |
| A venda não deve ser salva e o "Status" deve permanecer "NÃO CONFIRMADA". |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/fbd966c8863545d28aa5a2ad3cc8d35b]
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
| **DADO** que o usuário está na tela "Venda" e clica em "Novo" |
| **E** preenche o "Cliente" e "Funcionário" e clica em "Salvar"|
| **E** a lista "Entrada de Produtos" está vazia |
| **QUANDO** o usuário clicar em "Finalizar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro |
| **E** a tela "Confirmar Venda" não deve ser aberta. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de alerta informando a falta de itens deve ser exibida. |
| A venda deve permanecer "NÃO CONFIRMADA". |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E NO LOOM**
[https://www.loom.com/share/6cda4050e0ca48b1916e8de0a9be67aa]