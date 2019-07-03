Title: Gerenciamento ágil Simple

# Simple Agile Management


Simple is a functionality of the CITSmart that allows the easy and agile
management of activities. It was created to manage projects in the simplest way,
with resources to organize, monitor and delegate the activities among the members
of your team or individually.

Simple is based on the Kanban methodology, it's visually organized in a framework
with cards that indicate the flow progress.

In the Simple workspace, activities are inserted and grouped by projects
(in Simple called Workspace), task pane (in Simple called Sprint) and finally
tasks, which can be in groups of cards.

!!! Abstract "ATTENTION"

    Permissions in the Workspace and Sprint (located on Settings > Profiles and 
    Permissions), when the *administrator* is logged in, it will be selected by 
    default and cannot be changed. Only when the user is of type *normal*, the 
    permissions will be editable.
    
!!! warning "ATTENTION"

    The language in the columns that appear on the **My notifications screen (bell icon)** 
    will follow what was set in parameter 66 (Default language of the system).

Procedure
------------

***I - Create a Workspace***

1.  Access the main menu Inegrated Management \>
    Simple – Agile Management;

2.  Click on “Workspace” and give a name to create the new Workspace;

3.  Each Workspace will have in its home screen a summary of Sprints and
    its deadlines:

    -   Expired: it presents the number of **Sprints** with the "delivery date"
    smaller than the current date/time;

    -   To be expired: it presents the numer of **Sprints** with the "delivery date"
    that will expire in 24hs from the current date/time;

    -   On time: it presents the number of **Sprints** with the "delivery date"
    bigger than 24hs from the current date/time;

    -   Total: sum of the **Sprints** inside the Workspace.

!!! Abstract "ATTENTION"

    The workspace administrator can change the project manager (administrator permission) 
    in each sprint. If the user is not the administrator of the workspace, it is not possible 
    to give the administrator permission to another user.

!!! Abstract "ATTENTION"    

    To move a **workspace** by changing its ordering, click and drag it to the desired 
    priority position.
    
!!! Abstract "NOTE"

    The search field looks for any information that is in any other workspace, sprint, list 
    or task. To optimize the search, a new filter has been created that allows selecting 
    activities by the estimated date of its development (the period of its beginning and 
    conclusion). To use it, it is necessary to follow the instructions:
    1. For the correct operation of this field it is necessary that the Workspace, Sprint 
    and activity have an estimated date of beginning and end;
    2. Make the search. The system will then return a list of Workspaces, Sprints, and 
    Activities that are among the date referenced in the search.


***II - Create a Sprint***

1.  Click on the Workspace created before;

2.  Click on “Sprint”, give it a title and "Save”;

3.  Each Sprint has in its home screen a counter of **tasks**, hours spent
    and planned, total of tasks by deadline established and its percentage of
    achievement:

    -   Expired: it presents the number of **tasks** with the "delivery date" smaller
    than the current date/time;

    -   To be expired: it presents the number of **tasks** with the "Delivery date"
    that will expire in 24hs from the current date/time;

    -   On time: it presents the number of **tasks** with the "delivery date" bigger
    than 24hs from the current date/time;

    -   Total: it presents the total number of **tasks** of the Sprint;

    -   The progress bar has the following calculation:

        -   1st It's made the sum of the tasks estimate of all completed **tasks**;

        -   2nd The sum of the total estimates of all **tasks** is summed;

        -   3rd Progress is the percentage calculated with the total estimates of 
            completed **tasks** on the total estimates of all tasks.

!!! Abstract "NOTE"

    The calculation of progress depends entirely on the estimates reported in the tasks.
    
!!! Abstract "ATTENTION"

    To move a **sprint** by changing its ordering, click and drag it to the desired 
    priority position.


![sprint screen](images/figure-1-simple.png)
    
Figure 1 - Sprint Screen


   -   **1**: search Sprints with filters of members, tag and status of the Sprint
    (completed and not completed)

   -   **2**: create new Sprint

   -   **3**: abbreviation of added member names. By clicking on it, it's possible to
    delete and define if the member will be manager or not

   -   **4**: add member that will participate in the Sprint

   -   **5**: actions of configuration and permission of the Sprint


***III - Create lists***

1.  In each Sprint it will be available a default list of the system:: “To
    do, In progress and Completed”;

2.  To create a new list, click on "+List”, give a title and "Save”.

    ![list screen](images/figure-2-simple.png)
    
    Figure 2 - List screen


    -   **1**: search tasks with filters of member, tags and status of the list
    (completed and not completed)

    -   **2**: create new list

    -   **3**: refresh the screen

    -   **4**: abbreviation for the member name added. When clicking on it, it's possible to
    delete and define if the member will be manager or not

    -   **6**: set the date, hour and hours estimated to deliver

    -   **7**: view the history of actions

    -   **8**: archive tasks list

***IV - Create tasks***

   ![task screen](images/figure-3-simple.png)
    
   Figure 3 - Task screen


   -   **1**: create new task

   -   **2**: define in which stage the task is.

   -   **3**: move the list inside the framework

!!! Abstract "NOTE"

    To move a **task** from a list to another, click and drag it to the list.

***V - Complete Simple card***

The Simple card has fields and buttons to describe a task/action with planning
and control of dates, hours, checklist and several others device of control
and management.

1.  Each card has devices of control and information:

     ![card screen](images/figure-4-simple.png)
    
      Figure 4 - Card screen


    -   **1**: add or remove members in the task

    -   **2**: add list of actions that will be viewed in the Checklist tab

    -   **3**: add comments
    
    !!! Abstract "NOTE"
    
        When you open an activity (task) in *Simple*, you can see that in the *"Comment"* 
        feature, two new functions have been inserted:
        - *Edit Comment*;
        - *Delete Comment". If you choose to delete, the comment will not be saved in the "History" tab.

    -   **4**: each member can post hours referring to their time used in the task, besides detailing the action taken

    -   **5**: add tags to visually identify the task card

    -   **6**: click to be notified of any changes in this task. This notification will be
    done through the notification button of the CITSmart

    -   **7**: indicate the completion of the task

    -   **8**: move the task to another Sprint:

        -   Sprint of the *same* Workspace: tags are retained, but members are removed from the task

        -   Sprint of *other* Workspace: the tags and members will be removed from the task

    -   **9**: archive the card – once archived, in this version, the card cannot be reused.

1.  Describe the taks in the field "Description”;

2.  Define the date and time of delivery in the field "Delivery date”;

3.  Estimate the number of hours that will be used in the task;

4.  In the field "Hours released", the system will automatically count the total;

5.  The tabs available present:

    -   Checklist: adding a checklist will create an item on this tab. To name it,
    place the mouse on "Add item...", click on add "+" to add new item. To indicate
    the completion of an item inside the checklist, select the checkbox;

    -   Comments: list of comments made;

    -   Attachments: make availabe the field to add attachmetns;

    -   Hours released: relate hours released of each member participating in the task;

    -   History: it presents all actions made in the card, with date and time.


<i class='fa fa-youtube-play  fa-2x' style='color:#97ce17;vertical-align: middle;'> </i> [Video Library](https://www.youtube.com/watch?v=yHi8-heMMxM)


!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>02/13/2019 – Anna Martins

