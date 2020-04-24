Title: Registering type of CI relationship

# Creating type of CI relationship

The registration of type of CI relationship is necessary for the management of Configuration Items (assets and services) in the CMDB. 
With this registration, it'll be possible, from a CI, to define levels of relationship between CIs.

## What to do before
The user must have access to the Relationship Type Registration screen.

## Procedure

1. Access the functionality in Processes > Configuration Management > Configuration item;

2. Complete the fields available;

    | Field | Description |
    |-------|-----------|
    | Name | Description of relationship type|
    | Status | Select: Active (status indicating that the type of relationship is available for usage) or Inactive  (status indicating that the type of relationship is unavailable for usage)|
    | Position | It defines in the map design in which position the cardinality of the configuration item will be: "Same level" - from  the selected point for the designing of the CI map, it means that the CI will be at the same level; "Upper Level" - Description of the selected point for the designing of the CI map, which will be above; "Lower Level" - Description of the selected point for the designing of the CI map, which will be below;|
    | Actions | "Save" - Enters the type of relationship; "Clear" - Returns the registration fields to their default state; "Search" Returns to the Relationship Type search;|

3. Click on "Save" to record the information.

!!! warning "ATTENTION"
    If a Relationship Type is being used in a Map design, then the system will not allow editing the Same Level position.

## Related

[Relating Configuration Item to a service][1]

[1]:/en-us/citsmart-platform-9/processes/configuration/use/create-ic-relationship.html
