# MIGRATION TO TERRAFORM & DRIFT DETECTION

https://youtu.be/-4IMy5ihiiU

there is already a resource in aws 

first write a main.tf file

provider "aws" {
  region = "us-east-1"
  }

  import {
  id = "instance_ID"

  to = "aws.instance.example"
  }

  $terraform plan -generate-config-out=generated_resources.tf

  generated_resources.tf will created
  copy the resource block from generated_resources.tf and paste to main.tf to create terraform.statefile

  to import terraform state file. 
  
  $terraform import aws_instance.example instance ID

  $terraform plan

  result is
  No changes. your infrastrucre matches the configureration.
  

