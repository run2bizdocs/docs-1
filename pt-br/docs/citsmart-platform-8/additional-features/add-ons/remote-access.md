Title: Implementar o Acesso Remoto

# Implementar o Acesso Remoto

A funcionalidade de acesso remoto permite que computadores sejam acessados remotamente a partir de sua instância CITSmart. Neste sentido, utilizamos os recursos do protocolo VNC (Virtual Network Computing) por intermédio do Apache Guacamole - Gateway de acesso remoto baseado na web - para tornar esta operação viável. Além de poder acessar remotamente um item de configuração, todas as sessões são gravadas e disponibilizadas junto às informações do IC. Isto garante um melhor controle sobre as ações realizadas proporcionando um ambiente confiável e auditável.

Esta funcionalide é um complemento (add-on) à Gerência de Configuração e depende do processo de invetário para tonar o acesso remoto viável à um IC.


## O que fazer antes

Os seguintes quesitos antecedem o uso efetivo desta funcionalidade:

* [x] Ter a Gerência de Configuração implementada
* [x] Ter um processo de inventário definido e funcional
* [x] Ter os dados 

## Procedimento

1. Baixar o container do GUACD;
2. Configurar as propriedades do GUACD no servidor de aplicação;

    ```java
    CITSMART_PROTOCOL=http
    CITSMART_URL=your-instance.citsmartcloud.com
    CITSMARTGUACD_ID=guacd_id
    CITSMART_LOGIN=admin
    CITSMART_PASSWORD=********
    ```
	
3. Definir o diretorio para gravação dos vídeos (ex. /mp4);
    
!!! success "Gravação de video"
        
    Após o encerramento da sessão de acesso remoto, o vídeo gerado 
    entra em uma fila de copilação para então ser disponilizado na 
    plataforma. O tempo de compilação dempenderá do tempo da sessão, 
    além disso, o início da compilão está atrelado à rotina cron 
    definida na conexão de acesso remoto.
    
## O que fazer a seguir

Com o serviço do GuaCD ativo e comunicável, o próximo passao e criar uma conexão de acesso remoto em sua instância e testar o recurso.

## Relacionado

[Criar conexão com o servidor de acesso remoto][1]

[1]:/pt-br/citsmart-platform-8/processes/configuration/configuration/configure-remote-access.html
