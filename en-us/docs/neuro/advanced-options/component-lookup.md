Title: Lookup component
Description: Neuro's lookup component allows the creation of mater-datails interfaces in item listings.

# Lookup Component

The Lookup component is a feature of Neuro that allows the creation of quick lists of options, being possible to have a master-detail interface, that is, displaying a master list and the details of the selected item, for example, create fields for the user to select a country, then select a State, and then a city.

To use this feature in forms, you must:

* [x] Creating Lookup

* [x] Configuring elements of Lookup in the formu

## What to do before

Before creating lookup components you must create an application and optionally a Neuro database connection.

## Creating Lookup components

1. Access the functionality through the menu Neuro > Management > Lookup Component;
2. Register the lookup component(s);
3. Enter the information:

    |Field|Description|Example|
    |-----|---------|-------|
    |Name|Identifier which doesn't allow space|country|
    |Description|Information of lookup|Country|
    |Application|Neuro Application|My App|
    |Base Connection|Database connection (same as used in the business objects)|Neuro DB Connection|
    |Column or expression for field key|ID to return key|idcountry|
    |Column or expression for description|Return of field description|namecountry|
    |FROM and WHERE|Query to FROM and Query|`FROM country`|

4. Click on "Test the component" to see the result;
5. Click on "Save" to register the data.


## Screen design (Form)

1. Select a form;
2. Click on "Screen design";
3. Drag the element "Lookup" to the design area;
4. Change the width of the field as needed;
5. Enter the name of the Label;
6. In the item "Lookup", select the desired record;
7. Enter the "Model" property (form attribute that will receive the value of the lookup key field);
8. In the "Additional WHERE Clause" field, enter the SQL syntax when you want to filter the list result.

## Example of usage

Let's exemplify the creation of a master-detail interface to allow the user to select a country, State, and city from the selected State.

- **Lookup 1: Country**

Name: country

Description: Country

Application: My App

Base Connection: Neuro DB Connection 

Column or expression for field key: idcountry

Column or expression for description: namecountry

FROM and WHERE:

```mysql
FROM country
```

- **Lookup 2: State**

Name: State

Description: State

Application: My App

Base Connection: Neuro DB Connection 

Column or expression for field key: idstate

Column or expression for description: `namestate||'('||acronymstate||')'`

``` mysql
FROM state
```

- **Lookup 3: City**

Name: state

Description: State

Application: My App

Base Connection: Neuro DB Connection

Column or expression for field key: idcity

Column or expression for description: namecity

``` mysql
FROM cities
```

- **In the form**

To use the master details feature, that is, display data based on a previously selected item, you can use the same business object SQL syntax (as shown below);

Enter the SQL syntax in the "Additional WHERE Clause" field of the Lookup element;

``` mysql
iduf = ${nameModel.iduf:INTEGER}
```


Or insert into the Lookup component itself (FROM and WHERE field);

``` mysql
FROM cities
WHERE iduf = ${nameModel.iduf:INTEGER}
```
