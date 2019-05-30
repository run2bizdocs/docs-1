title:  Auditoria do sistema
Description: Permite gerenciar os eventuais riscos ao sistema
# Auditoria do sistema

Esta funcionalidade permite gerenciar os eventuais riscos ao sistema, ao auditar todas as execuções efetivadas no sistema em forma de logs.
Foram feitas algumas mudanças na auditoria (itsm-audit-0.4.0), mudanças essas apenas a nível de configuração

Antes de começar 
-----------------

**Versão inferior à 0.4.0**

É necesseário a instalação prévia dos seguintes produtos:

-   ACTIVEMQ com a versão 5.15.8 ou superior;

-   Mongodb.

**Versões iguais ou superiores à 0.4.0**

- Não é preciso ter um ActiveMQ externo ativo;

- Não é preciso ter um serviço executando o .jar da auditoria;

- Audit agora é um .war e é executado dentro do Wildfly junto ao ITSM na
pasta "\deployments"

- Adicionar as seguintes linhas ao standalone do wildfly no subsystem do activeqm:

<jms-queue name="ITSM.READ_DATA_AUDIT" entries="queue/ITSM.READ_DATA_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_DATA_AUDIT"/>
<jms-queue name="ITSM.READ_LICENSE_AUDIT" entries="queue/ITSM.READ_LICENSE_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_LICENSE_AUDIT"/>
<jms-queue name="ITSM.READ_ACCESS_AUDIT" entries="queue/ITSM.READ_ACCESS_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_ACCESS_AUDIT"/>
<jms-queue name="ITSM.READ_BACKUP_AUDIT" entries="queue/ITSM.READ_BACKUP_AUDIT java:jboss/exported/jms/queue/queue/ITSM.READ_BACKUP_AUDIT"/>

- Adicionar as seguintes linhas ao standalone do wildfly no system-properties (igual é utilizado no CITSmart EVM e CITSmart Inventory):

<property name="mongodb.host" value="localhost"/>
<property name="mongodb.port" value="27017"/>
<property name="mongodb.user" value="mongodb"/>
<property name="mongodb.password" value="mongodb"/>
<property name="mongodb.dabase.audit" value="itsm-audit"/>   

!!! note "NOTA"

    Configurar a conexão com do banco mongo com host, port, user, pass e database (Provavelmente já existente, EVM e Inventory utilizam     essas configurações).

- O parâmetro 424 deve ficar em branco;

- O parâmetro 425 deve ficar dessa forma (http://localhost:8080/itsm-audit);

!!! Abstract "ATENÇÃO"

    A porta 8080 deve ser alterada ser alterada se o CITSmart estiver sendo executado em porta diferente.  
    
- Adicionar o .war em anexo na pasta deployments (Ou via Console do Wildfly) e realizar start do Wildfly junto com o CITSmart.
   
Procedimento
------------

***Processo para configurar a Auditoria:***

*Configuração para gerar o backup das auditorias*.

Primeiramente, é imprescindível configurar os parâmetros específicos da
funcionalidade.

1.  Acessar a funcionalidade através da navegação no menu principal
    Parametrização \> Parametrização de Auditoria;

2.  Informar no campo “Diretório” a pasta onde será mantido todos *logs* de
    auditoria realizados;

3.  No campo “Frequência em dias” é possível ajustar uma rotina de backup dos
    logs de auditoria, ao escolher a periodicidade do backup em dias.

    !!! Abstract "NOTA"

        A escolha da frequência deve ser a partir de 1 (um) dia para a execução do backup.  

4.  É disponibilizado a possibilidade de determinar um período específico (data
    de início e fim) para a geração dos logs de auditoria do sistema.

    !!! note "IMPORTANTE"

        São oferecidos três tipos de auditoria de sistema: auditoria dos dados do sistema, do acesso ao sistema e as licenças do mesmo.

***Auditoria de dados do sistema***

*Apresenta o histórico de todos dados de alteração, inclusão e exclusão
realizadas no sistema.*

1.  Acessar a funcionalidade através da navegação no menu principal Sistema \>
    Trilha de auditoria \> Auditoria de dados;

2.  Será exibido os logs de auditoria de toda movimentação realizada no
    programa, mostrando a data e hora das atualizações, o endereço de IP, o nome
    do executor da atualização, o nome da tabela, o tipo de operação efetivada
    no sistema. Ao clicar no botão dados será apresentado o que de fato foi
    atualizado no programa.

    !!! Abstract "ATENÇÃO"

        O campo “Operações” apresenta o tipo de ação realizada na atualização do
        sistema em tese. É definida por símbolos, e seus significados são:

        -   A letra “A” significa “Alteração” nos dados do sistema;

        -   A letra “I” simboliza a “Inserção” de novos dados ao sistema;

        -   A letra “E” significa a “Exclusão” de dados do sistema.  

3.  É liberado também a busca de determinado *log* através dos filtros dispostos
    na tela.

***Auditoria de acessos ao sistema***

*Apresenta o histórico dos acessos ao sistema (entradas e saídas).*

1.  Acessar a funcionalidade através da navegação no menu principal Sistema \>
    Trilha de auditoria \> Auditoria de acesso;

2.  Será exposto os usuários que efetuaram o login e logout no sistema,
    registrando também a data e a hora de cada uma destas atividades;

    !!! Abstract "NOTA" 
    
        Se porventura o sistema expirar, não será possível captar o logout do
        sistema, ficando registrado, portanto, só as informações de entrada da
        sessão de acesso.  

3.  Existem filtros para auxiliar a busca de determinado acesso.

***Auditoria de licenças do sistema***

*Informa as licenças utilizadas para a validação do sistema.*

1.  Acessar a funcionalidade através da navegação no menu principal Sistema \>
    Trilha de auditoria \> Auditoria de licença;

2.  Apresenta os dados das licenças adquiridas e usadas para a execução do
    sistema;

3.  É possível pesquisar uma determinada licença e seu prazo de validade pelos
    filtros liberados na tela principal.
    
!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>02/15/2019 – Larissa Lourenço
