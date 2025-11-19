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

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO LOOM E DRIVE**
[https://www.loom.com/share/6e57d0a9f2c1450caaf9ba14561bfca7]

---

### Caso de Teste 02: Pagar parcela parcialmente (Positivo).

| ID | Descrição |
| :--- | :--- |
| R03-CT10 | Realizar o pagamento parcial da segunda parcela, redistribuindo o restante. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Desdobramento da Conta". |
| A primeira parcela foi paga. |
| O valor da segunda parcela é pago de forma parcial. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Desdobramento da Conta" |
| **E** na linha da segunda parcela, altera o "Valor Parcela" para um valor menor |
| **E** seleciona o "Tipo Documento" e clica em "Confirmar" |
| **QUANDO** o sistema processa o pagamento parcial |
| **ENTÃO** o valor restante deve ser automaticamente somado às parcelas futuras |
| **E** o "Valor Parcela" da parcela "03" deve ser recalculado. |

| **Critérios de aceitação** |
| :--- |
| O pagamento parcial da parcela 02 deve ser registrado. |
| O valor das parcelas subsequentes deve ser atualizado para refletir o saldo devedor. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO LOOM E DRIVE**
[https://www.loom.com/share/5ba33c627a4b434f84dea28d7a6847e9]

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

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO LOOM E DRIVE**
[https://www.loom.com/share/5338fb63b89e479c968faf1947d98765]

---