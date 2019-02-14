title: Objeto de negócio  

Description: Através dessa tela, é possível manter os objetos de negócio das aplicações. Objetos de negócio são os objetos armazenados no banco de dados da aplicação. Representam o modelo de dados e podem dar origem a um ou mais formulários.  

#Objeto de negócio   

Através dessa tela, é possível manter os objetos de negócio das aplicações. Objetos de negócio são os objetos armazenados no banco de dados da aplicação. Representam o modelo de dados e podem dar origem a um ou mais formulários.  

Todo objeto de negócio precisa possuir uma chave primária, no entanto, nem sempre a chave primária será criada no banco de dados. Os objetos de negócio são criados em nível de aplicação.  

Cada objeto de negócio criado representa uma tabela do banco de dados.  

##COMO ACESSAR  
1.	Acesse a funcionalidade através da navegação no menu Neuro > Gerenciamento > Objeto de Negócio.  

##PRÉ-CONDIÇÕES  
1.	Não se aplica.  

##FILTROS
1.	O seguinte filtro possibilita ao usuário restringir a participação de itens na listagem padrão da funcionalidade, facilitando a localização dos itens desejados:    
    
    *	Palavra chave ou enter.    

![Screenshot](images/business-object-filter.png)  
Figura 1 - Tela de pesquisa de objetos de negócio cadastrados  

##LISTAGEM DE ITENS  
1.	Os seguintes campos cadastrais estão disponíveis ao usuário para facilitar a identificação dos itens desejados na listagem padrão da funcionalidade: Aplicação, Nome, Descrição, Conexão de Banco e Versão.    

![Screenshot](images/business-object-listing.png)  
Figura 2 - Tela de listagem de objetos de negócio cadastrados  

##PREENCHIMENTO DOS CAMPOS CADASTRAIS  
1.	Para alterar um objeto de negócio, clique em Editar;    
2.	Para criar um novo objeto de negócio, clique em Cadastrar.    

##IDENTIFICAÇÃO  
Esta aba deve ser alimentada como forma de identificação do objeto de negócio criado.    
1.	Informe a Aplicação para a qual está sendo criado o objeto de negócio (cadastrada no menu Neuro > Gerenciamento > Aplicação.    
2.	Informe o nome de identificação do objeto de negócio, a descrição, o propósito e marque se o sistema deverá gerar o formulário ao salvar;    
3.	Ao clicar em Gerar formulário ao salvar, o Neuro se encarregará de gerar um formulário baseando-se nas informações inseridas na aba banco de dados. Este formulário poderá ser editado posteriormente através do menu Neuro > Gerenciamento > Formulário.    

![Screenshot](images/business-object-identification.png)  
Figura 3 - Tela de cadastro/edição de objetos de negócio  

##BANCO DE DADOS
1.	Esta aba se refere a estrutura do banco de dados da aplicação. Como cada objeto de negócio representa uma tabela do banco de dados, nesta aba são definidas as colunas do banco de dados, assim como seus relacionamentos, regras de negócio e comandos SQL (caso necessário).    
2.	Primeiramente, informe a conexão de banco de dados criada, o nome do esquema do banco, o tipo, se view ou tabela, e o nome do objeto de negócio no banco de dados.    

![Screenshot](images/business-object-database.png)  
Figura 4 - Tela de criação/edição de objeto de negócio - Aba de "Banco de dados"  

##FORMULÁRIO
1.	Pode se alterar as labels dos atributos através da aba Labels, e poderá editar os campos da grid, através da aba de Grid.    
2.	Ao clicar no botão Editar formulário presente no cabeçalho da tela, será gerado um formulário para este objeto de negócio. Se não houver nenhum formulário para este objeto de negócio, será apresentado a aba lateral Campos. Se já existir um formulário previamente cadastrado vinculado a este formulário, será aberta a aba de Desenho da tela para este formulário.    
3.	Mais informações a respeito da criação de formulário pelo Neuro podem ser encontradas na documentação técnica.     

![Screenshot](images/business-object-form.png)  
Figura 5 - Tela de criação/edição de objeto de negócio - Aba de "Formulários"  

!!! tip "About"
    <b>Updated:</b>17/01/2019 - João Pelles Junior
