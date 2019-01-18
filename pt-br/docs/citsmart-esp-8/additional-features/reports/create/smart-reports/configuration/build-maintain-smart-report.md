title: Construir e manter relatórios Smart - V. 8.0
Description: Tem o objetivo de prover a facilidade de elaboração de relatórios personalizados com os dados das funcionalidades requeridas, sem necessidade de novas atualizações ou softwares adicionais.
#Construir e manter relatórios Smart - V. 8.0

Esta funcionalidade tem o objetivo de prover a facilidade de elaboração de
relatórios personalizados com os dados das funcionalidades requeridas, sem
necessidade de novas atualizações ou softwares adicionais.

**Antes de começar**
--------------------

É necessário o cadastro prévio de sub relatórios.

**Procedimento**
----------------

1.  Acessar a funcionalidade através da navegação no menu principal Relatórios
    \> Relatórios Smart \> Gerador de Relatórios Smart;

2.  Clicar no botão "Novo";

3.  Preencher os campos necessários. Definir o tipo:

    1.  SQL: cria um Sub Relatório "SQL" (esse tipo permite criar relatórios que
        retornam as informações do Banco de dados através de uma Query). Ao
        selecionar esta opção, será necessário informar também o tipo de
        relatório a ser criado, a regra de negócio concernente ao mesmo, o
        designer do relatório, o parâmetro e o script;

    2.  RhinoScript: para criar um relatório que retorna as informações do Banco
        de dados através de um "Script" é necessário selecionar o tipo
        "RhinoScript". Será preciso eleger o tipo de relatório, definir os
        parâmetros e descrever o script;

    3.  JSP: cria um relatório com conteúdo dinâmico. Ao optar por este tipo,
        deverá informar os parâmetros e o script "JSP";

    4.  Neuro: cria um relatório do tipo "Neuro", basta vincular um formulário
        "Neuro" previamente cadastrado.

!!! Abstract "NOTA"

    Para se criar um Sub Relatório (Drill) o " Tipo de relatório" deverá ser
    "Gráfico de pizza" ou " Gráfico de Barra".**


1.  Definir o módulo (funcionalidade) onde será exibido o relatório que está
    sendo criado:

-   **N/A**: selecionar essa opção, caso queira que o relatório não seja exibido
    em nenhum módulo;

-   **Geral**: selecionar essa opção para exibição do relatório em um ou mais
    módulos, onde deseja que o relatório seja exibido ( Configuração,
    Incidentes/Requisições, Incidentes/Requisições (Gráfico), Liberação,
    Mudanças, Problemas);

-   **Específico**: selecione um único módulo onde deseja que o relatório seja
    exibido (Configuração, Incidentes/Requisições, Incidentes/Requisições
    (Gráfico), Liberação, Mudanças, Problemas).

1.  Clicar no botão "Gravar";

2.  Existe a possibilidade também de importar um "Relatório". Para tanto, clicar
    no botão "Importar" e vincular o arquivo contendo as informações desejadas;


!!! Abstract "ATENÇÃO"

    Os relatórios aqui criados serão exibidos na tela de "Relatórios Smart",
    onde será possível visualizar os dados pertinentes de cada relatório.


Relacionado
-------

Gerar relatórios Smart


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/18/2019 – Anna Martins
