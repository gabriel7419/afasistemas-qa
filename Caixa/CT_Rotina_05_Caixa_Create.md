## Cenário 05: Rotina de Caixa (CRUD - Create).

### Caso de Teste 01: Abrir o caixa com saldo inicial (Positivo).

| ID | Descrição |
| :--- | :--- |
| R05-CT01 | Iniciar o dia abrindo o "Livro Caixa" com um saldo inicial (ex: R$2.500,00). |

| **Pré-condições** |
| :--- |
| O usuário deve ter permissão para acessar o "Livro Caixa". |
| O caixa deve estar fechado ("Caixa Aberto: Não"). |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Livro Caixa" e o caixa está fechado |
| **E** clica no botão "Abrir Caixa" |
| **E** insere o "Saldo" inicial (ex: R$2.500,00) |
| **QUANDO** o usuário clicar em "Salvar" na tela de abertura |
| **ENTÃO** o "Caixa Aberto" deve mudar para "Sim" |
| **E** a primeira linha no histórico deve ser "SALDO DA ABERTURA DO CAIXA NO DIA" com o valor de entrada. |

| **Critérios de aceitação** |
| :--- |
| O status do caixa deve ser "Aberto: Sim". |
| O saldo inicial deve constar como a primeira entrada no histórico do "Livro Caixa". |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/b8a338a83ee34713a95e5f49b81915ef]

---

### Caso de Teste 02: Criar (registrar) uma retirada de valores (Positivo).

| ID | Descrição |
| :--- | :--- |
| R05-CT02 | Realizar uma retirada de valor (sangria) do caixa que está aberto. |

| **Pré-condições** |
| :--- |
| O "Caixa Aberto" deve estar "Sim". |
| O saldo em "DINHEIRO" no caixa deve ser suficiente para a retirada. |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Livro Caixa" com o caixa aberto |
| **E** clica no botão "Retirar Valores" |
| **E** clica em "Novo" na tela de "Retirada de Valores" |
| **E** preenche o "Valor" (ex: R$650,00), "Tipo de Documento: DINHEIRO |
| **QUANDO** o usuário clicar em "Salvar" |
| **ENTÃO** a retirada deve ser registrada no histórico do "Livro Caixa" |
| **E** o valor deve ser lançado na coluna "Saída", atualizando o "Saldo". |

| **Critérios de aceitação** |
| :--- |
| Uma linha "Retirada do Caixa: 3" (ou similar) deve aparecer no histórico. |
| O "Saldo" total do caixa deve ser reduzido no valor da retirada. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/41b30349a91c4c2c8ff462d2268a5a08]

---

### Caso de Teste 03: Tentar abrir um caixa que já está aberto (Negativo).

| ID | Descrição |
| :--- | :--- |
| R05-CT03 | O sistema não deve permitir que o usuário abra um segundo caixa se um já estiver "Aberto: Sim". |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa". |
| O status é "Caixa Aberto: Sim". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Livro Caixa" e o caixa está aberto |
| **QUANDO** o usuário clica no botão "Abrir Caixa" |
| **ENTÃO** o sistema deve desabilitar o botão. |
| **E** nenhuma nova tela de abertura deve aparecer. |

| **Critérios de aceitação** |
| :--- |
| O botão de Abrir Caixa deve estar desabilitado |
| O status do caixa e o saldo devem permanecer inalterados. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/e98d005e30ab4d7797a001f10cc68242]
---

### Caso de Teste 04: Tentar retirar valores com o caixa fechado (Negativo).

| ID | Descrição |
| :--- | :--- |
| R05-CT04 | O sistema não deve permitir o acesso à função "Retirar Valores" se o caixa estiver fechado. |

| **Pré-condições** |
| :--- |
| O usuário está na tela "Livro Caixa". |
| O status é "Caixa Aberto: Não". |

| **Passos** |
| :--- |
| **DADO** que o usuário está na tela "Livro Caixa" e o caixa está fechado |
| **QUANDO** o usuário clica no botão "Retirar Valores" |
| **ENTÃO** o botão deve estar desabilitado |
| **OU** o sistema deve exibir uma mensagem de erro. |

| **Critérios de aceitação** |
| :--- |
| O sistema deve impedir a criação de uma retirada com o caixa fechado. |

**CENÁRIO TESTADO E EVIDENCIADO - DISPONÍVEL NO DRIVE E LOOM**
[https://www.loom.com/share/2aaf7bba859b4a0188c7f6f7159084a5]