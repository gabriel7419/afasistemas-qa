## Cenário 05: Rotina de Caixa (CRUD - Delete).

### Caso de Teste 01: Conciliação de Saída (Retirada) (Positivo).

| ID | Descrição |
| :--- | :--- |
| R05-CT13 | Validar que a operação "Retirar Valores" (R05-CT02) subtraiu (deletou) o valor do saldo total do caixa. |

| **Pré-condições** |
| :--- |
| Saldo anterior à retirada era R$3.675,00. |
| Foi feita uma retirada de R$650,00. |

| **Passos** |
| :--- |
| **DADO** que o saldo era R$3.675,00 |
| **E** uma "Retirada do Caixa" de R$650,00 foi criada |
| **QUANDO** o usuário visualiza o histórico do "Livro Caixa" |
| **ENTÃO** a linha da retirada deve mostrar R$650,00 na coluna "Saída" |
| **E** o "Saldo" final deve ser R$3.025,00 (R$3.675,00 - R$650,00). |

| **Critérios de aceitação** |
| :--- |
| O saldo do caixa deve refletir a subtração (deleção) do valor retirado. |

---

### Caso de Teste 02: Conciliação de Saída (Troco) (Positivo).

| ID | Descrição |
| :--- | :--- |
| R05-CT14 | Validar que o "Troco" de uma venda foi registrado como uma "Saída" no "Livro Caixa". |

| **Pré-condições** |
| :--- |
| Uma venda foi finalizada e gerou "Troco para o Cliente" (ex: R$75,00). |

| **Passos** |
| :--- |
| **DADO** que uma venda gerou R$75,00 de troco |
| **QUANDO** o usuário visualiza o histórico do "Livro Caixa" |
| **ENTÃO** deve existir uma linha "Troco para o Cliente: JOSE SILVA - 3" |
| **E** o valor (R$75,00) deve estar na coluna "Saída". |

| **Critérios de aceitação** |
| :--- |
| O troco deve ser tratado como uma saída (redução) do saldo do caixa. |

---

### Caso de Teste 03: Tentar estornar (deletar) uma linha de Venda do "Livro Caixa" (Negativo).

| ID | Descrição |
| :--- | :--- |
| R05-CT15 | O sistema não deve permitir a exclusão manual de uma linha de Venda do histórico do "Livro Caixa". |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa". |
| Existe uma linha de "Venda para o Cliente...". |

| **Passos** |
| :--- |
| **DADO** que o usuário seleciona a linha da Venda no histórico |
| **QUANDO** o usuário tenta deletar a linha (ex: pressionando "Delete" ou procurando um botão de excluir) |
| **ENTÃO** o sistema não deve permitir a ação |
| **E** nenhuma mensagem de erro é necessária se a funcionalidade não existir. |

| **Critérios de aceitação** |
| :--- |
| O registro da venda deve permanecer intacto no "Livro Caixa". (A única forma de estornar seria via "Devolução" na Rotina de Venda). |

---

### Caso de Teste 04: Tentar estornar (deletar) uma "Retirada do Caixa" após o fechamento (Negativo).

| ID | Descrição |
| :--- | :--- |
| R05-CT16 | O sistema não deve permitir o cancelamento de uma retirada de um caixa que já foi fechado. |

| **Pré-condições** |
| :--- |
| O "Caixa Aberto" está "Não". |
| O histórico do dia anterior (agora fechado) mostra uma "Retirada do Caixa". |

| **Passos** |
| :--- |
| **DADO** que o usuário está visualizando o histórico de um caixa fechado |
| **E** seleciona a linha "Retirada do Caixa" |
| **QUANDO** o usuário tenta cancelar ou estornar esta linha |
| **ENTÃO** o sistema não deve permitir a ação |
| **E** deve exibir uma mensagem (ex: "Caixa fechado. Estorno não permitido"). |

| **Critérios de aceitação** |
| :--- |
| O histórico de um caixa fechado deve ser imutável. |