title: Register ticket related
Description: This functionality allows to register a ticket with activities related to the original ticket.
#Register ticket related
This functionality allows to register a ticket with activities related to the original ticket.

Before getting started
--------------------------

It's necessary to previously register the employee, contract and unity. It's
also necessary to link the group to the contract, unit to the contract and
contract to the service.

Register the portfolio with services and activities of request and incident. Set
the time of attendance for the activities of request and incident.

Link the activities of request and incident to the service contract. Set the
parameter 385 with value 'Y'.

Procedure
-------------

1.  Access the functionality Ticket Management through the main menu Processes
    \> Request and Incident Management \> Service Request and Incident;

2.  Click on the ticket you want and select "Create Related Request" in the
    options menu;

3.  Complete all mandatory fields and click on "Save'. The ticket related will
    be directed to the executor group defined in the activity link registration,
    to the executor group defined in the parameter 9;

4.  Note that the system will send notification e-mail about the creation,
    escalation, capture, close and other changes in the related tickets to the
    executor group of the main ticket.
    
5.  To search for tickets related, it'll be necessary to select the filter "Display related" in ,
    the search area in the main screen of the functionality.
    
!!! Abstract "ATTENTION"
    
    The tickets related for not having own flow, it'll be automatically closed,
    as well as the closure of the ticket origin.
    
!!! Abstract "ATTENTION"

    Regardless of whether the parent ticket is reopened or remains closed, its 
    related tickets cannot be reopened, since they do not have their own flow.

Related
-----------

[How to relate group to contract](/en-us/citsmart-esp-8/processes/tickets/configuration/relate-group-to-contract.html)

[How to relate unit to contract](/en-us/citsmart-esp-8/processes/tickets/configuration/relate-unit-to-contract.html)

[Register a contract](/en-us/citsmart-esp-8/additional-features/contract-management/use/register-contract.html)

[Register a service](/en-us/citsmart-esp-8/processes/portfolio-and-catalog/use/register-a-service.html)

[Configure service attributes](/en-us/citsmart-esp-8/processes/portfolio-and-catalog/use/configure-services-attributes.html)

[Create the portfolio](/en-us/citsmart-esp-8/processes/portfolio-and-catalog/use/create-the-portfolio.html)

[Create time of attendance](/en-us/citsmart-esp-8/processes/service-level/configuration/create-time-attendance.html)

[Register employee](/en-us/citsmart-esp-8/initial-settings/access-settings/user/register-employee.html)

[Register unit](/en-us/citsmart-esp-8/platform-administration/region-and-language/register-unit.html)

[Configure parametrization - system](/en-us/citsmart-esp-8/platform-administration/parameters-list/configure-parametrization-system.html)

<i class='fa fa-youtube-play  fa-2x' style='color:#97ce17;vertical-align: middle;'> </i> [Video Library](https://www.youtube.com/playlist?list=PLB5qK2uzf2RNrJnhiXj3dbmgsm9-quhfz)'

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/03/2019 – Larissa Lourenço

