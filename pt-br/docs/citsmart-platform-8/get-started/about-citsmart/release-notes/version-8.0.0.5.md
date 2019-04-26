Description: Release Notes CITSmart Versão 8.0.0.5 de 25/04/2019

# Versão 8.0.0.5
_22/04/2019_


## Problemas Resolvidos

| Problema | Descrição                                                                                                                                              |
|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| 3360     | Ger. de Problema - Erro ao recuperar Solução definitiva                                                                                                |
| 3361     | Ger. de Problema - Erro ao recuperar o campo de fechamento                                                                                             |
| 3362     | Ger. de Problema - Erro ao recuperar erro conhecido                                                                                                    |
| 3363     | Ger de Configuração – Erro ao recuperar Mudanças Concluídas relacionadas à Item de Configuração                                                        |
| 3364     | Ger. Liberação – Erro ao vincular Mudança encerrada em Liberação                                                                                       |
| 3365     | Ger. Problema – Adequação de interface para apresentar os campos “Mensagem de erro associada” e “Diagnóstico”                                          |
| 3366     | Ger. Mudança – Erro ao retornar Risco Simplificado                                                                                                     |
| 3393     | Ger. Liberação – Retorno da Regra de Negócio ao vincular uma mudança que tenha IC vinculado a uma Liberação, vincular automaticamente o IC à Liberação |
| 3282     | Ger. Eventos – Falha ao Editar um Ger. Genérico Zabbix                                                                                                 |
| 3115     | Ger. Eventos – Renderização maior da tela de Ger de Ticket                                                                                             |
| 3394     | Ger. Liberação – Sistema duplica anexos ao avançar fluxo                                                                                               |
| 3388     | Ger. Problema – Gravação de erro conhecido não seta campo de arquivamento e sistema não consegue recuperar o conhecimento                              |
| 3419     | Ger. Mudança – Sistema não recupera anexo colocado no campo de Revisão e fechamento                                                                    |

*Erro conhecido e solução*

Se atentem para o cenário descrito:

-   Pré Condições:

    1.  O cliente estará atualizando a versão 7 para a versão 8.0.0.5;

    2.  O consultor não parametrizou em Portfólio de Problema a pasta para
        gravar a base de conhecimento de Erro Conhecido;

-   O que ocorre:

    1.  O usuário acessa a tela de Gerenciamento de Problema;

    2.  O usuário informa o campo Causa Raiz e tenta acionar a gravação da base
        de conhecimento;

    3.  Ao abrir a tela de Base de Conhecimento para gravação o sistema exibe a
        mensagem de que o usuário não possui permissão;

-   Por que ocorre?

    1.  A mensagem ocorre porque o consultor não informou qual deveria ser a
        pasta de gravação do erro conhecido em Portfólio de Problema;

    2.  Uma vez tentado gravar o erro conhecido, o sistema não identifica a
        pasta e emite a mensagem;

    3.  Nesses casos, procure o Suporte Citsmart para realizar a adequação desse
        cadastro;

    4.  Faça a configuração da pasta para gravação de erro conhecido na tela de
        Portfólio de Problema;

    5.  No próximo cadastro a mensagem não se repetirá.
    
    
    
**Caminho dos pacotes:**  
**SM:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Enterprise/8.0.0.5/CitsmartITSM-Enterprise-8.0.0.5.war.zip**  
  
**Inventory:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-Inventory/citsmartinventory-2.0.0.3.war.zip**  
  
**EVM:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-EVM/citsmartevm-2.0.0.3.war.zip**  
  
**Neuro:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Citsmart-Neuro/citsmart-neuro-web-1.2.4.8.war.zip**  
  
**Audit:
ftp://ftpgo.centralit.com.br/10104_DIRETORIA_DE_SOLUCOES/PUBLICO/Citsmart-ITSM/Audit/itsm-audit-0.2.0.zip**
