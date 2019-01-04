title: Create time of attendance
Description: Provides a variety of actions, such as including, changing, and deleting the time of attendance 
#Create time of attendance
This feature provides a variety of actions, such as including, changing, and deleting the time of attendance of type Global (applicable to all services), Client (applicable to the contract services) and Incident/Request/Procedure (applicable to a specific service).

Before getting started
--------------------------

To register a time of attendance, it's necessary to previously register the
service portfolio.

Procedure
-------------

1.  Access the functionality Time of Attendance through the main menu Processes
    \> Service Level Management \> Attendance Time;

2.  Set the type of attendance time and click on the corresponding tab:

3.  Complete all mandatory field in **Basic Data**;

4.  In **Time of Attendance per Priority**, set the service time of attendance,
    taking into consideration the priority. The priority is used to identify the
    time required to an action to be taken. The priority goes from 1 to 5, being
    1 the highest priority and 5 the lowest. Select the priority to define the
    time:

-   **Capture**: set the time of capture of the service request, according to
    the priority selected;

-   **Resolution**: set the time of service resolution according to the priority
    selected.

1.  Before complete the fields in **Automation**, it should be properly
    parametrized, it must be properly parameterized, so it is necessary to
    execute the steps in the knowledge Creation escalation rule, except for
    parameter 190 that must be equal to 'N' in this context;

2.  Before the N minutes (informed in the time of action) and in case it doesn't
    have performed any action in the service request linked to this time of
    attendance, the system will attribute the priority and will escalate the
    execution group to the service request;

3.  In the fields of **Incident/Request/Procedure**, it will be selected the
    services to apply the configurations, taking into consideration the type of
    attendance time selected;

4.  Click on "Save".


Related
-------

Register a service

Configure service attributes

Create the portfolio

Configure parametrization – ticket

Create escalation rule


<i class='fa fa-youtube-play  fa-2x' style='color:#97ce17;vertical-align: middle;'> </i> [Video Library](https://www.youtube.com/playlist?list=PLB5qK2uzf2RMDKjZH8augISpB17EQqrrc)'

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/04/2019 - Anna Martins
