# *CAUTION: Still a work in progress!*

# How to use:
### Step 1:
Enter the required variables in the vars/vars.yaml file

### Step 2:
This step will make sure the hosts packages will be upgraded
run command: `sudo ansible-playbook update-host.yaml -k --ask-become-pass --become-method=su`
### Step 3:
This step will create a veeam service account[^1] and setup the repository XFS filesystem

run command: `sudo ansible-playbook setup-repository.yaml -k --ask-become-pass --become-method=su`
### Step 4:
This step will setup firewall rules and enable OTP[^2] for the user
run command: `sudo ansible-playbook harden-host.yaml -k --ask-become-pass --become-method=su`

### Step 5:
Configure OTP within the Authenticator application of your choice, use the information from the `credentials/OTP` file


[^1]: The service account credentials will be stored into the `credentials/veeamuserpw` file
[^2]: The OTP information will be stored into the `credentials/OTP` file