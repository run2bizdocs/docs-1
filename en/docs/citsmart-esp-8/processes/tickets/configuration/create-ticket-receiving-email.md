title: Automatically create a ticket from the receiving of an email
Description: Allows to automatic create ticket when an email message is sent to a a certain address.
#Automatically create a ticket from the receiving of an email

This functionality allows to automatic create ticket when an email message is
sent to a a certain address. In this context, the solution constantly monitors
the presence of messages in the mailbox, and if some message has the status of
not read, this will be used to register a new ticket.

For example, an user should request a service by sending a message to
service\@company.com, after receiving the email, the functionality, after check
the existence of a message, automatically registers the ticket. It's important
to highlight that after the ticket registration, the email is marked as read.

Before getting started
--------------------------

To create a ticket through email receiving, it's necessary to configure an email
account to allow the access through IMAP.

Procedure
-------------

*Step 1*

1.  Access the functionality through the main menu System \> Automatic actions
    \> Incident/Request/Procedure Actions (see knowledge Register automatic
    actions of incident/request/procedure).

*Step 2*

1.  Create the email automatic action by accessing the main menu System \>
    Settings \> Automatic Action Setting Via Email (see knowledge Create
    automatic action via email).

*Step 3*

1.  Create batch routine, by accessing the main menu System \> Batch Processing
    (see knowledge Batch Processing):

    -   Download script attached.

Related
-------

[Register automatic actions of incident/request/procedure](https://docs-dev.citsmart.com/en/site/citsmart-esp-8/3-additional-features/automation-of-operation/configuration/register-automatic-actions-incident-request-procedure.html)

[Create automatic action via email](https://docs-dev.citsmart.com/en/site/citsmart-esp-8/4-platform-administration/configuring-automatic-actions/email-create-automatic-action-via-email.html)

[Batch Processing](https://docs-dev.citsmart.com/en/site/citsmart-esp-8/4-platform-administration/configuring-automatic-actions/batch-batch-processing.html)


<i class='fa fa-youtube-play  fa-2x' style='color:#97ce17;vertical-align: middle;'> </i> [Video Library](https://www.youtube.com/playlist?list=PLB5qK2uzf2RNemh0QXhtOXntvZ6G6o2B_)'

Attachment
------------

[Download](images/verify-email.txt)

![Download](images/verify-email.txt "Download")

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/07/2019 – Anna Martins
