Title: Formulário  
Description: Nesta página são mantidos os formulários criados através do Neuro.  

#Formulário  
Nesta página são mantidos os formulários criados através do Neuro.   
Os formulários podem ser criados manualmente, ou gerados através do Objeto de negócio.    

##COMO ACESSAR  
1- Acesse a funcionalidade através do menu Neuro → Gerenciamento → Formulário.   

##PRÉ-CONDIÇÕES    
1- Não se aplica.    

##FILTROS    
1- O seguinte filtro possibilita ao usuário restringir a participação de itens na listagem padrão da funcionalidade, facilitando a localização dos itens desejados:    
- Palavra chave ou enter.    

![Screenshot](images/Form-Search.png)   
Figura 1 - Tela de pesquisa de formulário    

#LISTAGEM DE ITENS  
1- Os seguintes campos cadastrais estão disponíveis ao usuário para facilitar a identificação dos itens desejados na listagem padrão da funcionalidade: Aplicação, Nome e Descrição.     

![Screenshot](images/Form-Listing.png)  
Figura 2 - Tela de listagem de formulário  

##PREENCHIMENTO DOS CAMPOS CADASTRAIS  
1- Para criar um novo formulário, clique em Cadastrar.  

DADOS BÁSICOS

1- Nesta aba deverão ser informados os dados básicos dos formulários, como a aplicação ao qual o formulário pertence, o nome, descrição, Regras de negócio (caso houver), e a pasta, que é um agrupador físico dos formulários no servidor, para fins de organização. A pasta configurada não interfere no funcionamento do sistema.    
2- O campo versão é incrementado automaticamente pelo sistema sempre que uma nova versão do formulário for criada.    
3- Adicionar/Remover páginas: refere-se ao tipo de página que será criada utilizando o formulário. Existem os seguintes tipos no Neuro:    
- **Default page**: busca o que tem no banco e cadastra diretamente no mesmo. Funciona muito bem para telas que tem a função de CRUD. Gera a aba Página default.    
- **Process page**:  Design Workflows/ESI precisam de processo de negócio. É a primeira página que será utilizada ao executar um fluxo. Gera a aba Página p/ processo.    
- **Page for task**: Página para tarefas humanas que são executadas através de um Design Workflows/ESI criado. Gera a aba Página p/ tarefa.  
- **Report page**: Página para relatórios gerados pela aplicação. Gera a aba Página p/ tarefa.  
- **ITSM process page**: Página para processos do sistema ITSM associados a processos de negócio.  
- **ITSM Task Page**: Página para tarefas humanas que são executadas através de um workflow criado para o ITSM. Gera a aba Página p/ tarefa.  

4- As abas geradas possuem a seguinte estrutura:    
- **HTML**: estrutura html da página;    
- **HTML mobile**: estrutura html para dispositivos móveis;  
- **Controller**: código do controller referente ao formulário;  
- **Dependencies**: são informadas as dependências da aplicação. Deverão ser informados o nome da dependência e o path na qual a mesma se encontra. Informe também se será injetada no controller.      

![Screenshot](images/Form-business.png)    
Figura 3 - Tela de cadastro/edição de formulários, aba "Dados básicos"   

![Screenshot](images/Form-business2.png) 
Figura 4 - Tela de cadastro/edição de formulários, aba "Código compartilhado"    

##DESENHANDO A TELA    
1- Para criar o desenho da tela, clique em Editar tela ou navegue até a aba do sistema Desenho de tela que é aberta automaticamente.    
2- Arraste os componentes localizados na paleta lateral esquerda para o centro de acordo com a forma que desejar construir o formulário. Os componentes são organizados em linhas e colunas na tela, sendo que as linhas possuem largura de 12 colunas. Isso significa que em cada linha você poderá inserir até 2 componentes com largura 6, ou até 3 componentes com largura 4, por exemplo. Você não precisa necessariamente preencher todo o tamanho disponível na linha.    
3- É possível também criar abas nos formulários. Para isso, acesse o menu Abas, e escolha abas na horizontal ou na vertical. As abas serão adicionadas na tela, e você poderá desenhar a tela com os componentes em cada aba.    
4- Além disso, o Neuro contempla um mecanismo para que sejam adicionadas ações na barra de ferramentas superior da aplicação. Para isso, clique no botão localizado na barra superior.  
5- Para saber mais sobre os componentes dos formulários, acesse o conhecimento Desenvolvendo aplicações.    
6- Para visualizar o resultado do seu formulário, clique na opção Visualizar tela localizada na barra superior.    
7- Clique em Salvar para executar as alterações. Você poderá salvar na versão original (versão atual), ou em uma nova versão.   

![Screenshot](images/Form-screen-design.png)   
Figura 5 - Tela de cadastro/edição de formulários, tela de desenho das telas    

##JS PARA VISUALIZAÇÃO    
1- Esta aba tem a funcionalidade de adicionar variáveis no escopo do Javascript na tela que se abre quando se clica no botão Visualizar tela. Mais informações podem ser encontradas na Desenvolvendo aplicações.    

![Screenshot](images/Form-JS.png)  
Figura 6 - Tela de cadastro/edição de formulários, aba "JS para visualização"    

!!! tip "About"
    <b>Updated:</b>17/01/2019 - João Pelles Junior
