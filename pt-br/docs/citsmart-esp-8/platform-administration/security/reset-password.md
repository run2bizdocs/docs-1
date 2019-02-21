title: Configurar serviço de alteração de senha
Description: A alteração de senha do usuário é uma das possiblidades permitida pelo sistema.  
#Configurar serviço de alteração de senha

A alternativa de alteração de senha do usuário é uma das possiblidades liberadas pelo sistema. Para configurar esta opção é necessário seguir os procedimentos aqui descritos.

!!! danger "ATENÇÃO"

    Esta opção está disponível apenas para autenticação de contas manuais.

Antes de começar
----------------

É necessário previamente a configuração de envo de e-mail válido (smtp), uma vez
que o envio da senha é feito via e-mail.

Procedimento
------------

*1º Passo: Criar um modelo de e-mail com a finalidade de alteração de senha*

1.  Acessar o menu principal Sistema \> Configurações \> Modelo de e-mail;

2.  Criar o modelo de e-mail com o intuito de alterar a senha;

    !!! danger "ATENÇÃO"

        Para que o usuário receba as novas informações de acesso é preciso utilizer
        na mensagem de e-mail a chave ‘${NOVASENHA}’ (exemplo de chave referente a
        “Nova senha”). Adicionalmente, é possível enviar também o login usuário
        usando a chave ‘${LOGIN}’ ( exemplo de chave referente a “Login”).  

*2° Passo: Setar a parametrização referente ao serviço de alteração de senha*

1.  Acessar o menu principal Parametrização \> Parâmetros CITSmart;

2.  Editar e salvar o parâmetro 116 atribuindo-lhe o valor numeral do ID gerado
    para o modelo de e-mail recém criado;

O que fazer depois
------------------

Para testar o serviço de alteração de senha, acessar a página inicial do
Sistema, clicar na opção “Esqueceu sua senha?”, informar um login de usuário
local e apertar “Gravar”.

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>02/21/2019 – Larissa Lourenço

