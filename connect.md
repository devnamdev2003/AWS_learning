# Connect an Amazon Elastic Compute Cloud (EC2) instance from your local PC

you typically use SSH (Secure Shell) for Linux instances or RDP (Remote Desktop Protocol) for Windows instances. Here are the general steps to connect an EC2 instance to your local PC:

### Connecting to a Linux EC2 Instance (SSH):

1. **Create an EC2 Instance:**
   If you haven't already, launch a Linux EC2 instance. Note down the public IP address or DNS name of the instance.

2. **Install an SSH Client:**
   On your local PC, ensure you have an SSH client installed. If you're using Linux or macOS, you can use the built-in terminal and SSH client. On Windows, you might need to install an SSH client like PuTTY (https://www.putty.org/).

3. **Access the EC2 Instance:**
   Open a terminal (command prompt on Windows) and use the following command to connect to your EC2 instance using SSH:

   ```bash
   ssh -i "path/to/your/key.pem" ec2-user@ec2-instance-public-ip
   ```

   - Replace `path/to/your/key.pem` with the path to your private key file.
   - Replace `ec2-user` with the appropriate username based on your EC2 instance's operating system (e.g., `ubuntu` for Ubuntu, `ec2-user` for Amazon Linux, or `centos` for CentOS).
   - Replace `ec2-instance-public-ip` with the public IP address or DNS name of your EC2 instance.


