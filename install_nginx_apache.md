# Install Nginx on an AWS
you can follow these general steps:

1. **Update the Package Repository:**
:
     ```bash
     sudo apt update    
     ```

1. **Install Nginx:**
     ```bash
     sudo apt install nginx 
     ```
2. **Start Nginx:**
     ```bash
     sudo systemctl start nginx
     ```
3. **Enable Nginx to Start on Boot:**
     ```bash
     sudo systemctl enable nginx
     ```
4. **Test Nginx:**
    
    Open a web browser and enter your EC2 instance's public IP address or domain name. You should see the default Nginx welcome page if everything is configured correctly.

    ```bash
    sudo nginx -t
    ```

1.  **Reload Nginx Configuration (After Making Changes):**
      ```bash
      sudo systemctl reload nginx
      ```
2. **Stop the Nginx service**:

   ```bash
   sudo systemctl stop nginx
   ```

3. **Disable Nginx:**

    ```bash
    sudo systemctl disable nginx
    ```

<br>
<br>

# Install the Apache web server on an Ubuntu-based EC2 instance
you can use the `apt` package manager. Here's how to do it:

1. Install Apache by running the following command:

   ```bash
   sudo apt install apache2
   ```

   This command will install Apache and its dependencies.

2. After the installation is complete, start the Apache service:

   ```bash
   sudo systemctl start apache2
   ```

3. Enable Apache to start automatically at boot:

   ```bash
   sudo systemctl enable apache2
   ```

4. To check if Apache is running, you can use the following command:

   ```bash
   sudo systemctl status apache2
   ```

5. Run the following command to stop the Apache service:

   ```bash
   sudo systemctl stop apache2
   sudo systemctl disable apache2
   ```

Now, Apache will not start automatically when your EC2 instance boots up. You can start it manually using `sudo systemctl start apache2` when needed.