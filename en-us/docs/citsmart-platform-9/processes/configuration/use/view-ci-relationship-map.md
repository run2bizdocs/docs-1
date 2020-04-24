Title: See map of relationship of a CI

# See map of relationship of a CI

The relationship map is the place where you can visually have an overview of the relationship tree that exists between CIs and CIs and Services. There you can use several filters to shape the type of result that will be presented.

## What to do before

The visualization of the relationship map is conditioned to the following scenario:

- [X] Have performed the CI inventory and built the relationship tree (see: [Relating Configuration Item to a Service][2])

## Procedure

1. Access the functionality through the menu Processes > Configuration Management > CMDB;

2. Click on "View map of relatinship";

3. On the CI Design Map screen, the following fields are available:

| Field | Description |
|-------|-----------|
|Filter| a.  **Cause and Effect**: Standard view of the system consisting of the graphical demonstration both below and above the selected CI node; b. **Impact Analysis**: Visualization that consists of a graphical demonstration of the items drawn below the selected node; c. **Root Cause Analysis**: visualization that consists of a graphical demonstration of the items designed above the selected node.|
|Level| from 1 to 4 |
|Icons| **Arrow**: it allows to drag the map; **Magnifying glass**: it allows to increase or decrease the zoom in the map.

## View total CI capacity

It's possible to see the total of capacity and its indicators through the CI relationship map.
Moreover, The user will be able to forecast the capacity of the related CIs.The platform captures and shows all CI response times and if the total exceeds the configured limit, a notification can be sent to the user or published on the portal. 
By clicking on **View total capacity**, we have the following information:

| Field | Description |
|-------|-----------|
|Feature| The related configuration item|
|Indicator| It presents the indicators for the capacity configured by its total and medium |
|Measured| The amount measured by the tool, taking into consideration the indicators. It also presents the total and medium, however, with the addition of a visual representation of the amount used |
|Forecast| Here it's possible to forecast the total capacity, that is, you can set a percentage to inform you when a certain amount is reached. The tool will report if the current capacity is okay or if it's reaching it's fully capacity.|

## Related

[Relating Configuration Item to a service][1]

[1]:/en-us/citsmart-platform-9/processes/configuration/use/create-ic-relationship.html

[2]:/en-us/citsmart-platform-9/processes/configuration/use/create-ic-relationship.html
