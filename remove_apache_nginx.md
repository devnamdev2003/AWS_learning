# Remove Apache completely from your Ubuntu-based system
you can follow these steps:

1. **Stop the Apache Service**: 

   ```bash
   sudo systemctl stop apache2
   ```

2. **Disable the Apache Service**:
   ```bash
   sudo systemctl disable apache2
   ```

3. **Uninstall Apache Packages**: U
   ```bash
   sudo apt remove apache2 apache2-utils apache2-bin
   ```
   This command will remove Apache along with its configuration files.

4. **Purge Configuration Files**: To remove any configuration files that might be left behind, use the `purge` option:

   ```bash
   sudo apt purge apache2 apache2-utils apache2-bin
   ```

5. **Clean Up**: Finally, clean up any residual files or packages:

   ```bash
   sudo apt autoremove
   sudo apt autoclean
   ```
6. **Verify Removal**: 
   ```bash
   dpkg -l | grep apache2
   ```

7. if you see this
    ```bash
    ubuntu@ip-172-31-34-8:~$ dpkg -l | grep apache2
    ii  apache2-data                       2.4.52-1ubuntu4.6                       all          Apache HTTP Server (common files)

    ```
    
    run this:
    ```bash
    sudo apt purge apache2-data
    ```

8. **Using `apache2ctl` (Command):**

   You can use the `apache2ctl` command to check the status of Apache. Open your terminal and run:

   ```bash
   apache2ctl -v
   ```
9. **Checking Apache Files:**
   To check if the Apache service is running:
   ```bash
   sudo systemctl status apache2
   ```





# Remove Nginx from your Ubuntu-based system
you can follow these steps:

1. **Stop the Nginx Service**: 
   ```bash
   sudo systemctl stop nginx
   ```

2. **Disable the Nginx Service**:
   ```bash
   sudo systemctl disable nginx
   ```

3. **Uninstall Nginx Packages**: 
   ```bash
   sudo apt remove nginx nginx-common nginx-core
   ```

   This command will remove Nginx along with its configuration files.

4. **Purge Configuration Files**: 
   ```bash
   sudo apt purge nginx nginx-common nginx-core
   ```

5. **Clean Up**:
   ```bash
   sudo apt autoremove
   sudo apt autoclean
   ```

6. **Verify Removal**: 
   ```bash
   dpkg -l | grep nginx
   ```

7. if you see this
    ```bash
    ubuntu@ip-172-31-34-8:~$ dpkg -l | grep nginx
    rc  libnginx-mod-http-geoip2           1.18.0-6ubuntu14.4                      aNginx
    rc  libnginx-mod-http-image-filter     1.18.0-6ubuntu14.4                      ae for Nginx
    rc  libnginx-mod-http-xslt-filter      1.18.0-6ubuntu14.4                      aule for Nginx
    rc  libnginx-mod-mail                  1.18.0-6ubuntu14.4                      a
    rc  libnginx-mod-stream                1.18.0-6ubuntu14.4                      a
    rc  libnginx-mod-stream-geoip2         1.18.0-6ubuntu14.4                      ar Nginx
    rc  nginx-common                       1.18.0-6ubuntu14.4                      ale web/proxy server     - common files
    ```
    
    run this
    ```bash
    sudo apt purge libnginx-mod-http-geoip2 libnginx-mod-http-image-filter libnginx-mod-http-xslt-filter libnginx-mod-mail libnginx-mod-stream libnginx-mod-stream-geoip2 nginx-common

    ```