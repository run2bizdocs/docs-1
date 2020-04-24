title: Register Financial Item 
Description: Is intended to maintain financial item.

# Register financial item

This functionality is intended to maintain financial item.

!!! faq "Do you Know ..."

    In the BI reports you could reach synthetic and analytical information about:  
    Budget, Expenses, Expected Value, Final Value, Cost Value, Main Value, ROI, Cost per Services, CAPEX, OPEX.  
    Also BI data about Apportionment by Services,  Apportionment by Business Units, Apportionment by Result Centers,  Apportionment by Accouting Accounts,  Apportionment by Projects and  Accounting Activities.  
    
!!! note "Attention to the financial entries"

    The financial entries should be done respecting the type, classification, dates, category and eventual apportionments or indicators, as those data will be processed for the calculation creation of cost, revenue, final price, variables, profit, and others. To know more, access the document [Financial Cost Calculation](https://documentation.run2biz.com/en-us/4biz-helium/processes/financial/use/financial-cost-calculation.html).
    
!!! note "Templates of cost based on SLA or service catalog" 

    The values can be directly assigned to service level agreements or service level catalog according to the business rule that will be used. To know more, access the document [Create time of attendance](https://documentation.run2biz.com/en-us/4biz-helium/processes/service-level/use/create-time-attendance.html). 

## Before getting started

- [x] It's necessary to have defined the access permission to the functionalities of the Financial Management and have created the classification, contract, cycle, subcycle and approval workflow.


## Procedure
    
1. Access the main menu Processes > Financial Management > Financial item;
    
2. Click on "New" and complete the fields available.
    
## Creating Financial Item.

Complete the fields available on the **Information** tab:

|Field|Description|
|---|---|
|Type*|Cost/Expense, Budget, Revenue|
| Classification* |(Capex, Opex, Fixed, Direct, Unit Cost, Indirect, Variable, Assessment)|
|Due Date*|The date that will expire it|
|Reference date*|The date of reference for the item|
|Forecast| it's available Only for Revenue and Costs/Expense Category (Used to simulate financial forecasts)|
|Status*|It'll be always be created as "Pending". It'll only be available if the Forecast option is not selected|
|Category*|The category for this item|
|Contract|Select a contract to be linked to it|
|Budget Account| Specific Account linked to this item. It'll only be available if the Forecast option is not selected |
|Forecast financial item| It's possible to search for a title of the forecast financial item. It'll only be available if the Forecast option is not selected|
|Cycle*|It's the financial Method, for example, Yarly, Monthly or Quarter|
|Subcycle*|Depends on the Cycle|
|Code|Freetext to create or insert financial code|
|Title*|Title of this Financial Item|
|Description|Description about your financial item|

(\*) Indicate mandatory fields
    
### Values and Apportionments

In this tab you will register The Value of a financial item and also an apportionment for it´s values detailing Apportionment by Services, Apportionment by Business Units, Apportionment by Result Centers, Apportionment by Accouting Accounts, Apportionment by Projects and Accounting Activities.

|Field|Description|
|---|---|
|Entry type|There are two types: Value - if you set value, after the "Select services", it'll be presented a list with the service and its values; Accounting for activities performed - for this option, after Select the activities, it'll be presented the list with the activity you selected, as well as its information and description|
|Expected value*| It's possible to stablish to number for the value expected|
|Main value*| Set a number for the main value|
|Additional*| Set the number for the additional|
|Final value*| Set a number for the value end|
|Apportionment| Here we have the options to set all the apportionments types: Apportionment by Services (assets and CIs), Apportionment by Business Unit, Apportionment by Result Centers, Apportionment by Accounting Accounts, Apportionment by Projects. Once you select the type, you'll add the service, business unit, result center, accounting account and project. After add it, it'll appear the value and percentage for each one of them|

(\*) Indicates mandatory field

### Knowledge 

Select a financial document already created as a Knowledge to link to the financial item, you can .

| Objects    | Description                         |
|------------|-----------------------------------|
| Add Knowledge Button | Search / Link           |
| Grid               | Grid of linked Knowledges |
| Delete Button      | Unlink Knowledge          |

### Approvals

It's possible to create approvals and verify those that have been created, approved or denied. On the list of approvals we have the following fields:

|Field|Description                           |
|-----|------------------------------------- |
|Ticket  |The number identifying the approval|
|Date    |The date of the approval           |
|Activity|The financial activity             |
|Status  |The status of the approval         |

### History

It'll be presented all the information in a Grid about the changes/actions takes and made on the financial item.
The Grid wil inform Date and time of the ocurrence, the user, wich element is involved and the action details.

## Actions

| Action  | Description                                                 |
|---------|-------------------------------------------------------------|
| Save    | Create / Change the financial item.                         |
| Clear   | Return the fields to default.                               |
| Search  | Return to the previous list of financial items.             |

## Related

- [Register financial cycle](/en-us/4biz-helium/processes/financial/use/register-financial-cycle.html)

!!! tip "About"

    <b>Product/Version:</b> CITSmart | 9 &nbsp;&nbsp;
    <b>Updated:</b> 20/03/2020 - Andre Fernandes

