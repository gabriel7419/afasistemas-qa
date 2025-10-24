## Cenário 01: Inventário de Estoque.

## Casos de Teste Positivos

### Caso de Teste 01: Importação de XML com informações válidas.

| ID       | Descrição                                                                 |
| :------- | :------------------------------------------------------------------------ |
| C01-CT01 | O sistema deve permitir a importação de XML válidos. |

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
| O usuário deve estar logado e ter acesso ao módulo "Pedido" e "Importar XML de Compra". |

| **Passos**                                                                                |
| :----------------------------------------------------------------                         |
| **DADO** que o usuário acessa o menu "Pedidos";                                            |
| **E** seleciona "Importar XML de Compra";                                                  |
| **QUANDO** preencher os "Dados do Produto" corretamente e selecionar um arquivo XML válido;|
| **ENTÃO** os produtos a serem importados devem ser exibidos na tabela abaixo;              |

| **Critérios de aceitação**                                                                |
| :--------------------------------------------------------------                           |
| O sistema deve exibir os produtos importados e os dados necessários.                       |


---

### Caso de Teste 02: Cadastro de um Novo Produto Corretamente Cadastrado.

| ID       | Descrição                                                                       |
| :------- | :------------------------------------------------------------------------------ |
| C01-CT02 | O sistema deve permitir o cadastro correto dos itens . |

| **Pré-condições**                                                                            |
| :------------------------------------------------------------                                |
| O usuário deve estar logado no sistema e ter acesso ao menu de cadatros.                     |

| **Passos**                                                                                    |
| :----------------------------------------------------------------                             |
| **DADO** o usuário acessa o menu "Cadastros"                                                  |
| **E** preenche os dados corretamente no formulário                                            |
| **QUANDO** na tela de Cadastro de "Protudos"                                                  |
| **ENTÃO** o sistema deve confirmar o cadastro e exibir o novo item na seleção de produtos     |

| **Critérios de aceitação**                                        |
| :--------------------------------------------------------------   |
| O item cadastrado deve ser exibido na lista de itens cadastrados. |


---

## Casos de Teste Negativos

### Caso de Teste 03: Exportar relatório gerado em PDF.

| ID       | Descrição                                                               |
| :------- | :---------------------------------------------------------------------- |
| C08-CT03 | O sistema deve permitir exportar um relatório gerado no formato PDF.    |

| **Pré-condições**                                             |
| :------------------------------------------------------------ |
| Um relatório deve ter sido gerado previamente.                |

| **Passos**                                                        |
| :---------------------------------------------------------------- |
| **DADO** que o usuário visualiza um relatório na tela           |
| **QUANDO** clicar na opção \"Export to PDF\"                    |
| **ENTÃO** o relatório deve ser baixado em formato PDF           |

| **Critérios de aceitação**                                      |
| :-------------------------------------------------------------- |
| O download do arquivo PDF deve ocorrer com os dados exibidos na tela. |

**TESTE EVIDENCIADO E REPROVADO**
[https://jam.dev/c/68508551-7504-48b7-be66-9315e47626b6]