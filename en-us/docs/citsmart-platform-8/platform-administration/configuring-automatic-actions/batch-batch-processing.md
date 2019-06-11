title: Batch Processing
Description: Intended to register the batch processing, that can be used in other system routines.
# Batch Processing

This functionality is intended to register the batch processing, that can be
used in other system routines.

Routines like:

   - Email verification
   
   - Server time verification
   
   - Automatic ticket distribution with workload balancing 

Procedure
-------------

1.  Access the functionality through the main menu System \> Batch Processing;

2.  Click on "New";

3.  Complete the fields available (description, type [Java class, RhinoScript,
    SQL]; status; cron expression that defines the routine execution time and
    the context of the routine to be executed in the system);
    
    Example of "Clase Java" content:
    ```html
    br.com.centralit.citcorpore.quartz.job.JobConfiguracaoAberturaAutomaticaViaEmail
    ```

4.  Click on "Save".

Batch Routines
------------------

-   Return server time (download script attached);

    -   Type: RhinoScript

-   Perform e-mail reading (download script attached).

    -   Type: Java class


Attachment
----------
[Download-Verify email routine][1]

[Download-Return server time routine][2]

!!! tip "About"

    <b>Product/Version:</b> CITSmart | 8.00 &nbsp;&nbsp;
    <b>Updated:</b>01/07/2019 – Anna Martins



[1]:/en-us/citsmart-platform-8/platform-administration/configuring-automatic-actions/images/routine_verify_email.docx
[2]:/en-us/citsmart-platform-8/platform-administration/configuring-automatic-actions/images/routine-return-server-time.docx
