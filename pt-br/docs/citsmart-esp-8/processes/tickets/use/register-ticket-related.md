title: Cadastrar ticket relacionado
Description: Permite cadastrar um ticket com atividades relacionada ao ticket original.
#Cadastrar ticket relacionado
A funcionalidade permite cadastrar um ticket com atividades relacionada ao ticket original.

Antes de começar
----------------

É necessário o cadastro prévio do colaborador, contrato e unidade. Também é
preciso vincular o grupo ao contrato, a unidade ao contrato e o contrato ao
serviço.

Cadastrar o portfólio com os serviços e as atividades de requisição e incidente.
Definir o tempo de atendimento das atividades de requisição e incidente.

Vincular as atividades de requisição e incidente ao contrato do serviço.
Configurar o parâmetro 385 com o valor 'S'.

Procedimento
------------

1.  Acessar a funcionalidade Gerenciamento de Ticket navegando pelo menu
    principal Processos \> Gerência de Requisição e Incidente \> Ticket;

2.  Clicar sobre o ticket desejado e selecionar a alternativa "Criar Solicitação
    Relacionada" no menu opções;

3.  Preencher os campos necessários e clicar no botão "Gravar". O ticket relacionado será direcionado para o grupo executor definido
    no registro do vínculo da atividade, o mesmo será direcionado para o grupo
    executor definido no parâmetro 9;

4.  Lembre-se que o sistema enviará e-mails de notificação a respeito de
    criação, escalonamento, captura, encerramento e demais alterações dos
    tickets relacionados para o grupo executor do ticket principal.
    
5.  Para pesquisar os tickets relacionados, será necessário marcar o filtro "Exibir relacionadas" na área de pesquisa na tela principal     da funcionalidade.
    
!!! Abstract "ATENÇÃO"

    Os tickets relacionados por não possuírem fluxo próprio, são encerrados
    automaticamente juntamente com o fechamento do ticket de origem.
    
!!! Abstract "ATENÇÃO"

    Independentemente de o ticket pai ser reaberto ou permanecer encerrado,
    seus tickets relacionados não poderão ser reabertos, uma vez que não
    possuem fluxo próprio.

Relacionado
-----------

[Criar portfólio](/pt-br/citsmart-esp-8/processes/portfolio-and-catalog/use/create-the-portfolio.html)

[Cadastrar um colaborador](/pt-br/citsmart-esp-8/initial-settings/access-settings/user/register-employee.html)

[Cadastrar um contrato](/pt-br/citsmart-esp-8/additional-features/contract-management/use/register-contract.html)

[Cadastrar uma unidade](/pt-br/citsmart-esp-8/platform-administration/region-and-language/register-unit.html)

[Cadastrar um serviço](/pt-br/citsmart-esp-8/processes/portfolio-and-catalog/use/register-a-service.html)

[Configurar atributos de serviço](/pt-br/citsmart-esp-8/processes/portfolio-and-catalog/use/configure-services-attributes.html)

[Criar tempo de atendimento](/pt-br/citsmart-esp-8/processes/service-level/configuration/create-time-attendance.html)

[Configurar parametrização - sistema](/pt-br/citsmart-esp-8/platform-administration/parameters-list/configure-parametrization-system.html)

[Como relacionar unidade ao contrato](/pt-br/citsmart-esp-8/processes/tickets/configuration/relate-unit-to-contract.html)

[Como relacionar grupo ao contrato](/pt-br/citsmart-esp-8/processes/tickets/configuration/relate-group-to-contract.html)

<i class='fa fa-youtube-play  fa-2x' style='color:#97ce17;vertical-align: middle;'> </i> [Video Library](https://www.youtube.com/playlist?list=PLB5qK2uzf2ROn4Xs6UdH84Ujzta2iJ6Ei)'

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/17/2019 – Larissa Lourenço
