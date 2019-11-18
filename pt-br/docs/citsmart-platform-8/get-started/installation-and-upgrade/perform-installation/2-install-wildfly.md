Download e Instalação do JDK

O download do Java SE Development Kit deve ser realizado diretamente do site da Oracle. No momento da criação deste documento o caminho pode ser acessado por esse endereço:

https://www.oracle.com/technetwork/pt/java/javase/downloads/jdk8-downloads-2133151.html

Caso o endereço não esteja funcionando, procure pelo JDK na área de download do site da Oracle. Baixe a versão de acordo com a arquitetura de seu sistema operacional. No exemplo estamos utilizando um `Linux CentOS 7.x 64bits`. Todos os pacotes serão baixados no `/tmp`.

Faça o download do jdk para máquina local e envie para o servidor via scp. Para isso, é obrigatório ter um usuário e senha no site da Oracle (o cadastro é gratuito). Isso se deve ao fato do site da Oracle exigir o aceite dos termos de serviço antes de realizar o download. A última versão do JDK disponível no momento da criação da documentação era a `jdk-8u231`. Utilize sempre a último patch da versão recomendada.

## Instalando e configurando o JDK

Supondo que o arquivo esteja no `/tmp` execute os comandos abaixo para descompactação:

``` bash
[root@server /tmp]# tar -xvzf jdk-8u231-linux-x64.tar.gz -C /opt/
```
Crie um link simbólico para pasta do jdk na respectiva versão que foi feito o download. Isso facilita futuras atualizações e testes com outras versões.

``` bash
[root@server /tmp]# ln -s /opt/jdk1.8.0_231 /opt/jdk
```

Crie o arquivo de configuração do java em /etc/profile.d/ chamado java.sh. Embora o servidor web tenha suas próprias configurações de java, esta etapa previne que outras aplicações que funcionem com java dê algum tipo de problema.

``` bash
[root@server /tmp]# vi /etc/profile.d/java.sh
```

e adicione o seguinte conteúdo (o Wildfly será instalado mais adiante):

``` shell
export JAVA_HOME="/opt/jdk"
export JBOSS_HOME="/opt/wildfly"
export PATH="$JAVA_HOME/bin:$JBOSS_HOME/bin:$PATH"
```
Carregue as configurações com comando abaixo e teste:

``` shell
[root@server /tmp]# source /etc/profile.d/java.sh
[root@ip-172-16-12-182 opt]# java -version
java version "1.8.0_231"
Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)
[root@ip-172-16-12-182 opt]#
```
