Title: Relacionar IC a um serviço

# Relacionar IC a um serviço

O cadastro de relacionamento entre Itens de Configuração e Serviços tem por objetivo evidenciar no CMDB as dependências existentes entres cada um desses elementos. O registro é feito para auxiliar os operadores dos IC’s a identificarem serviços ou itens que sofrerão impacto durante o tratamento de uma mudança, seja ela no parque de IC’s, no tratamento de um incidente, no tratamento de uma mudança ou no tratamento de um portfólio de serviço.
O relacionamento existe da seguinte forma:

- Itens de Configuração com outros Itens de Configuração;
- Itens de Configuração com Serviços de Negócio/Apoio;

## O que fazer antes

O cadastro de relacionamento requer Itens de configuração e Serviços ativos. O usuário deverá possuir acesso à tela de Cadastro de Tipo de Relacionamento (ver [Criar Perfil de Acesso][1])

## Procedimento

1. Acessar a funcionalidade pelo menu Processos > Gerência de Configuração > CMDB;

2. Preencher os campos disponibilizados;

    | Campo | Descrição |
    |-------|-----------|
    |Nome | Descrição do tipo de relacionamento|
    |Status | Selecione: Ativo (situação indicativa de que o tipo de relacionamento está disponível para uso) ou Inativo (situação indicativa de que o tipo de relacionamento está indisponível para uso)
    |Posição | Define no desenho de mapa em qual posição ficará a cardinalidade do item de configuração: "Mesmo nível" - do ponto selecionado para o desenho do mapa de IC, significa que o IC ficará no mesmo nível; "Nível Superior" – Descrição do ponto selecionado para o desenho do mapa de IC, que ficará acima; "Nível Inferior" - Descrição do ponto selecionado para o desenho do mapa de IC, que ficará abaixo;
    |Ações| "Gravar" – Insere o tipo de relacionamento; "Limpar" – Retorna os campos de cadastro ao seu estado default; "Pesquisa" – Retorna à pesquisa de Tipo de relacionamento;

3. Ao acionar a ação de “Gravar” O sistema grava na tabela tipo de relacionamento a descrição, o usuário que realizou a gravação, a data e a hora da criação e a situação do tipo de relacionamento, o sistema deverá exibir a seguinte mensagem “Tipo de relacionamento gravado com sucesso!”

## Relacionado

[Criar Item de Configuração][1]

[1]:/pt-br/citsmart-platform-8/processes/configuration/use/register-CI.html