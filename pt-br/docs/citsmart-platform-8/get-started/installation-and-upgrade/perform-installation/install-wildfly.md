# Instalação do Wildfly

O download do wildfly pode ser realizado diretamente do site da comunidade em sua área de downloads em https://wildfly.org/downloads/. A versão deverá ser a mesma sugerida pela documentação em [Requisitos do sistema][1]. Neste caso, deverá ser feito o download do pacote tgz `Java EE Full & Web Distribution`.

```sh
cd /tmp
```
```sh
wget https://download.jboss.org/wildfly/12.0.0.Final/wildfly-12.0.0.Final.tar.gz
```
Descomprima o pacote para o `/opt`:

```sh
tar -xvzf wildfly-12.0.0.Final.tar.gz -C /opt/
```
Crie um link simbólico para o wildfly versão 12. Isso visa facilitar administrações futuras:

```sh
ln -s /opt/wildfly-12.0.0.Final /opt/wildfly
```

Envie via scp e descomprima o arquivo assets disponibilizada pela CITSmart dentro do diretório do wildfly. Essa pasta é necessária para funcionamento da solução, e é disponibilizada para parceiros através de nosso portal de parceria juntamente com os pacotes de instalação:

```sh
tar -xzvf assets.tar.gz -C /opt/wildfly/
```

Crie um usuário e grupo para o wildfly:

```sh
groupadd -r wildfly
```
```sh
useradd -r -g wildfly -d /opt/wildfly -s /sbin/nologin wildfly
```

Crie a pasta dos relatórios:

```sh
mkdir /opt/wildfly/reports
```

Altere as permissões da pasta do wildfly para o usuário criado acima:

```sh
chown -R wildfly.wildfly /opt/wildfly-12.0.0.Final/
```
## Testando o Wildfly

A partir desta etapa, podemos realizar um teste para identificar se o Wildfly está funcionando corretamente. Faça um login com usuário do wildfly com comando abaixo:

```sh
su - wildfly -s /bin/bash
```

E verifique se o PATH do java está funcionando corretamente:

```sh
java -version
```
A saída deverá ser semelhante a esta:
```sh
java version "1.8.0_231"
Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)
-bash-4.2$
```

Suba o serviço com comando abaixo:

```sh
~/bin/standalone.sh
```

Acompanhe as mensagens de inicialização. Caso o servidor tenha iniciado corretamente, será exibida uma mensagem semelhante a essa abaixo:

```sh
INFO  [org.jboss.as] (Controller Boot Thread) WFLYSRV0025: WildFly Full 12.0.0.Final (WildFly Core 4.0.0.Final) started in 3762ms - Started 292 of 513 services (308 services are lazy, passive or on-demand)
```

Se a mensagem acima indica que o serviço está funcionando corretamente. Pressione `[CTRL+C]` para interromper o serviço. Em seguinda digite `exit` para sair do usuário CITSmart.

## Próximo passo

[Configurando o Java para o WildFly][2]

[1]:/pt-br/citsmart-platform-8/get-started/installation-and-upgrade/system-requirements.html
[2]:/pt-br/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/conf-java-for-wildfly.html
