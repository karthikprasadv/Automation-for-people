----------------------------------------------------------------------
Scenario: Launching Application on AWS Infra Resources using Terraform
----------------------------------------------------------------------
========================================
Step-1: Launch the Terraform on Windows
========================================
1.Download terraform from https://www.terraform.io/downloads.html
2.Extract the downloaded binary file
3.Create a new folder and name it as "terraform" under C-Drive,i.e "C:\terraform"
4.Copy the extracted binary "terraform" file to "C:\terraform"
5.Set Env Variable by setting PATH="C:\terraform\"
6.Verify terraform version by command
    $terraform --version

7.Download AWS CLI from https://aws.amazon.com/cli/ based on OS
8.Install AWS CLI
9.Verify AWS CLI by commands
    $aws --verify

============================================================
Step-2:Terraform IAM User Creation
============================================================
11. Create an IAM user-terraform user from AWS Console
      Name: 	terraform-admin
      Role:	  Administrator

12.Download .csv from newly created IAM user terraform-admin


================================================================
Step-3:Provising a Terraform Use Access Key ID and Secret Key ID
================================================================
13.Move to Windows machine and configure access_key and secret_key
   for aws by commands
    $ aws configure        
    #Input your access_key && secret_key,


=========================================================
Step-4: Setup for GITHUB
==========================================================
14.Using GITHUB Create a repo to have terraform scripts ,i.e "terraform-scripts"
15.Using GITHUB Create another repo to have application ,i.e "ion"
16.Clone both "terraform-scripts" && "ion"

=========================================================
Step-5:Ruuning Terraform Scripts init/Plan/apply
=========================================================

17. Move to cloned version of "terraform-scripts" and run the following commands
    $ terraform init

18.The terraform plan will let us know what changes, additions and deletions
   will be done to the infrastructure before actually applying it.
   The resources with '+' sign are going to be created,
   resources with '-' sign are going to be deleted and resources with '~' sign are going to be modified.

19.$ terraform plan

==========================
Step-6:Terraform Apply
==========================
20.To create the instance, execute terraform apply
    $ terraform apply

===========================
Step-6:Terraform Destroy the Infra
===========================
21.Move to AWS Console and get the public IP of instance
22.Open Browser and paste <public-ip>/ion

===========================
Step-7:Terraform Destroy the Infra
===========================
23.To create the instance, execute terraform apply
    $ terraform destroy
