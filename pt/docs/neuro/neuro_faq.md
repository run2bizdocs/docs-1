Title: FAQ (Neuro)
Description: CITSmart - FAQ

#FAQ (Neuro)

??? Question "Qual a diferença entre criar um formulário através do menu Formulário e através do menu Objeto de negócio?"
    A criação através do menu de Formulário ocorre de forma 100% manual. Através do menu de objeto de negócio, é possível gerar o formulário a partir do modelo do banco de dados. O formulário gerado poderá ser editado no menu de cadastro de formulário.

	Como eu crio um menu para acessar o meu processo de negócio?

	A criação do menu para processo de negócio é feita no próprio cadastro de processo de negócio, definindo o campo "Menu associado".

	É necessário que esteja previamente cadastrado um menu com dois níveis para que ele possa ser vinculado à este processo de negócio.

	Também é necessário que, após salvo o processo de negócio com menu associado, seja atribuído permissão para o item de menu novo. A atribuição de permissão pode ser realizada através da tela de Menu ou da tela de Perfil de Acesso.

??? Question "Como eu crio relacionamentos "muitos para muitos" no objeto de negócio?"
	Para criar um relacionamento "Muitos para muitos", é necessário criar um objeto de negócio terceiro para relacionar os dois objetos de negócio desejados.

	Ex: Vamos criar um relacionamento muitos para muitos entre dois objetos, A e B. Para isso, iremos necessitar de um objeto C que irá relacionar os dois.

	O objeto A terá um relacionamento "um para muitos" com o objeto C, e o objeto B também terá um relacionamento "um para muitos" com o objeto C.

	Dentro de nosso objeto C teremos de ter dois relacionamentos, um deles "muitos para um" com o objeto A e o outro "muitos para um" com o objeto B.

	Assim, podemos relacionar um dado do objeto A à vários dados do objeto B, e um dado do objeto B à vários dados do objeto A, através do objeto de negócio C, tendo efetivamente um relacionamento "muitos para muitos"

??? Question "I would like to know if every workflow must have a business process?"
	Not every workflow must have or needs a business process. Every Main Workflow needs a business process, however the sub-processes don't require other business processes.

	In addition, this this rule only applies to process integration flows. The service integration flows do not require a related business process.

??? Question "Is there any alternative to access my workflow tasks opened in a customized menu? I mean, out of task management?"
	You can make your own task list to access the workflow tasks. For a complete tutorial, please check the technical documentation.

??? Question "Is it possible to create customized components that can be used in the forms creation?"
	You can create your own components that will be used in the form. For a complete tutorial, please check the technical documentation.

??? Question "Where should I start building an application using the Neuro?"
	It is recommended that the first step to be executed on the Neuro, is to register the application or register a connection to the DB (database), according to the needs of the application.

??? Question "How does it work the dependency injection in a Neuro form? Which steps must be performed?"
	To inject a dependency , you must register it before. Only CSS and Javascript dependencies types can be injected in a Neuro form.

	Create a new register according to the dependency type. It can be done via menu "Neuro → resources" and upload the dependency.

	To import it on the form, select the tab “page type” that you would like to import and choose the tab "Dependencies".

	Click on the "+ add" icon to add a new dependency, in the field "name" enter the name of your resource dependency and select the corresponding option. For more information about form dependencies, please check the technical documentation.

??? Question "How do I define the actions that should be available in each workflow task?"
	The actions are registered in the main register flow tabs. To associate an action to a specific task, go to the workflow design, open the element properties, and select the desired actions. After all that is done, save your changes.

??? Question "How do I delete an element from the workflow?"
	To delete a workflow element, select the element you want to delete, and then press Ctrl + Del.

??? Question "What do I do when I get this error message "business process not informed"?"
	This error occurs because the business process is not referenced in the controller of the form that starts the business process. To fix this problem, access the business process form, and then insert the following command on the controller "p/process Page": $scope. businessProcessName = ' name_of_the_business_process';

??? Question "I would like to know, when I register a sub-process, the information in the main process is inherited by the sub-process?"
	No, it doesn´t inherit. When you include a new sub-process, BPE or ESI in the main workflow, you must inform the "attributes", the exact name of the sub-process that must be created on the workflow registration.

	All information, such as actions and main workflow status should be replicated in the sub-process registration.

	In short steps, it is recommended to follow the following order:

			1. Register the main workflow;
			2. Register the sub-process;
			3. Include the element of sub-process, making a reference to the sub-process already created.

??? Question "What is the difference between a process integration workflow and a service integration workflow?"
	The process integration workflow has tasks performed by users, and may also have automated tasks performed by the system.

	The service integration workflow has workflows that were executed, based on system services, such as integrations and conversions, for example.

	There is no problem if a process integration workflow uses a sub-process of the service integration workflow.
	
	!!! tip "About"
    <b>Updated:</b>17/01/2019 - João Pelles Junior