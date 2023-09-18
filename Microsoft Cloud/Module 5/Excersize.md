# Excersize
- This Module has three excersizes which are connected to each other. That is why I have put them in one. 
## 1. Create an Azure virtual machine

### Overview
In this exercise, you create an Azure virtual machine (VM) and install Nginx, a popular web server. You could use the Azure portal, the Azure CLI, Azure PowerShell, or an Azure Resource Manager (ARM) template.

### Tasks Performed
1. Create a Linux virtual machine and install Nginx
2. Work with blob storage
3. Change the access level of your blob
4. Clean up

### New terms 

1. To create a Linux VM instance:
```cmd 
az vm create \
  --resource-group [sandbox resource group name] \
  --name my-vm \
  --public-ip-sku Standard \
  --image Ubuntu2204 \
  --admin-username azureuser \
  --generate-ssh-keys
```

2. To configure NGINX on the VM
```cmd 
az vm extension set \
  --resource-group [sandbox resource group name] \
  --vm-name my-vm \
  --name customScript \
  --publisher Microsoft.Azure.Extensions \
  --version 2.1 \
  --settings '{"fileUris":["https://raw.githubusercontent.com/MicrosoftDocs/mslearn-welcome-to-azure/master/configure-nginx.sh"]}' \
  --protected-settings '{"commandToExecute": "./configure-nginx.sh"}'
```

## 2. Configure network access

### Overview 
In this exercise, you'll configure the access to the virtual machine (VM) you created earlier in this module.

### Tasks Performed
1. Access your web server
2. List the current network security group rules
3. Create the network security rule
4. Access your web server again
5. Clean up

### New Terms

1.  To check if a previous instance is still running
```cmd
az vm list
```

If you receive an empty response [], It isn't running.