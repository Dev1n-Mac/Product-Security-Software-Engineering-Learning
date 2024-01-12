**terraform init** : 

- This command initializes a working directory containing Terraform configuration files. It is the first command to run after writing a new Terraform configuration or cloning an existing one from version control. It installs any required providers and sets up the backend for state management

**terraform apply** :

- This command applies the changes required to reach the desired state of the configuration. It's the command that deploys or applies your configuration to a provider​

**terraform destroy**:

- This command destroys the Terraform-managed infrastructure, effectively removing all provisioned resources​

**terraform plan**:

- This command creates an execution plan, showing what actions will be taken to apply the configuration, without actually making any changes. It's a way to see what changes will be made before actually applying them​