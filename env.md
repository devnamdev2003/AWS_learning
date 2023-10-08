# Creating a virtual environment (virtualenv) in AWS 

1. **Update the System:** 
   ```bash
   sudo apt-get update
   ```

2. **Install Python (if not already installed):** :
   ```bash
   sudo apt-get install python3 -y 
   ```
3. **Install virtualenv:** Install it using pip:
   ```bash
   sudo python3 -m pip install virtualenv
   ```
4. **Create a Virtual Environment:** 
   ```bash
   cd /path/to/your/project
   virtualenv venv
   ```
5. **Activate the Virtual Environment:** 
   ```bash
   source venv/bin/activate
   ```
6. **Deactivate the Virtual Environment:** 

   ```bash
   deactivate
   ```
