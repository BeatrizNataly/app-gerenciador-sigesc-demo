# Gerenciador de Serviços e Clientes (DEMO)
Demonstração de aplicação mobile com banco de dados, capaz de gerenciar lista de clientes, categoria de serviço e serviços solicitados.

## Funcionalidades:
O aplicativo permite manipular as listas da seguinte forma:
  * Cliente: Criar cliente, editar informações do cliente (exceto RG e CPF), alterar status do cliente de 'Ativo' para 'Inativo', pesquisar informações na lista de clientes.
  * Categoria: Criar categoria e excluir categoria.
  * Serviços: Criar serviço, associar categoria e cliente a ele, editar serviço, alterar status do serviço de 'Pendente' para 'Concluído' ou 'Cancelado', excluir serviço e pesquisar informações na lista de serviços.

## Como usar:
* Baixe a versão mais recente do projeto: As versões são enviadas em .zip indicadas como 'NomeProjeto-Data', ex: 'Pedidos-10.06', baixe a mais atual de acordo com a data que estará acessando o repositório.
* Descompacte o zip e abra o projeto em um editor, de preferência Android Studio para que possa utilizar o emulador dele.
* A primeira lista aberta será a de Clientes. No canto superior direito você verá dois icones.
* O ícone de **lousa** abre a lista de **serviços** e o ícone de **formas geométricas** abre a lista de **categorias**.
* Tanto na lista de clientes como de serviços é possível adicionar um novo item a lista clicando no botão azul no canto inferior direito com símbolo de **+**.

## Adicionando clientes à lista:
* Abra a tela na lista de Clientes. O nome da tela aparecerá no canto superior esquerdo da tela.
* Após clicar no botão azul esverdeado no canto inferior da tela, deverá ser aberto um formulário. Nesse formulário são obrigatórios os campos: Nome, CPF e RG.
* Você pode preencher o formulário da forma que preferir, respeitando os campos obrigatórios e o limite de caracteres (RG aceita até 9 números sem traços ou pontuação, CPF aceita 11 números sem traços ou pontuação.)
* Você pode salvar o novo cliente apertando o botão 'Salvar' no fim do formulário, ou no canto superior direito da tela.
* Caso aja algum cliente na sua lista com o mesmo CPF e/ou RG do formulário, o programa não deixará que prossiga com o salvamento.
* Ao clicar em editar um cliente o programa abrirá o formulário com as informações dele. Note que você não poderá alterar o rg e cpf do cliente, já que são informações imutáveis.

## Adicionando categorias à lista:
* Abra a tela de categorias
* Digite o nome da nova categoria na barra de adição
* Clique em "OK"
* Note que o sistema não permite adicionar categorias vazias.

## Adicionando serviços à lista:
* Abra a tela de serviços
* Clique no botão + no canto inferior da tela, ela deverá abrir um formulário
* Note que são obrigatórios um cliente e uma categoria para se criar o serviço, no formulário você deverá dar uma descrição ao serviço e atribuir uma data e horário.
* Você pode adicionar a lista clicando em 'Salvar' no final do formulário ou no canto superior direito.
* Caso já exista um pedido pendente com mesma data e hora na lista, o programa solicitará correções antes de salvar.
* Você pode editar todos os aspectos do serviço após criado, **desde que esse serviço esteja com status de conclusão 'Pendente'**
* Você pode alterar o status de conclusão do pedido para "Concluído" clicando no ícone de checklist no rodapé do pedido ou "Cancelado" clicando no ícone de X no rodapé.
