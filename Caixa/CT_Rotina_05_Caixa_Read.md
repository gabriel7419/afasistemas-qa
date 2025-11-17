## Cenário 05: Rotina de Caixa (CRUD - Read).

### Caso de Teste 01: Ler (visualizar) o histórico de movimentações (Positivo).

| ID | Descrição |
| :--- | :--- |
| R05-CT05 | O usuário visualiza o histórico de todas as transações (abertura, vendas, retiradas) do dia no "Livro Caixa". |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa". |
| Várias operações (Abertura, Vendas, Retirada) foram realizadas. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Livro Caixa" |
| **QUANDO** o usuário inspeciona o grid de histórico |
| **ENTÃO** o sistema deve exibir, em ordem cronológica, todas as transações |
| **E** deve incluir "SALDO DA ABERTURA DO CAIXA" (Entrada) |
| **E** deve incluir "Venda para o Cliente..." (Entrada) |
| **E** deve incluir "Retirada do Caixa..." (Saída). |

| **Critérios de aceitação** |
| :--- |
| O histórico deve refletir com precisão todas as operações do caixa com "Hora", "Histórico", "Entrada", "Saída" e "Saldo" corretos. |

---

### Caso de Teste 02: Gerar e ler relatório de conciliação (Positivo).

| ID | Descrição |
| :--- | :--- |
| R05-CT06 | Gerar o relatório de "Movimentações e Cheque/Cartão/Produto" para conciliar os totais de venda. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa". |
| Vendas com diferentes "Tipos de Documento" (Dinheiro, Cheque) foram realizadas. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Livro Caixa" |
| **E** clica em "Imprimir Caixa" |
| **E** seleciona "Movimentações e Cheque/Cartão/Produto" |
| **E** clica em "Confirmar" na tela de impressão |
| **QUANDO** o relatório é exibido |
| **ENTÃO** o "Resumo por Tipo de Documento" deve mostrar os totais corretos para "CHEQUE" e "DINHEIRO" |
| **E** o total de "Venda de Produto por Grupo" (ex: R$1.425,00) deve ser exibido corretamente. |

| **Critérios de aceitação** |
| :--- |
| O relatório deve ser gerado com sucesso e os valores devem bater com as vendas registradas. |

---

### Caso de Teste 03: Tentar ler relatório de conferência sem dados (Negativo).

| ID | Descrição |
| :--- | :--- |
| R05-CT07 | O sistema exibe um relatório vazio se nenhuma venda foi realizada. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa". |
| O caixa foi aberto, mas nenhuma venda ou retirada foi feita. |

| **Passos** |
| :--- |
| **DADO** que o usuário está no "Livro Caixa" sem movimentações |
| **E** clica em "Imprimir Caixa" |
| **E** seleciona "Movimentações e Cheque/Cartão/Produto" e "Confirmar" |
| **QUANDO** o relatório é exibido |
| **ENTÃO** o "Resumo por Tipo de Documento" e "Venda de Produto" devem estar zerados (ou exibir R$0,00). |

| **Critérios de aceitação** |
| :--- |
| O relatório deve ser gerado, mas sem valores de movimentação, exceto a abertura (se aplicável ao relatório). |

---

### Caso de Teste 04: Ler saldo do dia anterior após fechar caixa (Negativo).

| ID | Descrição |
| :--- | :--- |
| R05-CT08 | O saldo do "Livro Caixa" deve ser R$0,00 após o fechamento, indicando que o dia foi encerrado. |

| **Pré-condições** |
| :--- |
| O usuário acabou de realizar um "Fechar Caixa". |
| O status é "Caixa Aberto: Não". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Livro Caixa" e o caixa está fechado |
| **QUANDO** o usuário visualiza os totalizadores na parte inferior da tela |
| **ENTÃO** os campos "Entrada", "Saída" e "Saldo" devem ser "R$ 0,00". |

| **Critérios de aceitação** |
| :--- |
| O sistema não deve exibir os totais do dia anterior; deve mostrar os contadores zerados, prontos para a próxima abertura. |