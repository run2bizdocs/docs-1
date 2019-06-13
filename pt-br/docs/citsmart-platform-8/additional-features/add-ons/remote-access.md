Title: Implementar o Acesso Remoto

# Implementar o Acesso Remoto

A funcionalidade de acesso remoto permite que computadores sejam acessados remotamente a partir de sua instância CITSmart. Neste sentido, são utilizados os recursos do protocolo VNC (Virtual Network Computing) por intermédio do Apache Guacamole - Gateway de acesso remoto baseado na web - para tornar esta operação viável. Além de poder acessar remotamente um item de configuração, todas as sessões são gravadas e disponibilizadas junto às informações do IC. Isto garante um melhor controle sobre as ações realizadas, proporcionando um ambiente confiável e auditável.

Esta funcionalide é um complemento (add-on) à Gerência de Configuração e depende do processo de inventário para tonar o acesso remoto viável a um IC.


## O que fazer antes

Os seguintes quesitos antecedem o uso efetivo desta funcionalidade:

* [x] Ter um processo de inventário definido e funcional utilizando o CITSmart Inventory;
* [x] Ter itens de configuração inventariádos;

## Procedimento

1. Instalar o GuaCD utilizando a [documentção oficial][1] ou baixar o container disponibilizado pela CITSmart;

2. Após a instalação, configurar o apontamento de logs;
    
    ```sh
    /usr/local/sbin/guacd -b 0.0.0.0 > /var/log/guacd.log 2>&1
    ```

3. Baixar o binário do [encoder (.jar)][2];

4. Copiar o enconder de vídeo para o servidor;

5. Realizar a configuração substituindo as variáveis pelas inforamações de seu servidor;
    
    ```java
    java -Durl=${CITSMART_PROTOCOL}://${CITSMART_URL}/citsmart -DcontainerIdentifier=${CITSMARTGUACD_ID} -DuserName=citsmart.local\\${CITSMART_LOGIN} -Dpassword=${CITSMART_PASSWORD} -jar /citsmart-guacd-encoder.jar &
    ```
    
6. Definir o diretório para gravação dos vídeos (ex. /mp4);
    
    !!! success "Gravação de video"
        Após o encerramento da sessão de acesso remoto, o vídeo gerado 
        entra em uma fila de compilação para então, ser disponilizado na 
        plataforma. O tempo de compilação dependerá do tempo da sessão, 
        além disso, o início da compilação está atrelado à rotina cron 
        definida na conexão de acesso remoto.
        
7. No item de configuração que será acessado remotamenete (ex. Computador Windows), instalar um cliente de acesso remoto com suporte ao protocolo VNC (Exemplo: [TightVNC][3]) e definir uma senha de acesso. Guarde esta senha pois ela será utilizada no próximo passo.
    
8. Realizar o cadastro de conexões de Acesso Remoto em sua instância [conforme o documento][4].


## O que fazer a seguir

Com o serviço do GuaCD ativo e comunicável, o próximo passo é acessar remotamente o IC configurado.

## Relacionado

[Gerenciamento de Configuração][5]

[Implementar o CITSmart Inventory][6]

[1]:https://guacamole.apache.org/doc/gug/installing-guacamole.html
[2]:images/citsmart-guacd-encoder.jar.zip
[3]:https://www.tightvnc.com/
[4]:/pt-br/citsmart-platform-8/processes/configuration/configuration/configure-remote-access.html
[5]:/pt-br/citsmart-platform-8/processes/configuration/overview.html
[6]:https://docs.citsmart.com/pt-br/citsmart-platform-8/additional-features/add-ons/inventory.html

