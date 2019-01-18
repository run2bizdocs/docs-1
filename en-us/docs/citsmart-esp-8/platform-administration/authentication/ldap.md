Title: LDAP

# LDAP

O LDAP (Lightweight Directory Access Protocol - Protocolo de acesso aos diretórios leves) é um protocolo padrão que permite gerenciar diretórios, ou seja, acessar bancos de informações sobre os usuários de uma rede por meio de protocolos TCP/IP.

Essa funcionalidade permite cadastrar múltiplas conexões LDAP e definir as configurações para cada uma delas.

## Antes de começar

É preciso ter cadastrado o horário para agendamento da sincronização automática.

## Procedimento

1. Acessar o menu principal Parametrization > DAP Configuration;
2. Clicar no botão "New";

    REGRA: todos os campos são igualmente relevantes para viabilizar a conexão com o LDAP, enquanto o teste não for bem-sucedido o procedimento de configuração não pode ser considerado completado.

3. Preencher os campos disponibilizados;
    
	REGRA: caso não exista grupos LDAP, preencher o campo “DN Grupo” apenas com um asterisco. Isto fará com que o sistema verifique todo o domínio.

4. É possível vincular novos grupos, para isso clicar no botão "Adicionar" na área Grupos LDAP;

    REGRA: antes de pedir para testar DEVE ser clicado o botão "Gravar" para salvar a configuração, caso contrário o teste usará os dados anteriores às alterações feitas na tela.
    
    REGRA: quando há um pedido de autenticação na tela de identificação do sistema (login e senha) é executado um ciclo de busca da conexão correta com base nesta configuração, ou seja, há uma tentativa de autenticação para cada domínio aqui cadastrado (isso se houver mais de um).
    
5. É possível vincular mapas de campos, para isso clicar no botão "Adicionar" na área Mapeamento de campos;
6. Clicar no botão "Gravar".

    REGRA: o sistema não permite excluir um usuário que tem origem no LDAP.