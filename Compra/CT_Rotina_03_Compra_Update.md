## Cenário 03: Rotina de Compra (CRUD - Update).

### Caso de Teste 01: Confirmar pedido de compra (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT09 | Alterar o status de um pedido de compra de "NÃO CONFIRMADA" para "CONFIRMADA". |

| **Pré-condições** |
| :--- |
| Existe um pedido de compra "NÃO CONFIRMADA" (ex: Número "10"). |
| O usuário está na tela deste pedido de compra. |

| **Passos** |
| :--- |
| **DADO** que o usuário localizou a compra "10" |
| **E** clica em "Finalizar" |
| **E** na tela "Confirmar Compra", muda o "Status" para "CONFIRMADA" |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** o sistema deve salvar a alteração |
| **E** (se for à vista) os produtos devem entrar no estoque |
| **E** (se for a prazo) a tela "Contas a Pagar" deve ser aberta. |

| **Critérios de aceitação** |
| :--- |
| O status da compra deve ser "CONFIRMADA". |
| O fluxo de pagamento (à vista ou a prazo) deve ser iniciado. |

---

### Caso de Teste 02: Pagar parcela parcialmente (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT10 | Realizar o pagamento parcial da segunda parcela, redistribuindo o restante. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Desdobramento da Conta". |
| A primeira parcela foi paga. |
| O valor da segunda parcela é (ex: R$550,00). |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Desdobramento da Conta" |
| **E** na linha da segunda parcela, altera o "Valor Parcela" para um valor menor (ex: R$225,00) |
| **E** seleciona o "Tipo Documento" e clica em "Confirmar" |
| **QUANDO** o sistema processa o pagamento parcial |
| **ENTÃO** o valor restante (R$325,00) deve ser automaticamente somado às parcelas futuras |
| **E** o "Valor Parcela" da parcela "03" deve ser recalculado (ex: R$658,33). |

| **Critérios de aceitação** |
| :--- |
| O pagamento parcial da parcela 02 deve ser registrado. |
| O valor das parcelas subsequentes deve ser atualizado para refletir o saldo devedor. |

---

### Caso de Teste 03: Tentar alterar pedido de compra confirmado (Negativo).

| ID | Descrição |
| :--- | :--- |
| R03-CT11 | O sistema não deve permitir a alteração de um pedido de compra que já foi "CONFIRMADO". |

| **Pré-condições** |
| :--- |
| Existe um pedido de compra com status "CONFIRMADA". |

| **Passos** |
| :--- |
| **DADO** que o usuário localizou a compra "CONFIRMADA" |
| **QUANDO** o usuário clica no botão "Alterar" |
| **ENTÃO** o botão deve estar desabilitado |
| **OU** o sistema deve exibir uma mensagem (ex: "Compra confirmada não pode ser alterada"). |

| **Critérios de aceitação** |
| :--- |
| O sistema deve impedir a alteração dos dados ou itens da compra. |

---

### Caso de Teste 04: Tentar pagar valor maior que a parcela (Negativo).

| ID | Descrição |
| :--- | :--- |
| R03-CT12 | O sistema não deve permitir o pagamento de um valor maior que o devido na parcela. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Desdobramento da Conta". |
| O valor da parcela "01" é R$550,00. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Desdobramento da Conta" |
| **E** no campo "Valor Parcela" da parcela "01", digita "R$600,00" |
| **QUANDO** o usuário tenta clicar em "Confirmar" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Valor maior que o saldo da parcela") |
| **E** o pagamento não deve ser processado. |

| **Critérios de aceitção** |
| :--- |
| Uma mensagem de erro de validação de valor deve ser exibida. |
| O pagamento não deve ser confirmado. |