# Gerenciador de Serviços e Clientes (DEMO)
## Beatriz Nataly
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

## Vendo informações:
Ao clicar em um item da lista de clientes, será expandida uma tela com todas informações do cliente já cadastradas. O mesmo ocorre ao tocar em um serviço, ele exibe suas informações e permite que sejam visualizadas as do cliente associado.

## Clientes e categorias deletadas
Quando deletamos uma categoria ou serviço do nosso aplicativo ela é removida do banco de dados. Mas e se houver um serviço associado a elas??

Quando uma categoria é excluída, a categoria do serviço associado a ela é automaticamente atualizado para "Categoria inexistente" com uma tag cinza que indica que a categoria não existe mais. Caso o serviço ainda esteja pendente é possível alterar para uma nova categoria válida.

No caso do cliente ser deletado, ele só é excluído do banco de dados caso não haja nenhum serviço associado a ele, caso contrário ele tem seu status de cliente definido como 'Inativo' e é removido da lista de clientes, sendo possível ver suas informações apenas através do serviço em que ele ainda existe, com uma coloração cinza que indica que o cliente é inativo no sistema. Após o serviço que o cliente está associado deixar de existir, o cliente inativo também desaparecerá do banco, não sendo mais possível recuperar suas informações.

## Filtro de pesquisa:
O filtro de pesquisa utiliza queries buscando a informação diretamente no banco de dados, logo o filtro de busca até a atual versão (10.06.2022) não é case sensitive, buscando um conjunto de caracteres independente do caso.
Digitando sua busca e clicando "Pesquisar" o programa exibirá a lista dos resultados encontrados.
Ao buscar um termo que não existe a lista ficará vazia.
Para retornar a lista principal você pode reabrir a tela ou pesquisar uma pesquisa vazia: Apague sua última pesquisa e apenas clique 'Pesquisar' novamente.

#### Exemplos de resultado de busca para uma lista fictícia de serviços:
Cliente solicitante | Categoria | Data | Hora
--------------------|-----------|------|-----
Beatriz Nataly      |Develop    |01.01|12:00
Camilla Antonio Rui |UX Writing|01.01|13:00
Pabblo Agú|Develop|10.01|14:20
Romanato Marcel|Engenharia| 11.02|12:30

* Buscando "01.01" obtemos: Beatriz e Camilla
* Buscando "01" obtemos: Beatriz, Camilla e Pabblo
* Buscando "Develop" obtemos: Beatriz e Pabblo
* Buscando "L" obtemos: Beatriz, Camilla, Pabblo e Romanato (Pois todos possuem L em algum ponto de seu nome e/ou sobrenome).
* Buscando "12:45" não obtemos ninguém, pois ninguém tem essa data específica, apesar de terem datas com os números 12 ou 45.

## Menus:
O menu das telas é composto principalmente por ícones que realizam diferentes ações no programa.
Esses ícones possuem descrição para auxiliar pessoas com dificuldade visual, e títulos para melhorar sua compreensão para novos usuários.
Para ver o título de um botão do menu basta pressionar e segurar o botão, então seu título apareçerá abaixo do ícone como um texto simples com sombreamento preto.

#### Glossário de símbolos dos ícones:
##### Última alteração dos ícones feita em 13/jun/2022.

* Seta apontando para esquerda: Ícone que indica ação de "voltar". Quando localizado numa lista retornará para a lista inicial de clientes,
quando no menu de um formulário, retornará para a lista de origem daquele formulário, exemplo: Formulário de clientes + <- = Lista de clientes.
* Prancheta: O ícone de prancheta, lousa ou quadro de anotações leva para a lista de serviços.
* Pessoa com lupa: Esse ícone levará o usuário à lista de clientes.
* Formas geométricas: Esse ícone indica a tela com a lista de Categorias de Serviços, e levará o usuário até ela.
* Adicionar: O ícone flutuante de +, ou 'adicionar', abre um formulário. O formulário aberto dependerá da lista de origem.
* Marca de confirmação/checagem: Na lista de serviços, quando apertado muda o status de um serviço para 'Concluído'.
* Marca de X/errado: Na lista de serviços, quando apertado muda o status de um serviço para 'Cancelado'.
* Lixeira: Quando o símbolo de lixeira é pressionado, ele exclui o item ao qual ele se referia.
