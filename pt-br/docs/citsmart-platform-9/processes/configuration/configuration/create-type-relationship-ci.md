Title: Cadastrar tipo de relacionamento de IC

# Cadastrar tipo de relacionamento de IC

O cadastro de tipo relacionamento de IC é necessário para a gestão de Itens de Configuração (ativos e serviços) no CMDB. Com este cadastro será possível, a partir de um IC, definir níveis de relacionamento entre ICs.

## O que fazer antes
O usuário deverá possuir acesso à tela de Cadastro de Tipo de Relacionamento.

## Procedimento

1. Acessar a funcionalidade pelo menu Processos > Gerência de Configuração > Item de configuração;

2. Preencher os campos disponibilizados;

    | Campo | Descrição |
    |-------|-----------|
    | Nome | Descrição do tipo de relacionamento|
    | Status | Selecione: Ativo (situação indicativa de que o tipo de relacionamento está disponível para uso) ou Inativo (situação indicativa de que o tipo de relacionamento está indisponível para uso)
    | Posição | Define no desenho de mapa em qual posição ficará a cardinalidade do item de configuração: "Mesmo nível" - do ponto selecionado para o desenho do mapa de IC, significa que o IC ficará no mesmo nível; "Nível Superior" – Descrição do ponto selecionado para o desenho do mapa de IC, que ficará acima; "Nível Inferior" - Descrição do ponto selecionado para o desenho do mapa de IC, que ficará abaixo;
    | Ações | "Gravar" – Insere o tipo de relacionamento; "Limpar" – Retorna os campos de cadastro ao seu estado default; "Pesquisa" – Retorna à pesquisa de Tipo de relacionamento;

3. Clicar em "Gravar" para salvar as informações.

!!! warning "ATENÇÃO"
    Caso um Tipo de relacionamento esteja sendo utilizado em um desenho de Mapa, então, o sistema não permitirá a edição da posição Mesmo Nível.

## Relacionado

[Relacionar Item de Configuração a um serviço][1]

[1]:/pt-br/citsmart-platform-9/processes/configuration/use/create-ic-relationship.html