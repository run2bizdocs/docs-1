Title: Workflow

# Workflow 2

Apresentação
-----------

Fluxos são representações visuais de algo que se move continuamente.
A funcionalidade de Fluxos tem a finalidade de modelar seus
objetivos de negócio, descrevendo os passos que precisam ser executados para
atingir esses objetivos através de um fluxograma.

A funcionalidade
---------------

1.  Na tela inicial da funcionalidade, as seguintes atividades estão
    disponibilizadas assim:

    -  Os fluxos podem ser buscados previamente cadastrados, ao clicar em “Filtros
        avançados” e preencher os dados;

    -  No botão “Editar” poderão existir várias versões do mesmo fluxo;

    !!! Abstract "NOTA"

        O versionamento tem por objetivo preservar o estado do fluxo de trabalho que
        está vinculado a algum serviço, evitando alterações em fluxo produtivo.  
        
     -  A opção “Exportar” permite a exportação do fluxo no formato JSON;

     -  Em “Excluir” é possível remover os fluxos.

    !!! Abstract "NOTA"

        A exclusão só será possível se não houver nenhum serviço vinculado ao fluxo
        a ser removido.  
        
3.  Ao clicar em “Editar” e selecionar qualquer versão do fluxo serão
    apresentadas as informações do fluxo em três abas: “Dados do fluxo”,
    “Diagrama” e “Documentação”. Cada qual tem a seguinte função:

    -   Na aba **Dados do fluxo**, serão expostos dados com as informações do fluxo,
        tais como: o nome, o processo a que está vinculado (O fluxo estará
        visível apenas para o processo a que está vinculado), versão, a
        descrição do fluxo e a opção para permitir a reabertura de um serviço
        independentemente das configurações de grupo.

    !!! tip "DICA"

        A opção de reabertura no fluxo pode ser útil em
        cenários em que existem muitos serviços onde a reabertura é permitida, sendo assim, ao marcar a opção "permitir reaberutra" não         é necessário utilizar a ação "reopen" na permissão do fluxo.

    -   A aba “Diagrama” representa uma ferramenta de design de fluxo. No lado esquerdo
        desta tela encontra-se a organização dos elementos que compõem a
        funcionalidade. Ao clicar em cada um destes elementos, estará
        acessível cada atividade realizada por este elementos, que são:

        -   **Eventos:** são os elementos de eventos que podem ser utilizados no
            desenho do fluxo:

            -   Evento Início

            -   Evento Intermediário de Envio de Link

            -   Evento Intermediário de Captura de Link

            -   Evento Intermediário de Temporizador

            -   Boundary - Evento Intermediário de Captura de Erro

            -   Evento Intermediário de Captura de Sinal

            -   Evento de Finalização com Erro

            -   Evento de Fim

        -   **Atividades**: são os elementos de atividades que podem ser utilizados
            no desenho do fluxo:

            -   Tarefa de Usuário

            -   Tarefa Script

            -   Envio de Mensagem – E-mail

            -   Business Rule Task

            -   Tarefa de Serviço – ESI

            -   Armazenamento de Dados

            -   Subprocesso

        -   **Extensões**: são as extensões que podem ser utilizadas no desenho do
            fluxo:

            -   Comunicação REST

            -   Notificação

            -   Atribuição de Variável

            -   Conversação Watson

        -   **Gateways**: são os elementos de gateway que podem ser utilizados no
            desenho do fluxo:

            -   Gateway Inclusivo

            -   Gateway Paralelo

            -   Gateway Exclusivo

            -   Gateway Complexo

            -   Gateway Baseado em Evento

        -   **Swimianes:** são os elementos de swimianes que podem ser utilizados no
            desenho do fluxo:

            -   Pool/Participante

            -   Lane

        -   **Artefato**: é o elemento de artefato que pode ser utilizado no
            desenho do fluxo:

            -   Anotação de Texto

    -   Nesta aba, também é permitido ao clicar no botão “Gerar Documentação” a
        exportação em PDF das informações geradas na aba “Documentação”. Além
        disso, ao clicar em “Gravar”, pode-se escolher a forma deste
        armazenamento (“Como nova versão” que significa versionar e gerar uma
        nova visão do fluxo ou “Na versão original” que significa salvar o fluxo
        na versão atual, a que está sendo editada).

    -   Na aba “Documentação” é gerada uma visão de todas as informações do fluxo
        (diagrama, descrição de elementos utilizados no diagrama).

!!! Abstract "NOTA"

    Vale lembrar que:

    - as normativas configuradas no fluxo terão prioridade em relação às
    marcações do template de solicitação de serviço, pois esta é um complemento do fluxo;

    - para usar o componente "Conversação Watson" a organização deve possuir a
    arquitetura IBM BlueMIX, possibilitando assim acesso à API Conversation do Watson;

    - para excluir um elemento que foi inserido no desenho do fluxo, clicar no
    mesmo e pressionar as teclas *Ctrl+Delete*.

Diagrama de um fluxo de trabalho
-------------------------------------

![Diagrama do Fluxo](images/flow-diagram.png)


-   1 – Representa o inicio do fluxo de trabalho;

-   2 – Representa uma tarefa do usuário a ser realizada no fluxo (que neste
    caso significa ‘receber a tarefa’);

-   3 – Representa a segunda tarefa do usuário a ser executada no fluxo (que
    neste caso significa ‘aprovação ou rejeição da tarefa’);

-   4 – Representa o “Gateway exclusivo” (que representa uma condição de fluxo
    exclusiva, em que um dos caminhos criados a partir do Gateway será seguido,
    de acordo com uma informação a ser testada. Este gateway pode ser
    representado visualmente como o losango vazio ou com um marcador de “x”) do
    fluxo;
	
-   5 – Representa o evento final do fluxo de trabalho (que neste caso significa
    a conclusão de execução da tarefa ou a rejeição da tarefa);	

-   6 – Representa a terceira tarefa do usuário a ser desempenhada no fluxo (que
    neste caso significa ‘executar a tarefa’, se a mesma tiver sido aprovada).
    
Uso
---

[Criar um fluxo de trabalho](/pt-br/citsmart-platform-8/workflow/use/create-flow.html)

[Modelagem de processo](/pt-br/citsmart-platform-8/workflow/use/modeling.html)


Configuração
----------

[Expressões](/pt-br/citsmart-platform-8/workflow/configuration/expressions.html)

[Construir expressões](/pt-br/citsmart-platform-8/workflow/configuration/expressions-creator.html)

!!! tip "About"

    <b>Product/Version:</b> CITSmart Platform | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>04/12/2019 - Anna Martins
