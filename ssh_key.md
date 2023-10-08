# Cnnect your EC2 instance to your GitHub account
you can use SSH keys for authentication. Here's a step-by-step guide on how to do this:

## **Generate an SSH Key Pair:**

   If you don't already have an SSH key pair, you can generate one on your local machine using the following command:

   ```shell
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

   output:
   Generating public/private rsa key pair.
   Enter file in which to save the key (/home/ubuntu/.ssh/id_rsa): 
   Enter passphrase (empty for no passphrase): 
   Enter same passphrase again: 
   Your identification has been saved in /home/ubuntu/.ssh/id_rsa
   Your public key has been saved in /home/ubuntu/.ssh/id_rsa.pub
   The key fingerprint is:
   dhfsjfhghyjghjvjgnbvnhvjjgyj
   xyz@gmail.com
   The key's randomart image is:
   +---[        ]----+
   |                 |
   |                 |
   |                 |
   |                 |
   |                 |
   |                 |
   |                 |
   |                 |
   |                 |
   +----[      ]-----+


   ```
   You can press "Enter" to accept for default

   Replace `"your_email@example.com"` with the email associated with your GitHub account. This command will create an SSH key pair (public and private keys) in your `~/.ssh/` directory.

   Now, your EC2 instance's SSH key is associated with your GitHub account, allowing you to interact with your GitHub repositories from your EC2 instance using SSH authentication.



## **Acces your key**: 
The output you provided indicates that you have successfully generated an SSH key pair. The private key is saved in `/home/ubuntu/.ssh/id_rsa`, and the public key is saved in `/home/ubuntu/.ssh/id_rsa.pub`.

To use this key for GitHub, you should copy the contents of the public key (`id_rsa.pub`) and add it to your GitHub account as an SSH key. Here's how you can do it:
    bash   

Open the public key file for viewing. You can use the `cat` command for this:
  

```bash
ubuntu@ip-0.0.0.0:~$ cat /home/ubuntu/.ssh/id_rsa.pub
```

        
This will display the contents of the public key in your terminal. Copy the entire content of the public key, including the "ssh-rsa" prefix.




## **Add the Public Key to Your GitHub Account:**

   - Log in to your GitHub account.
   - Click on your profile picture in the top-right corner and select "Settings."
   - In the left sidebar, click on "SSH and GPG keys."
   - Click the "New SSH key" button.
   - Give your SSH key a title (e.g., "EC2 Instance") and paste the contents of your **public** key (usually located in `~/.ssh/id_rsa.pub`) into the "Key" field.
   - Click "Add SSH key."


## Verify that your GitHub account is connected to your SSH key:
you can perform the following steps:


1. **Start the SSH Agent:**

   Run the following command to start the SSH agent:

   ```bash
   eval $(ssh-agent)
   ```

   This command starts the SSH agent and sets up the necessary environment variables.

2. **Add Your SSH Key:**

   Once the SSH agent is running, you can add your SSH key to it using the `ssh-add` command. Assuming your SSH key is located in the default `~/.ssh/` directory and named `id_rsa`, you can add it like this:

   ```bash
   ssh-add ~/.ssh/id_rsa
   ```

   Replace `~/.ssh/id_rsa` with the correct path to your private key if it's located elsewhere.


3. **Check Your SSH Key Configuration:**

   After adding the key, you can use `ssh-add -l` to verify that it has been loaded into the SSH agent:

   On your EC2 instance, you can list the SSH keys that are currently configured by running the following command:

   ```bash
   ssh-add -l
   ```

   If your key is listed, it means it has been loaded into the SSH agent.

5. **Test SSH Authentication:**

   You can test SSH authentication to GitHub using the following command:

   ```bash
   ssh -T git@github.com
   ```

   If your SSH key is properly configured and associated with your GitHub account, you should receive a message like:

   ```
   Hi username! You've successfully authenticated...
   ```


6. **Clone or Pull from Your GitHub Repository:**

   Now that your EC2 instance is connected to your GitHub account, you can clone or pull from your GitHub repository as needed:

   - Clone a repository:

     ```shell
     git clone git@github.com:yourusername/yourrepository.git
     ```

   - Pull changes from a repository:

     ```shell
     cd yourrepository
     git pull origin master
     ```

   Ensure that you replace `yourusername` and `yourrepository` with your GitHub username and repository name.

With these steps, your EC2 instance is now connected to your GitHub account via SSH keys, allowing you to interact with your GitHub repositories on the instance.