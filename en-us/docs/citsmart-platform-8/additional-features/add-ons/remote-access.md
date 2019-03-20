Title: Implement Remote Access

# Implement Remote Access

The remote access functionality allows computers to be accessed remotely from your CITSmart instance.In this sense, we use the Virtual Network Computing (VNC) protocol resources through the Apache Guacamole - web-based remote access gateway - to make this operation feasible. In addition to being able to remotely access a configuration item, all sessions are saved and made available to the CI information. This ensures better control over the actions taken by providing a reliable and auditable environment.

This functionality is an add-on to the Configuration Management and depends on the inventory process to make viable remote access to a CI.


## Before getting started

The following questions precede the effective use of this functionality:

* [x] Having the Configuration Management implemented;
* [x] Having the inventory process defined and functional;
* [x] Having data 

## Procedure

1. Download the GUACD container;
2. Configure GUACD properties on the application server;

    ```java
    CITSMART_PROTOCOL=http
    CITSMART_URL=your-instance.citsmartcloud.com
    CITSMARTGUACD_ID=guacd_id
    CITSMART_LOGIN=admin
    CITSMART_PASSWORD=********
    ```
	
3. Set the directory for recording videos (eg. /mp4);
    
    !!! success "Video recording"
        After the remote access session ends, the generated video enters a queue to be available on the platform. The compilation time will depend on the session time, in addition, the beginning of the compilation is linked to the cron routine defined in the remote access connection.
    
## What to do next

With the GuaCD service active and communicable, the next step is to create a remote access connection in your instance and test the resource.

## Related

[Create connection to remote access server][1]

[1]:/en-us/citsmart-platform-8/processes/configuration/configuration/configure-remote-access.html
