Title: Financial Cost Calculation
Description:

# Financial Cost Calculation

## Before getting started

It's necessary to have defined the access permission to the functionalities of the Financial Management and have permission of usage the functionality.

It's necessary to have done the financial entries, created the financial cycles and classifications.  

Based on the financial entries [Register financial item](https://documentation.run2biz.com/en-us/4biz-helium/processes/financial/use/register-financial-item.html) and the tabs "cost distribution" and "set price" it is possible to monitor all cost details (Hardware purchase, hardware maintenance, software purchase, software licenses, facility including utilities, personnel, etc.) according to the financial entry.  
This monitoring of cost details can also be done through reports.

## Procedure

1 - Access the main menu Processes > Financial Management > Financial Cost Calculation

2 - In the Financial Cost Calculation main screen, we have the following actions available:

|Action|Description|
|------|-----------|
|New| To create a new financial cost calculation|
|Generate CSV report| To generate a report of CSV|
|Advanced Filters| To set the filters to find a cost calculation already created|
|Edit| Once selected a cost calculation already created, this option will appear to edit it|
|Remove| Once selected a cost calculation already created, this option will appear to remove it|

## Registering/Editing Financial Cost Calculation

1 - To create a new cost calculation, click on "New";

2 - To edit a cost calculation already created, search for it, click on it and then on "Edit";

3 - Select the period you want, for example, 12 months (January to December);

4 - Select the service you want to make the financial calculation;

5 - Enter the minimum rate.

!!! abstract "Info"

    On a simulation, mark on the "Forecast" checkbox.

|Field|Description|
|-----|-----------|
|Start date(\*)| The start date for the cost calculation|
|End date(\*)|The date to finish the cost calculation|
|Service(\*)|Select the service you want to make the cost planning|
|Minimum rate(\*)|Set a value for the minimum rate|
|Forecast(\*)|Select to forecast the cost|

(\*) Indicate mandatory fields

!!! abstract "NOTE"

    Select the start date and end date to make the 12-month Plan.
    
4 - After complete the fields, click on "Generate" to present the values. It'll generate three tabs for values information:

### Calculation of NPV and IRR

Based on the information added in the "Financial Item" functionality, the tool will present the values according to the information and calculation presented in the fields:

|Field|Description|
|-----|-----------|
|Month|The month of reference to present the costs|
|Investment|The value of investment|
|Revenue|The value of the revenue|
|Cost/Expense|The value of cost/expense|
|Result|The value of result|
|Present Value|The present value|
|Net present value| The net present value|
|Internal rate of return|The value for internal rate of return|

### Cost by Category

This tab presents the appropriation of costs by categories. The categories are: Investments and Cost distribution.

**Investments**

|Field|Description|
|-----|-----------|
|Category|The category of the distributed cost|
|Scenario variation|The percentage for the variation of scenario|
|Cost|The fixed cost number|
|%|The percentage reached|
|Total|The final value of the investment|

!!! tip

    Scenario variation: this field allows to make financial variations

**Cost distribution**

The calculated costs will be appropriated in the respective services and configuration items according to the apportionment or fixed values defined in the financial entries on the [Register Financial Item](https://documentation.run2biz.com/en-us/4biz-helium/processes/financial/use/register-financial-item.html) and will be automatically associated with the service and the CI.

!!! tip "Example"

    Roll-up cost of a customer-facing service (e.g. email) with the breakdown of the costs for the systems (e.g. MS Exchange, Lotus Notes) and the associated supporting IT infrastructure (e.g. servers, databases, network, storage) and applications. 

|Field|Description|
|-----|-----------|
|Category|The category of the distributed cost|
|Scenario variation|The percentage for the variation of scenario|
|Cost|The fixed cost number|
|Cost breakdown|The breakdown cost|

!!! tip

    Scenario variation: this field allows to make financial variations

At the end of the page, we'll have the information about: **Number of months, Investment apportionment per month, Average cost per month and Total cost per month**

### Set Price

Complete the fields available to set the prices. In the "How to price" field, select how to make the price, the options available are: Fixed value, Variable value or Both.

If you select the **Fixed value** option, complete the fields:

Based on the selected service in the previous tab "Cost by category", the costs for the selected service will be displayed and the final service price (Final price) using will be calculated "cost" and "profit" fields.

The calculated values may be updated and published in the service catalog and in the service level agreement (gold, silver and bronze).

|Field|Description|
|-----|-----------|
|% Profit margin|Set the margin you want to work with|
|Cost|Set the fixed cost|
|Final price|The final price for the fixed value|

If you select the **Variable value** option, complete the fields:

Based on the service selected in the previous tab "Cost by category", the costs for the selected service will be displayed and the service price will be calculate using the fields "estimated quantity", "Monthly unit value" and "Profit Margin".  
The fields "estimated quantity" and "Monthly unit value" are related to the demand metrics and will be calculated through the "Integration flow of quatity capture" to generate the varied price, respecting the business rules and the profit margin.

The calculated values may be updated and published in the service catalog and in the service level agreement (gold, silver and bronze).

|Field|Description|
|-----|-----------|
|What is the unit of measurement|Set the unit of measurement|
|Estimated quantity|Set the amount|
|Do you accpet less than expected quantity?|Select if you accept it or not|
|Monthly unit value|Once completed all values in the previous fields, it'll appear the monthly unit value, with the information of: % Profit margin, Cost and Final Unit Price|
|How to calculate the amount monthly|Select how the calculation will be made: Informed manually or Automatically calculated|
|Integration flow of quantity capture|Integration with internal and external systems to capture the amount of (access, services, working hours) made|

!!! tip

    In the "How to calculate the amount monthly", if it's selected "manually", the values should be manually informed; if it's selected "automatically", the integration workflow should be selected to the contabilization of services executed.  
    For the "How to price" field, at the **Both** (fixed and variable costs) option, it's possible to set a fixed cost for some cases and, if the number is not reache, it's possible to use variables costs.

    <b>Product/Version:</b> CITSmart | 9 &nbsp;&nbsp;
    <b>Updated:</b> 04/02/2020 - William Costa
