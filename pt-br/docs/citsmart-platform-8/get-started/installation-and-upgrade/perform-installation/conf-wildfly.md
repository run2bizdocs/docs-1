Title: Configurando o Wildfly

# Configurando o Wildfly

Entre no jboss-cli e execute os comandos abaixo:

``` shell
/subsystem=logging/root-logger=ROOT:write-attribute(name=level,value=INFO)

/subsystem=logging/console-handler=CONSOLE:write-attribute(name=level,value=INFO)

/subsystem=undertow/server=default-server/http-listener=default:write-attribute(name=max-post-size,value="5000485760")

/subsystem=undertow/server=default-server/http-listener=default:write-attribute(name=max-parameters,value="3000")

/subsystem=undertow/server=default-server/http-listener=default:write-attribute(name=max-header-size,value="65535")

/subsystem=undertow/server=default-server/https-listener=https:write-attribute(name=max-post-size,value="5000485760")

/subsystem=undertow/server=default-server/https-listener=https:write-attribute(name=max-header-size,value="65535")

/subsystem=undertow/server=default-server/https-listener=https:write-attribute(name=max-parameters,value="3000")

/subsystem=undertow/configuration=filter/rewrite=citsmart:add(target="/citsmart")

/subsystem=undertow/server=default-server/host=default-host/filter-ref=citsmart:add(predicate="regex('\^/?\$') and equals(/citsmart)")

/subsystem=undertow/server=default-server/host=default-host/setting=access-log:add

/subsystem=undertow/server=default-server/host=default-host/setting=access-log:write-attribute(name=pattern, value="%h %l %u [%t] \"%r\" %s %b \"%{i,Referer}\" \"%{i,User-Agent}\"")

/subsystem=messaging-activemq/server=default/jms-queue=filaDocumentoQueue:add(entries=["queue/filaDocumento","java:jboss/exported/jms/queue/filaDocumento"])

/subsystem=messaging-activemq/server=default/jms-topic=filaDocumentoTopic:add(entries=["topic/filaDocumento","java:jboss/exported/jms/topic/filaDocumento"])

/subsystem=messaging-activemq/server=default/jms-queue=neuroInputQueue:add(entries=["queue/neuroInputQueue","java:jboss/exported/jms/queue/queue/neuroInputQueue"])

/subsystem=messaging-activemq/server=default/jms-queue=neuroOutputQueue:add(entries=["queue/neuroOutputQueue","java:jboss/exported/jms/queue/queue/neuroOutputQueue"])

/subsystem=deployment-scanner/scanner=default:write-attribute(name=deployment-timeout,value=6000000)
```

## Próximo passo

[Configurações extras do CITSmart][1]

[1]:/pt-br/citsmart-platform-8/get-started/installation-and-upgrade/perform-installation/conf-extras.html
