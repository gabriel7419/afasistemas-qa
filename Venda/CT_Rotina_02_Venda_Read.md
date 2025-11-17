## Cenário 02: Rotina de Venda (CRUD - Read).

### Caso de Teste 01: Consultar venda confirmada existente (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT06 | Buscar e visualizar os detalhes de uma venda já confirmada usando os controles de navegação. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Venda". |
| Deve existir uma venda "CONFIRMADA" (ex: Número "5")[cite: 1210]. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Venda" |
| **E** utiliza os botões de navegação (setas) ou busca para localizar a venda "5" [cite: 809] |
| **QUANDO** a venda "5" é carregada na tela |
| **ENTÃO** o "Status da Venda" deve ser "CONFIRMADA" [cite: 1241] |
| **E** todos os campos (Cliente, Itens, Total) devem estar corretos e bloqueados para edição [cite: 1211-1222]. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve exibir todos os dados da venda 5. |
| Os botões "Alterar", "Excluir" (itens) e "Finalizar" devem estar desabilitados. |

---

### Caso de Teste 02: Validar fechamento de caixa (conciliação) (Positivo).

| ID | Descrição |
| :--- | :--- |
| R02-CT07 |  Conferir os totais no Livro Caixa após a realização de vendas[cite: 771]. |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para "Livro Caixa". |
| Pelo menos uma venda com "DINHEIRO" e "CHEQUE" foi confirmada (Rotina 02, CT01) [cite: 2774-2775]. |

| **Passos** |
| :--- |
| **DADO** que o usuário realizou vendas durante o dia |
| **E** navega para a tela "Livro Caixa" [cite: 1256] |
| **E** clica em "Fechar Caixa" e depois em "Fazer Conferência" [cite: 1258, 1299] |
| **QUANDO** o usuário visualiza a tela de "Conferência de Caixa" |
| **ENTÃO** o "Valor no Caixa" para "DINHEIRO" e "CHEQUE" deve corresponder exatamente aos valores recebidos nas vendas [cite: 2773-2774]. |

| **Critérios de aceitação** |
| :--- |
| Os valores "Valor no Caixa" por tipo de documento devem bater com os valores das vendas confirmadas[cite: 2773]. |
| A conciliação do relatório (Rotina 5) deve ser validada com o caixa[cite: 2897]. |

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
| **E** digita "9999" no campo "Número" |
| **QUANDO** o usuário pressiona "Enter" ou sai do campo |
| **ENTÃO** o sistema deve exibir uma mensagem de erro (ex: "Venda não encontrada") |
| **E** os campos de cliente e itens devem permanecer vazios ou com dados da venda anterior. |

| **Critérios de aceitação** |
| :--- |
| Uma mensagem de erro informando que o registro não foi localizado deve ser exibida. |

---

### Caso de Teste 04: Tentar ler dados de conferência com caixa fechado (Negativo).

| ID | Descrição |
| :--- | :--- |
| R02-CT09 | O sistema não deve permitir a visualização da conferência de caixa se o caixa não estiver aberto. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa". |
| O "Caixa Aberto" está "Não"[cite: 1341]. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Livro Caixa" e o caixa está fechado [cite: 1341] |
| **QUANDO** o usuário clica em "Fechar Caixa" (para tentar acessar a conferência) |
| **ENTÃO** o sistema deve exibir uma mensagem (ex: "Caixa já está fechado") |
| **E** não deve permitir o acesso à tela de "Conferência de Caixa". |

| **Critérios de aceitação** |
| :--- |
| O sistema deve impedir o acesso à funcionalidade de conferência. |
| O usuário só pode "Abrir Caixa"[cite: 2602]. |