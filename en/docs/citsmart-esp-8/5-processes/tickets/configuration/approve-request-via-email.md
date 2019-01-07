title: Approve request via email
Description: Intended to approve or reject the ticket request through email, without the need of the manager being logged.
#Approve request via email
This functionality is intended to approve or reject the ticket request through email, without the need of the manager being logged.

Before getting started
--------------------------

In order to configure the email in the ticket, it's necessary to pre-register
the user, the group and configure parameters 33 and 370 according to the
guidelines of the system-related parametrization rules. It's also necessary to
know how to design the request approval flow via email registered. In this flow,
there should be the "Approval" task and the design for sending the email,
registering the template with the "Waiting Approval" template attached, and
thee-mail server must be configured with all the parameters for email
parameterization rules.

Procedure
-------------

1.  Access the functionality through the main menu System \> Flow Maintenance;

2.  Select the request approval flow and click on "Edit";

3.  Click on the **Diagram** tab;

4.  In the request approval flow, click on the icon  and then on the icon  to
    configure it;

5.  Register, in the **Identification** tab, the name and email template to be
    used;

6.  Configure, in the **Recipient** tab, the type of recipients (group/user) of
    the email to be sent (the system don't search the recipients via
    "Expression").

*Configure the email approval notification*

1.  Access the functionality through the menu** **System \> Settings \> Email
    template;

2.  Paste the email template available in HTML in attachment, in the Text field
    and verify the following guidelines:

-   href="{TOKEN(serviceRequestIncident, \${IDSOLICITACAOSERVICO}, VIEW, 50)};

-   serviceRequestIncident = Interface directing: this field cannot be changed
    by the user;

-   \${IDSOLICITACAOSERVICO} = Key to increment the number of the service
    request: this field cannot be changed by the user;

-   VIEW - calls the command to open the request: this field cannot be changed
    by the user;

-   MM (50) - Token expiration time in Minutes: this field can be changed by the
    user;

1.  Click on "Save".

Related
-------

Register group

Register user

Workflow maintenance

Configure parametrization – email

Configure parametrization - system


<i class='fa fa-youtube-play  fa-2x' style='color:#97ce17;vertical-align: middle;'> </i> [Video Library](https://www.youtube.com/playlist?list=PLB5qK2uzf2RNemh0QXhtOXntvZ6G6o2B_)'

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>1/7/2019 – Anna Martins
