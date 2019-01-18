Title: Configure email account

# Configure email account

Este documento visa apresentar o passo à passo da configuração de e-mail no CITSmart ESP para leitura (IMAP) e envio (SMTP) de mensagens.

## O que fazer antes

Obter as informações da conta de e-mail e configurar permissões de acesso ao servidor de e-mail.

## Procedimento

1. Acessar o menu principal Parametrization > Email

* Configurar o SMTP

|ID |Descrição | Exemplo |
|---|----------|---------|
|10 | Endereço de e-mail da Organização	| company@exemple.com |
|11 | Exige autenticação | Sim |
|12 | Endereço de e-mail | your.email@gmail.com |
|13 | Senha | Sua senha do Gmail |
|14 | Servidor de envio de e-mails (SMTP) | smtp.gmail.com |
|199| Requer TLS/SSL | Sim |
|269| Porta| 587 |


* Configurar o IMAP

|ID | Descrição | Exemplo |
|---|-----------|---------|
|23 | Servidor de recebimento de e-mails (IMAP) | imap.gmail.com |
|24 | Endereço de e-mail | your.email@gmail.com |
|25 | Senha | Sua senha do Gmail |
|26 | Protocolo (imaps, pop, etc.) | imaps |
|27 | Porta | 993 |
|28 | Caixa de E-mail | inbox |
|72 | Quantidade de mensagens carregadas | 10 |
|199| Requer TLS/SSL | Sim |