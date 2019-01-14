title: Enable messaging within CITSmart
Description: Gathers information pertinent to the configuration of the messaging service.
#Enable messaging within CITSmart

CITSmart provides a communication channel between the requester (Smart Portal)
and the technician (service/ticket request area) through message (email). This
communication aims to facilitate the resolution of a call. This knowledge
gathers information pertinent to the configuration of the messaging service.

Procedure
-------------

1.  In order for the messaging service to be available within CITSmart, it's
    necessary to set parameter 417 with the ID number of the e-mail template
    that contains some variables to send the message;

2.  Below are the keys for sending email:

    - \${IDSERVICEREQUEST} - Number of the ticket (public key);

    - \${COMMENTTEXT} - Description of the comment made on the messaging;

    - \${DATETIMECREATED} - Date the comment was registered;

    - \${USERNAME} - Name of user that made the comment;

    - \${REQUESTERNAME} - Name of the requester;

    - \${REQUESTRESPONSIBLENAME} - Name of the technician responsible for the
    ticket attendance.

Related
-------

[The desktop of Service Desk](https://docs-dev.citsmart.com/en/site/citsmart-esp-8/5-processes/tickets/use/desktop-of-service-desk.html)

[Configure parametrization – ticket](https://docs-dev.citsmart.com/en/site/citsmart-esp-8/4-platform-administration/parameters-list/configure-parametrization-ticket.html)

[Configure email template](https://docs-dev.citsmart.com/en/site/citsmart-esp-8/4-platform-administration/email-settings/email-templates-configure-email-template.html)

[Manage my requests through Smart Portal](https://docs-dev.citsmart.com/en/site/citsmart-esp-8/5-processes/portfolio-and-catalog/use/request-through-Smart-Portal.html)


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/10/2019 - Anna Martins
