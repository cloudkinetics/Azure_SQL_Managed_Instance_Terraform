## Azure SQL Managed Instance

az account clear  

az login  

az account set --subscription="sid"

It is recommended to create a separate service principal for deploying resources on azure.

https://learn.microsoft.com/en-us/azure/developer/terraform/get-started-cloud-shell-bash?tabs=bash

Since SQL Managed instance takes a long time to create we can use the timeout feature of terraform to create the instance. Terraform will usually timeout after 15-20 minutes so it is important to update the values of timeout within the resource block.

https://developer.hashicorp.com/terraform/language/resources/syntax#operation-timeouts

resource "<resource_name>" "<resource_name>" {
  ...
  timeouts {
    create = "1h30m"
    update = "2h"
    delete = "20m"
  }
}



terraform init
terraform plan
terraform apply 
