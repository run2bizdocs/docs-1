Title: Relacionar IC a um serviço

# Relacionar Item de Configuração a um serviço

O cadastro de relacionamento entre Itens de Configuração e Serviços tem por objetivo evidenciar no CMDB as dependências existentes entres cada um desses elementos. O registro é feito para auxiliar os operadores dos IC’s a identificarem serviços ou itens que sofrerão impacto durante o tratamento de uma mudança, seja ela no parque de IC’s, no tratamento de um incidente, no tratamento de uma mudança ou no tratamento de um portfólio de serviço.
O relacionamento existe da seguinte forma:

- Itens de Configuração com outros Itens de Configuração;
- Itens de Configuração com Serviços de Negócio/Apoio;

## O que fazer antes

O cadastro de relacionamento requer:

- [X] Ter acesso à interface de gestão de CMDB (ver [Criar Perfil de  Acesso][1]);

- [X] Cadastrar tipo de relacionamento de IC (ver [Cadastrar tipo de relacionamento de IC][2]);

- [X] Ter Itens de configuração inventariados;

- [X] Ter serviços configurados no portfólio (negócio/apoio);

## Procedimento

1. Acessar a funcionalidade pelo menu Processos > Gerência de Configuração > CMDB;

2. Pesquisar e selecionar um Item de Configuruação;

3. Clicar na opção à esquerda "Relacionamento", logo após em "Editar";

4. Preencher os campos disponibilizados;

    | Campo | Descrição |
    |-------|-----------|
    |Item (não editável) | Informa o Item de Configuração selecionado para o desenho dos relacionamentos|
    |Ícone | Permite selecionar um desenho que represente esse item de configuração |
    |Tipo de Relacionamento| Identifica o tipo de relacionamento (cadastrar tipo de relacionamento de IC) |
    |Nome|Auto complete que retorna as descrições do Tipo de Relacionamento cadastrado na tela Tipo de Relacionamento|
    |Nível|Retorna os níveis inferior e superior cadastrados na tela Tipo de Relacionamento|
    |Para|Identifica o outro ponto da ligação do relacionamento;|
    |Tipo| Opões para selecionar: "Item de Configuração", "Serviço de Negócio" ou "Serviço de Apoio"|
    |Item|Auto complete que permite a busca do tipo selecionado|
    |Ícone|Permite selecionar um desenho que represente esse tipo selecionado|

5. Clicar em "Gravar" para salvar as alterações.

## Relacionado

[Ver mapa de relacionamento de um IC][4]

[Criar Item de Configuração][3]

[1]:/pt-br/citsmart-platform-9/initial-settings/access-settings/profile/create-profile-access.html
[2]:/pt-br/citsmart-platform-9/processes/configuration/configuration/create-type-relationship-ci.html
[3]:/pt-br/citsmart-platform-9/processes/configuration/use/register-CI.html
[4]:/pt-br/citsmart-platform-9/processes/configuration/use/view-ci-relationship-map.html