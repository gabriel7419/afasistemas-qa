## Cenário 01: Rotina de Inventário de Estoque (Importação).

### Caso de Teste 01: Importar XML de compra e confirmar estoque (Positivo).

| ID | Descrição |
| :--- | :--- |
| R01-CT01 | Importar um XML de NFe válido e confirmar a entrada dos produtos, atualizando o estoque. |

| **Pré-condições** |
| :--- |
| O usuário deve ter um arquivo XML de NFe válido. |
| O usuário deve ter permissão para acessar o menu "Pedido". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela inicial do sistema |
| **E** navega para "Pedido" > "Importar XML de Compra" |
| **E** clica em "Importar XML" e seleciona um arquivo XML válido |
| **E** clica em "Gerar Compra" após os itens serem carregados |
| **E** na tela de "Compra", clica em "Finalizar" |
| **E** na tela "Confirmar Compra", muda o "Status" para "CONFIRMADA" |
| **E** preenche o "Tipo de Documento" (ex: BOLETO) e salva |
| **QUANDO** o usuário clicar em "Salvar" na tela de "Confirmar Compra" |
| **ENTÃO** a compra será registrada como "Confirmada" |
| **E** os itens importados serão adicionados ao estoque do sistema. |

| **Critérios de aceitação** |
| :--- |
| O "Status da Compra" na tela principal de Compra deve mudar para "CONFIRMADA". |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE**
[https://www.loom.com/share/02d1fa537eba4b969eed06a7ca65d421]

---

### Caso de Teste 02: Tentar importar arquivo inválido (Negativo).

| ID | Descrição |
| :--- | :--- |
| R01-CT02 | O sistema não deve permitir a importação de um arquivo que não seja um XML válido. |

| **Pré-condições** |
| :--- |
| O usuário deve ter um arquivo inválido/corrompido. |
| O usuário deve ter permissão para acessar o menu "Pedido". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela inicial do sistema |
| **E** navega para "Pedido" > "Importar XML de Compra" |
| **E** clica em "Importar XML" |
| **QUANDO** o usuário seleciona um arquivo em outro formato ou corrompido e clica em "Abrir" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro informando que o arquivo é inválido |
| **E** os "Produtos no XML" não devem ser carregados. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro (ex: "Arquivo XML inválido" ou "Formato não suportado") deve ser exibida. |
| A lista "Produtos no XML" deve permanecer vazia. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/07e46d5493b149c2839ca054d9fb5b8e]