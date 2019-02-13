Title: LDAP Configuration

# LDAP Configuration

LDAP (Lightweight Directory Access Protocol) is a standard protocol that allows managing directories, that is, accessing information banks about the users of a network through TCP/IP protocols.

This functionality allows to register multiple LDAP connections and configure each one of them.

## Before getting started

It's necessary to have registered the time for scheduling automatic synchronization.

## Procedure

1. Access the main menu Parametrization > LDAP Configuration;
2. Click on "New";

    !!! Abstract "RULE"

        All fields are equally relevant to enable the connection to the LDAP, while
        the test is not successful, the configuration procedure cannot be considered
        complete.


3. Complete the fields available;
    
    !!! Abstract "RULE"

       If there are no LDAP groups, complete field "DN Group" with an asterisk only.
       This will cause the system to verify the entire domain.


4. It's possible to link new groups by clicking on "Add" in the LDAP Groups area;

    !!! Abstract "RULE"

       Before asking to test, it MUST click on "Save" to register the
       configuration, otherwise the test will use the data prior to the changes
       made on the screen.
  
    !!! Abstract "RULE"

        When an authentication request is made on the system identification screen
        (login and password), a correct connection search cycle is executed based on
        this configuration, that is, there's an authentication attempt for each domain
        registered here (if there is more than one).

5. It's possible to link field maps by clicking on "Add" in the Field Mapping area;
6. Click on "Save".

    !!! Abstract "RULE"

       The system does not allow to delete a user that originates in LDAP.

	
## Related

[Configure parametrization - LDAP][1]

[1]:/en-us/citsmart-esp-8/platform-administration/parameters-list/configure-parametrization-ldap.html

!!! tip "About"

    <b>Product/Version:</b> CITSmart ESP | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/22/2019 - João Pelles  
	
