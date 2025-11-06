## Deploying python applications with Azure 

#### How to get free credits in Azure:
1. Create a free account in Azure at `https://azure.microsoft.com/en-in/free/students` using your student email id.
2. After creating the account, you will get $100 worth of credits.

#### Steps to deploy a python application in Azure VM:

1. Login to your Azure portal.
2. Click on `Create a resource` and select `Virtual Machine`.
3. Select appropriate options and create a VM.
4. After the VM is created, go to `Virtual Machines` and select your created VM.
5. SSH via your prefered terminal using the command:
   ```
   ssh <username>@<public-ip-address>
   ```
6. Update the package lists:
   ```
   sudo apt update
   ```
7. Install Python and Pip:
   ```
    sudo add-apt-repository ppa:deadsnakes/ppa -y
    sudo apt install python3.11 python3.11-venv python3.11-distutils -y
    curl -sS https://bootstrap.pypa.io/get-pip.py -o get-pip.py
    python3.11 get-pip.py
    ```
   #### OR
8. Install Anaconda:
   ```
   wget https://repo.anaconda.com/archive/Anaconda3-2024.06-1-Linux-x86_64.sh
   bash Anaconda3-2024.06-1-Linux-x86_64.sh
   source ~/.bashrc
   # reopen terminal
   ```

#### Lets deploy a sample python application:
1. Clone the repository containing your python application:
   ```
   git clone https://github.com/Rakesh-46-VR/azure-deployment-demo.git
   cd azure-deployment-demo
   ```
2. Create a virtual environment and activate it with Python 3.11:
   ```
   python3.11 -m venv myenv
   source myenv/bin/activate
   ```
   #### OR
3. Create a virtual environment and activate it with anaconda:
    ```
   conda create -n myenv python=3.11 -y
   conda activate myenv
   ```
4. Basic check to verify environment:
    ```
   which python
   which pip
   python --version
   pip --version
   ```
5. Install required packages using pip:
    ```
   pip install -r requirements.txt
   ```
6. Run your python application:
    ```
   gunicorn --bind 0.0.0.0:8000 app:app
   ```

#### Note:
- Make sure to open necessary ports in the Azure portal for your application to be accessible externally.
- You can monitor your VM usage and credits in the Azure portal to avoid exceeding your free credits.
- Remember to stop or delete your VM when not in use to save credits.

#### Conclusion:
By following these steps, you can successfully deploy a Python application on an Azure Virtual Machine. Enjoy the benefits of cloud computing with your free Azure credits!