title: CITSmart Enterprise ITSM Mobile Application user guide (iOS)
Description: Intended to provide guidance for installing, configuring, and using the CITSmart ITSM Enterprise mobile application (iOS plataform).
#CITSmart Enterprise ITSM Mobile Application user guide (iOS)

This document is intended to provide guidance for installing, configuring, and
using the CITSmart ITSM Enterprise mobile application (iOS plataform).

It offers several features, such as:

1-  Facility in service and have a direction of where the request is located;

2-  Filter personal and work group requests;

3-  Viewing the details of a service request;

4-  Receipt of notifications.

This document is structured in three major sections:

1-  Before getting started

2-  Installing and Configuring the App on the Mobile;

3-  Using the App on Mobile.

Before getting started
----------------------

It´s necessary to use CITSmart Enterprise ITSM solution in version 7.2.2.0
or higher, setup the server for using CITSmart Enterprise mobile
application.

Installing and configuring the app on the mobile
------------------------------------------------

To install CITSmart ITSM Enterprise, the app must be searched in the online
store (App Store).

1-  Search for CITSmart ITSM Enterprise on App Store, select and download
    the app;

2-  After installation, the CITSmart ITSM Enterprise icon will appear;

3-  The connections screen will be displayed, press the “Create connection”, as
    shown in the figure below:

![Connection screen](images/ios-app-1.png)

Figure 1 - Connection screen

4-  The "New connection" screen for connection registration will be displayed:

![Connection log screen](images/ios-app-2.png)

Figure 2 - Connection log screen

5-  Enter the relevant data:

   +  Connection name: enter the name of the connection you want to
        connect to;

   +  Server URL: enter the server address for the connection. The
        protocol (https) must be placed in the URL;

   +  Main connection?: inform if the chosen URL will be the primary ;

   +  Domain \\ User: From this version the user will have to inform the
        use LDAP domain and its user;

      +  The format is citsmart.local\\user.consultor (example), where the first part
         is the domain information and the second part is the user;

   +  Password: The user will enter the password to access the system;

   +  Available:

      +  Enabled: When enabled, the connection will be provided in the URL field,
         and in addition, to get the position of the attendant this field must be
         enabled;

      +  Disabled: When disabled the system will not allow connection to the
         server nor will it pick up the position of the attendant.

!!! Abstract "ATTENTION"

    If the device is changed, this connection must be deleted.  

6-  After entering the desired connection data, press the *Create* button;

7-  After the connection is added, the list of created connections will appear.
    To change a connection, simply select the desired connection and make the
    change;

8-  To connect, just select the connection, in the initial screen of the
    application;

9-  Enter the username and password:

![Connection](images/ios-app-3.png)

Figure 3 - Login screen


Using the app on the mobile
---------------------------

### Viewing service requests

1-  After the connection is made, the menu screen will be displayed, where you
    can click on the Service Ticket:

![Login screen](images/ios-app-4.png)

Figure 4 - Menu screen


2-  To choose the type of request you want to view, click on the icon  located
    in the upper left corner;

![Menu screen](images/ios-app-5.png)

Figure 5 - Request search screen


3-  Will be presented filters:

![Request search](images/ios-app-6.png)

Figure 6 - Filters

![Filters](images/ios-app-7.png)

Figure 7 - Filters (continuation)


4-  Select the filter of request you want and click on the “Search” icon, in the
    lower left corner;

5-  The list of service requests will be displayed, depending on the filter
    chosen:

![continuation](images/ios-app-8.png)

Figure 8 - Ticket list


!!! Abstract "RULE"

    In order for the search functionality to work, it is necessary to
    configure the corresponding web service (notices) in the "Web Service
    Operation Register" screen in CITSmart Enterprise Web.  

6-  In each request, when you click on it, a list of options is displayed,
    being:

![Ticket list](images/ios-app-9.png)

Figure 9 - Ticket list


-  “Open” icon - capture the request to the logged in user or just view the
    ticket without capturing;

-  “View” icon - view the ticket;

-  “Description” icon - shows the summary of the request;

-  “Message” icon - view messages;

-   “Reports” icon- show ticket reports;

-  “More options” icon - options menu for the request (Delegate, Suspend,
    Change SLA, Reclassify, Create sub-requests, Show sub-requests, Schedule
    activity, Create related request and Print Request).

### Creating service request

1-  To create a service request, press the “Operations” icon located in the
    lower right corner of the screen and select the "New ticket" option, as
    illustrated below:

![Ticket lists](images/ios-app-10.png)

Figure 10 - Creating a service request

!!! Abstract "ATTENTION"

    The request registered by CITSmart ITSM Enterprise uses services that are
    configured in CITSmart Enterprise Web.  

2-  After performing the operation, the request registration message will be
    displayed.

![Creating a service](images/ios-app-11.png)

Figure 11 - Create request

![Creating request](images/ios-app-12.png)

Figure 12 - Create request(continuation)

![Create reques](images/ios-app-13.png)

Figure 13 - Create request (continuation)

![request continuation](images/ios-app-14.png)

Figure 14 - Create request (continuation)

3-  Fill in the fields as described below:

-  Applicant: enter the name of the applicant, that is, the name of the
   person requesting the opening of an incident or service request.

!!! Abstract "ATTENTION"

    After reporting the requester a statistical summary of the calls of him is
    shown (per situation), as well as another statistical summary of
    satisfaction (per type of response) about the services already requested by
    him. These two summaries are paginated, thus it is possible to move
    forward/backward to view all the information preserving performance and
    screen lay-out.  

-   Phone: enter the telephone number of the applicant;

-   Extension: enter the extension number of the applicant, if applicable;

-   E-mail: inform the requestor's e-mail;

-   Contact Origin: enter the origin of the contact to register the service
    request;

-   Unit:select the unit on which the applicant is full;

-   Physical Location:state the location of the applicant;

-   Other Information: describe the observations about the applicant, if
    necessary.

4-  Record service request information:

   +  Catalog: select the catalog of services;

   +  Service: enter the service for the selected service catalog. If the
      service catalog is "**Business**", the business services for selection
      will be available in this field, but if the service catalog is
      "**Technical**", the support / technical services for selection will be
      available in this field;

   +  Type: select the type of request, whether it is an incident opening
       or service request;

       +  Incident: if the situation presented is an unplanned outage, a
          reduction in the quality of the service or failure of any
          configuration item that has not yet impacted an IT service. Eg: The
          network link is out, the network is slow, the server is
          inaccessible, etc.

        +  Request:refers to requests for demands made by users within the
           Information Technology environment. They can range from access
           requests to suggestions for improvement at low cost. Ex .: request
           of access to the network for a new user, request of configuration of
           some equipment, request to add some software in the workstation,
           etc.

   +   Category: enter the category of service to facilitate the search of the
       activity (Request / incident). The category will identify the nature of the
       activity, positioning it within similar groups of action, placing it in the
       hierarchy of its category;

   +   Activity (Request / Incident): inform the activity that will be
       performed referring to the type of request. If the reported activity has a
       "Guidance Script" associated with it, it will be displayed in the "Scripts"
       tab represented by the icon  located in the upper right corner of the
       screen;

   +   Contract: after informing the activity (Request / incident), the
       contract will be displayed for which the opening of an incident or service
       request will be made;

   +   Urgency: after informing the activity (request / incident), the urgency
       information will be displayed which indicates the speed at which the service
       needs to be performed;

   +   Impact: after informing the activity (Request / incident), the impact
       information of the service to the business will be displayed;

!!! Abstract "RULE"

    After informing the Request / incident activity, the expected time to
    fulfill the request will be established, as configured in the record of the
    time of service related to the activity. The service time will be counted
    according to what was defined in the calendar linked to the unit, but if the
    unit does not have a linked calendar, it will be accounted according to the
    calendar linked to the service. However, when closing the expected time of
    attendance is counted the delay in time, being disregarded the calendar.  

   +   Title: enter the title of the service request;

   +   Description: enter the description of the service request. The
       description must be objective, including all the information necessary to
       attend to it;

   +   Head to group: enter the group to which the service request will be
       directed. If you do not inform the group, the request will be directed to
       the executor group defined in the record of the link of the Request /
       incident activity to the contract. But if the executor group is not defined
       in the record of the link of the Request / incident activity to the
       contract, the request will be directed to the executor group defined in
       parameter "9 - Group ID Level 1";

   +   Notifications: check the options for sending notification of the request
       to be sent to the requestor;

   +   Execution Record: it is not necessary to fill in this field, as it is
       indicated for the technician who will attend the request, to describe the
       execution of his activity.

   +   Situation: select the option that fits with the current status of the
       request: Registered / In progress.

### Approving/rejecting service request

Some requests need approval, so to meet them you need to approve them.

1-  Select the request that is eligible for approval;

2-  The "Details" screen will be displayed displaying the description of the
    request for approval / rejection of the request;

![Create requ](images/ios-app-15.png)

Figure 15 - Request approval/reject screen


3-  To approve the request, just press the Approve button;

4-  To reject the request, press the Reject button. A screen will be displayed
    to choose the justification for this rejection, as shown in the figure
    below:


![approval](images/ios-app-16.png)

Figure 16 - Request rejection screen justified

-  Choose the justification for rejecting/approve the request and press the
    “Save and forward the Flow” button.

Related
-------

[CITSmart Enterprise ITSM server configuration manual for use of APP (iOS and
Android)](https://itsm.citsmartcloud.com/citsmart/pages/knowledgeBasePortal/knowledgeBasePortal.load#/knowledge/4342)

[Configure mobile options](https://docs-dev.citsmart.com/en/site/citsmart-esp-8/3-additional-features/mobile-and-field-service/configuration/configure-mobile-options.html)


!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/11/2019 - Anna Martins
