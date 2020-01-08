title: Criar pasta
Description: Disponibiliza ações diversas, tais como, incluir, alterar e excluir pastas que serão utilizadas para armazenamento e organização dos documentos registrados na base.

# Criar pasta

Pastas são locais utilizados na aplicação para armazenamento e organização de arquivos. As bases de conhecimentos do CITSmart são construídas utilizando-se estruturas de diretórios. Nos diretórios são aplicadas as permissões de leitura ou leitura e gravação, também devem ser definidas as ações possíveis no processo de gestão do conhecimento: revisar, aprovar, publicar e arquivar/desarquivar. Além disso, é possível realizar a pré-configuração das notificações que ocorrerão nas diversas ações do processo de gestão do conhecimento.

As permissões em pastas são aplicadas em duas perspectivas: perfil de acesso e grupo de usuários. Ao usar o permissionamento por perfil de acesso você poderá controlar os perfis que podem ler e escrever na pasta. Ao utilizar a abordagem por grupo, além do permissionamento padrão (ler e escrever), você poderá definir preferências de notificações para os diversos status dos conhecimentos.

## Antes de começar

- [X] Para ter acesso às pastas é necessário utilizar uma forma de permissionamento (perfil ou grupo), assim, antes de qualquer coisa você deve configurar os perfis de acesso ou criar os grupos.

- [X] Além disso, se você pretende criar preferências de notificações será necessário definir o ID de e-mail que será utilizado no envio das mensagens.

## Procedimento

1.  Acessar a funcionalidade através da navegação no menu Processos > Gerência de Conhecimento > Pasta;

2.  Clicar em "Novo";

3.  Preencher os campos disponibilizados;

    | Campo | Descrição | Exemplo |
    |-------|-----------|---------|
    | Nome | Informar o nome da pasta | Service Desk |
    | Pasta superior | Se você deseja criar uma pasta filha selecione uma pasta pai | Root Folder |
    | Notificar o autor... | Se o autor será notificado em todo o ciclo de vida do documento | Sim/Não |
    | Perfil de Acesso | Selecionar os perfis que terão acesso de leitura ou leitura e gravação na pasta | Administrador [Leitura/Gravação] |
    | Grupo | Selecionar os grupos que terão acesso de leitura ou leitura e gravação na pasta | Knowledge Managers |

4.  Clicar em "Gravar".

!!! info "IMPORTANTE"
    As configurações para uso de notificações só funcionarão quando você definir as partes interessas em um conhecimento. As configurações das pastas são apenas uma preparação (pre-configuração) para uso nas fases da gestão do conhecimento, ou seja, quando você começar a criar novos conhecimentos ou quando você realizar uma ação em um Conhecimento já existente é que, de fato, você poderá usar as preferências definidas nas pastas ou definir novas preferências. Estas prefências são definidas na aba "Partes interessadas" de cada conhecimento. Para mais informações acesse a documentação [Criar conhecimento][1].


## Relacionado

[Criar conhecimento][1]

[Cadastrar um grupo][2]

[Criar perfil de acesso][3]


<i class='fa fa-youtube-play  fa-2x' style='color:#97ce17;vertical-align: middle;'> </i> [Video Library](https://www.youtube.com/playlist?list=PLB5qK2uzf2RMbaWr-pRsc9bsaVnc_xTzd)

!!! tip "About"
    <b>Product/Verssion:</b> CITSmart | 8.05 &nbsp;&nbsp;
    <b>Updated:</b>12/23/2019 – Education Team

[1]:/pt-br/citsmart-platform-8/processes/knowledge/use/create-knowledge.html
[2]:/pt-br/citsmart-platform-8/initial-settings/access-settings/user/register-groups.html
[3]:/pt-br/citsmart-platform-8/initial-settings/access-settings/profile/create-profile-access.html