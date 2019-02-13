title: Configure mobile options
Description: Intended to configure the Menu options to the use through mobile.
#Configure mobile options
This functionality is intended to configure the Menu options for the mobile usage.

Before getting started
--------------------------

It's necessary to previously install the CITSmart Enterprise ITSM application in
the mobile.

Procedure
-------------

1.  Access the functionality through the main menu Access and Permission \>
    Setting up mobile options;

2.  Click on "New";

3.  Complete the fields necessary (title, status, description in the three
    languages of CITSmart [English, Portuguese and Spanish], and select the menu
    that best fits to your needs);

4.  Click on "Save".


!!! Abstract "ATTENTION"

    In order for the field technician to see tickets only assigned to him/her 
    in the request list, the attendant/manager must set the parameter 435 to "Yes".

### Get signature in field service


The option for a technician, to collect signature from a validator 
in the field, will follow the configuration:

*In CITSmart*

1.  Access the main menu Processes \> Portfolio and Catalog Management \>
    Portfolio;
    
2.  Search for the portfolio and click on "Advance";

3.  Select the service and click on "Advance";

4.  Click on the tab **Contract**;

5.  Select the contract and click on "Advance";

6.  Click on the tab **Requests**;

7.  Select the activity and click on "Edit";

8.  Configure the option "Yes" the field **Requires signature on Mobile**;

9.  Click on "Save".

*In mobile*

1.  When capture a ticket (using mobile), the technician must complete the fields
    available and, when put the ticket with the status "Solved", the field **Signatures**
    will be enabled so it'll be posible to put the Number of the register, Name and Signature
    of the validator in field. This signature will be done with the finger in the mobile screen;
    
2.  Click on "Options" and then on "Save and advance flow";

3.  The ticket will not appear anymore in the technician list.

4.  The attendant/manager will see in his/her request list (at CITSmart), the ticket attended
    by the technician (via mobile) with the status "Solved" and when openning it, it'll see the
    signature gathered.



Related
-------

[CITSmart Enterprise ITSM Mobile application user guide (Android)](/en-us/citsmart-esp-8/additional-features/mobile-and-field-service/apps/citsmart-app-android.html)

[CITSmart Enterprise ITSM Mobile Application user guide (iOS)](/en-us/citsmart-esp-8/additional-features/mobile-and-field-service/apps/citsmart-app-ios.html)

[Configure parametrization - ticket](/en-us/citsmart-esp-8/platform-administration/parameters-list/configure-parametrization-ticket.html)


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/08/2019 – Anna Martins
