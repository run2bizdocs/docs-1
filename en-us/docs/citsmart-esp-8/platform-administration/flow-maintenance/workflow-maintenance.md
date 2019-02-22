title: Workflow maintenance
Description: Designed to model your business objectives, describing the steps that need to be taken to achieve those goals through a flowchart.
#Workflow maintenance

Flows are visual representations of something that moves continuously.
The Flow Maintenance is designed to model your business objectives, describing
the steps that need to be taken to achieve those goals through a flowchart.

Procedure
-------------

1.  Access the main menu System \> Flow maintenance;

2.  It's presented the homescreen of the functionality. The following activities are
    available here.
    
    - We can search for flows already registered when clicking on "Advanced filters"
      and complete the data;
      
    - In the "Edit" button there may be several versions of the same flow;
    
    !!! Abstract "NOTE"
        
	    The deletion will only be possible if the flow has no services linked to it.
	    
3.  When click on "Edit" and select any version of the flow, it'll be presented the
    flow information in three tabs: "Flow data", "Diagram" and "Documentation".
    Each one has the following function:

-   In the tab "Flow Data", it'll be presented data about the flow, for example: name,
    process linked (the flow will be visible only for the process linked to), version,
    flow description and the option to enable the reopening of a service, regardless
    of the group configuration.
    
    !!! tip "TIP"
    
        The option to reopen the flow can be useful in scenarios where there are many services 
        where reopening is allowed, so by selecting the option "allow reopening" it's not necessary 
        to use the "reopen" action in the flow permission.

-   The "Diagram" tap represents a design tool of flow. On the left side of the screen,
    is the organization of the elements that comprise the flow functionality. Clicking on 
    each of these elements will be accessible to each activity performed by these elements,
    which are:
    
    -   **Events:*** it presents the events elements to be used in the flow design. They are:
    
        -   Initial Event
       
        -   Intermediate Link Submission Event
        
        -   Intermediate Event of Link Capture
        
        -   Intermediate Event of Timer
        
        -   Boundary - Intermediate Event of Error Capture
        
        -   Intermediate Event of Signal Capture
        
        -   Event of Finalization with Error
        
        -   Event End
        
    -   **Activities:** the elements of activities that can be used in the flow design. They are:
    
        -   User Task
        
        -   Script Task
        
        -   Message Sending - E-mail
        
        -   Business Rule Task
        
        -   Service Task - ESI
        
        -   Data storage
        
        -   Subprocess
        
    -   **Extensions:** the extensions that can be used in the flow design. They are:
    
        -   REST Communication
        
        -   Notification
        
        -   Variable Assignment
        
        -   Watson Conversation
        
    -   **Gateways:** the elements of gateway that can be used in the flow design. They are:
    
        -   Inclusive Gateway
        
        -   Parallel Gateway
        
        -   Exclusive Gateway
        
        -   Complex Gateway
        
        -   Gateway Based on Event
        
    -   **Swimianes:** the elements of swimianes that can be used in the flow design. They are:
    
        -   Pool/Participant
        
        -   Lane
        
    -   **Artifact:** the element of artifact that can be used in the flow design. They are:
    
        -   Text Notes
        
    -   In this tab, it's also allowed to, by clicking on "Create Documentation", to export in PDF
        the information created on "Documentation". Besides, when click on "Save", we can choose how
        it's gonna to be the storage ("As a new version" means versioning  and create a new vision
        of the flow or "In the original version" that means save the flow in the current version being
        edited).
        
-  In the tab "Documentation", it's created a vision of all information of the flow
   (diagram, elements description used in the diagram).

!!! Abstract "NOTE"

    Remember that:
    
    - the rules configured in the flow will have priority over the service request template 
    markings, as this is a complement to the flow;
    
    - to use the "Watson Conversation" component, the organization must have the IBM BlueMIX ,
    architecture, thus allowing access to the Watson API Conversation;
    
    - to delete an element that was inserted in the flow design, click on it and press Ctrl+Delete.
    
Diagram of a workflow
-------------------------------------    

![Flow Diagram](images/flow-diagram.png)


-   1 - It represents the workflow start;

-   2 - It represents a user task to be performed in the flow (that in this
    case means 'receive the task');
    
-   3 - It represents the second user task to be executed in the flow (that in
    this case means 'approval or rejection of task');
    
-   4 - It represents the "Exclusive Gateway" (which represents a unique flow condition, 
    in which one of the paths created from the Gateway will be followed according to 
    information to be tested. This gateway can be represented visually as the empty diamond 
    or with an "x") of the flow;
    
-   5 - It represents the final event of the workflow (which in this case means the completion 
    or rejection of the task);
    
-   6 - It represents the third user task to be performed in the flow (which in this case means 
    'execute the task' if it has been approved).    


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/10/2019 - Anna Martins
