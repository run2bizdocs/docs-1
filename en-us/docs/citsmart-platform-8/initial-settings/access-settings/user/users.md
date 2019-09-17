title: Register user
Description: This feature provides a variety of actions, such as including, changing, and deleting an user. 
# Register user

In order for the employee to be able to access the system, it's necessary to create an user.
The system will send an email with the login and password of the new user that was created 
by Citsmart.

This feature provides a variety of actions, such as including, changing, and deleting an user.

!!! warning "ATTENTION"

    The sending of login and password, when registering the new user, doesn't include users 
    imported via AD or LDAP.

Before getting started
--------------------------

To register an user, it's necessary to previously register the profile access
and employee.

Configure the parameters:

|#|Description|
|--------|---------|
|33|System access URL.|
|455|Email template ID that will be sent to the user with the password when the user is created or changed|

The admin can create a new email template by editing the existing email template:

    ID: 205
    Email template ID: ACCESSCREDENCIAL
    
Just include the keys:

    User: ${LOGIN}
    Password: ${NOVASENHA}

Procedure
-------------

1.  Access the functionality through the main menu General Registration \>
    Personnel Registration \> User;

2.  Complete all mandatory field;

3.  Click on "Save".

4.  The system checks if there is an email template for the  new employee that has the password 
    key to send via email;
    
5.  The system administrator registers or changes an employee's login and password on the user 
    screen;
    
6.  The system checks if:

    -    the system uses the password policy;
    -    the user is LDAP or not;
    
7.  The system allows the imput of a new password;

8.  When saving, the system sends by email the new data to the employee.


Related
-----------

[Register employee](/en-us/citsmart-platform-8/initial-settings/access-settings/user/register-employee.html)

[Create profile access](/en-us/citsmart-platform-8/initial-settings/access-settings/profile/create-profile-access.html)

!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/10/2019 – Larissa Lourenço

