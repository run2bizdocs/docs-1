title: System displays a message of invalid date when audit a ticket
Description: Displays message of invalid date
#System displays a message of invalid date when audit a ticket

In the Ticket Management interface, specifically in the item "Auditing", when
trying to configure the audit of an open ticket (define the start and end dates
in the filter), the following error may occur: the system will display the
"Invalid Date" message. This is because the functionality requires that the
language set in the system and browser used be the same.

If this requirement is not observed and this difference occurs in the languages,
when auditing the tickets, the system will display a message and will not be
able to receive the report you want. It is therefore necessary to match the
system and browser languages.
