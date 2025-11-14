## Cenário 01: Rotina de Inventário de Estoque.

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
| **E** navega para "Pedido" > "Importar XML de Compra" [cite: 441] |
| **E** clica em "Importar XML" e seleciona um arquivo XML válido [cite: 477, 504] |
| **E** clica em "Gerar Compra" após os itens serem carregados [cite: 641] |
| **E** na tela de "Compra", clica em "Finalizar" [cite: 644] |
| **E** na tela "Confirmar Compra", muda o "Status" para "CONFIRMADA" [cite: 720, 739] |
| **E** preenche o "Tipo de Documento" (ex: BOLETO) e salva [cite: 752, 794] |
| **QUANDO** o usuário clicar em "Salvar" na tela de "Confirmar Compra" [cite: 831, 869] |
| **ENTÃO** a compra será registrada como "Confirmada" [cite: 873] |
| **E** os itens importados serão adicionados ao estoque do sistema. |

| **Critérios de aceitação** |
| :--- |
|  O "Status da Compra" na tela principal de Compra deve mudar para "CONFIRMADA"[cite: 877]. |

---

### Caso de Teste 02: Tentar importar arquivo inválido (Negativo).

| ID | Descrição |
| :--- | :--- |
| R01-CT02 | O sistema não deve permitir a importação de um arquivo que não seja um XML válido. |

| **Pré-condições** |
| :--- |
| O usuário deve ter um arquivo inválido (ex: `.txt` ou `.png`). |
| O usuário deve ter permissão para acessar o menu "Pedido". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela inicial do sistema |
|  **E** navega para "Pedido" > "Importar XML de Compra" [cite: 441] |
|  **E** clica em "Importar XML" [cite: 477] |
| **QUANDO** o usuário seleciona um arquivo `fatura.txt` ou `imagem.png` e clica em "Abrir" |
| **ENTÃO** o sistema deve exibir uma mensagem de erro informando que o arquivo é inválido |
|  **E** os "Produtos no XML" não devem ser carregados[cite: 485]. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro (ex: "Arquivo XML inválido" ou "Formato não suportado") deve ser exibida. |
| A lista "Produtos no XML" deve permanecer vazia. |