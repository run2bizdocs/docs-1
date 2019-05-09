Title: Neuro AddOns
Description: AddOns do Neuro para o CITSmar.

# AddOns

## [Ticket History][1]

[1]:addons/ticket-history.md

##Ações


###Ticket History

!!! example "Por meio dessa funcionalidade, é possível customizar a tela de inclusão de ocorrências criando um timesheet do ticket.  Na nova tela, os campos Data e Tempo foram substituídos por "Data e hora início" e "Data e hora fim". " 
![(images/imagem.png)](http://www.gmail.com)


    ```tab="URL"
    /services/request/listOccurrences
    ```

    ```tab="Atributos de entrada"
    requestNumber - número da solicitação no CITSmart. Obrigatório quando o atributo requestNumberOrigin não for informado.
    requestNumberOrigin - número da solicitação no sistema de origem. Obrigatório quando o atributo requestNumber não for informado.
    ```

    ```tab="Atributos de saída"
    Objeto da classe CtOcurrence containing:
        number - número do evento na CITSmart.
        numberOrigin - número da ocorrência no sistema de origem.
        description - descrição da ocorrência.
        date - data do registro da ocorrência.
        Hour - hora para registrar a ocorrência no formato HH:MM.
        userID - identificação do usuário responsável por registrar a ocorrência.
        origin - origem da ocorrência. Valores possíveis: EMAIL, FONE_FAX, VOICE_MAIL, PERSONALLY, OTHERS.
        category - categoria da ocorrência. Valores possibles: Creation, Monitoring, Update, Diagnosis, Investigation, Memo, Information, Return, Symptom, Outline, Executing, Exchanging, Reclaiming, Reclassification, Schedule, Suspend, Reopen, Targeting, Sharing, Cancellation Task, HomeSLA, SuspendedSLA, Approval, ReactivationSLA
        elapsedTime - tempo gasto (para categoria do tipo de execução)
        reason – motivo da ocorrência.
        task - tarefa associada com a ocorrência, contendo:
           number - número da tarefa.
           name - nome da tarefa.
           startDateTime - hora e data inicial.
           endDateTime - hora e data da execução.
           status - status da tarefa, contendo:
              code - código da localização.
              name - nome da situação.
          userId - login do usuário responsável pela execução da tarefa.
    ```

    ```JSON tab="Exemplo JSON"
    {"requestNumberOrigin":"9999"}
    ```

<hr>
<font  Size=2><b>Produto/Versão:</b> CITSmart ESP | 8.00</font> &nbsp; &nbsp;
<font  Size=2><b>Atualização:</b>07/01/2019 - João Pelles Junior</font>
	






