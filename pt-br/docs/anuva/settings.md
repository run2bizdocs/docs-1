Title: Configuração

# Configurações

## Parâmetros

### O que é acurácia?

Podemos entendê-la como o nível de entendimento do que o usuário está dizendo ao
assistente, se o texto digitado pelo usuário precisa estar exatamente igual ao
construído ou se a partir de certo ponto de compreensão do texto o assistente já
pode seguir o fluxo de conversação planejado.

O assistente somente dará continuidade no diálogo se acurácia de entendimento
dele em relação a frase digitada pelo usuário for maior que o valor cadastrado
nesta página. Caso contrário o assistente virtual iniciará o fluxo cadastrado de
fallback.

**Exemplo:** Supondo que no diálogo foi construída a saudação “Bom dia!” e a
acurácia está marcada para 100%. Se o usuário escrever “bom dia?” o seu
assistente não vai compreender o que foi dito e apresentará mensagem de
fallback. Somente será dada continuidade no fluxo de conversa se o usuário
digitar “Bom dia!”, exatamente como foi construído.

Quanto melhor seus exemplos de diálogos e cadastros de intenções, melhor será
seu assistente. Então é importante definir qual o cenário que o assistente irá
atuar antes de definir o nível de acurácia. Veja abaixo o motivo:

**Níveis de acurácia:**

|Porcentagem|Descrição|
|-|-|
|Entre 0% e 30% |Em geral consideramos baixo, e portanto, há pouca certeza de que os diálogos irão corresponder ao planejado. Quando se tratarem de validações de identidade e login o risco é elevado para sua organização.|
|Entre 30% e 70%|São considerados médios, apresenta risco moderado. Dependendo do nível de informações que irão validar, podem valer a pena.|
|Entre 70% e 100%|Representa baixo risco e chances maiores de precisão das informações.|

**Notificações**

Área para gerenciamento de quais administradores do sistema precisam receber as
notificações de atualização do assistente.

São enviadas três tipos de notificações:

|Função|Descrição|
|-|-|
| Agendamento iniciado  | E-mail enviado para notificar que o treinamento agendado foi iniciado.|
|Treinamento concluído|Enviado quando o treinamento foi concluído com sucesso e o assistente está disponível com os novos aprendizados.|
|Falha no processo|Notifica o administrador da plataforma que a atualização não pôde ser realizada, o motivo e a solução.|
|| Exemplo: Treinamento não realizado. Você precisa cadastrar mais três frases na intente, pois o mínimo de frases para atualização acontecer são quatro frases.                                                                                                       |

*Temos a lista de pendências????\*\*\*\*\*\**

**Procedimento**

1.  No campo “Digite para adicionar um e-mail” digite o e-mail que receberá as
    notificações;

2.  Clique o botão Adicionar;

3.  Depois de adicionado, é possível excluir o e-mail.

-   **Migrações**

Esta área permite que utilize o case ou cenário construído no IBM Watson no
Helper, sem a necessidade de reconstrução dos fluxos de conversação nesta
plataforma.

**Procedimento**

1.  Clique na opção IBM Watson;

2.  Na aba Configurações preencha os campos Chave da API, URL, Usuário, Senha e
    Versão com estes dados fornecidos na plataforma IBM Watson;

3.  Serão apresentados na aba Importações os Workspaces disponíveis para
    importação da plataforma IBM Watson;

4.  Selecione o Workspace que seja importar;

5.  Clique o botão Salvar.

6.  A aba Histórico de Importações apresentará o nome do workspace importado, a
    data de importação e status da importação.

!!! note "Nota"

    Pode ocorrer do tipo de frase ou opção não ser compatível com o Helper e por
    este motivo a importação, somente deste item, não ocorrerá. Neste caso será
    necessária a conferência e criação manual do trecho não importado.

-   **Importação/Exportação**

Nesta área é possível importar diálogos por intent e exportar os diálogos
existentes no seu assistente também.

Continua sendo necessário agendar um treinamento após a importação dos diálogos
para que o Helper aprenda esses diálogos importados também.

**Procedimento de exportação**

7.  Clique o botão exportar;

8.  O sistema irá iniciar o processo de download do arquivo, que será entregue
    em formato .xlsx.

**Procedimento de importação**

1.  Em uma planilha de formato .xlsx, crie três colunas nesta ordem: Intent,
    User Says, Text Response;

|Função|Descrição|
|-|-|
|Intent| Nome da intenção cadastrada no Helper.Exemplo: 1.0 Saudações ao Usuário Logado|
|User says|O que a pessoa que está sendo atendida pelo assistente pode dizer. Sendo cada hipótese em uma linha diferente.Exemplo: Olá, boa noite|
|Text Response| O que o assistente deve responder a esta fala.Exemplo: Olá, eu sou o Helper, seu novo assistente virtual. Estou aqui para simplificar o seu processo de atendimento e ajudá-lo em suas necessidades. Basta digitar o que precisa que eu vou te ajudar!|

!!! exemple "Exemplo"

    ![](media/a328388ce8570d6d775a9829ac12bac4.png)

    1.  Salve a planilha;

    2.  De volta a página de Importação/Exportação clique o botão Importar;

    3.  Clique o botão Escolher arquivo;

    4.  Localize a planilha salva;

    5.  Clique o botão Importar.

!!! note "Nota"

    Somente poderão ser importadas respostas em formato texto. As demais opções
    (botão, imagem e carrossel) ainda não estão disponíveis nesta
    funcionalidade;

    Caso queira refinar diálogos existentes, exporte, ajuste, e importe
    novamente. A importação substitui o conteúdo, então, caso você retire alguma
    frase existente na planilha que foi exportada, quando for importada o
    sistema irá apagar a(s) frase(s) retiradas da planilha.

!!! info "Dica"

    Utilize o procedimento de atendimento (FAQ ou SAC) que sua organização
    já possui (caso possua) em formato de perguntas e respostas para montar essa
    planilha. Aproveite o conhecimento que já existe no seu ambiente para aprimorar
    seu assistente virtual.
