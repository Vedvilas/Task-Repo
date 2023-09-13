## Terraweek Day 3: Defining and managing AWS Resources Using with Terraform.

Welcome to Day 3 of **Terraweek**..! Today we will dive into the word of terraform and lets understand how to define AWS resources. And also explore the resource types and theire configurations.
And additionally explore the **Lifecycle** management. By the end of this guide, these all crucial concetps in terraform. Lets get started.

## Table of Content 
- Defining & managing AWS resources using Terraform
- Check State Files Before Running and Validate .tf File
- Resource Dependencies and Provisioners
- Lifecycle Managment
- Conclusion
## Defining & managing AWS resources using Terraform

Create a Terraform configuration file to define a resource of AWS EC2 instance
1. **Login into Aws management console**
2. **Spin up a **Linux** Ec2 instance on AWS**
3. **Install Terraform**:Visit the official Terraform website to download the latest version of Terraform for your operating system. Terraform supports various platforms like Windows, macOS, and Linux. Download the appropriate binary for your OS.
[Terraform Official Website](https://www.terraform.io/downloads.html)

![Screenshot from 2023-09-13 14-50-27](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/ed7f42a4-e838-4c9a-ba9f-c1fdd8998a20)
 Once installation done, Verify the installation using **terraform --verion**\
 
 ![Screenshot from 2023-09-13 15-17-59](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/1aa56381-86e8-4bde-9230-6c07ebe55245)
 
## Set up the AWS Creadials

- Sign in to AWS Management Console.
  
- Create a IAM User with Required Permissions
  
![Screenshot from 2023-09-13 15-15-24](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/0e1ce5af-3f15-4999-aefe-1e5a34880610)

- Create the Access key and Screate key to you User
  
![Screenshot from 2023-09-13 15-22-53](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/0011fa83-5f42-4be0-8aa9-bfbe85a9bddf)

## Create Terraform Configuration file.
- Create a new directory for your Configuratuion.
- open the terminal and navigate to your project directory.
- Create a new file for your confuguration with .tf extention (provider.tf, Intstance.tf)
- In your configuration file specify the Provider details and Your Resource details (Which Resource you want to craete).

  ![Screenshot from 2023-09-13 15-42-30](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/0c7508bb-6ee9-48c8-8812-e97f0c965379)


  ![Screenshot from 2023-09-13 15-34-44](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/055e6802-7a98-47f0-a061-2cb3c9c77b87)

  ## Check State Files Before Running and Validate .tf File.
  Check the state file before running terraform plan and terraform apply command and use validate command to validate your .tf file for finding errors.
- Initilize the your directory using the **terraform **init command****
  ![Screenshot from 2023-09-13 15-44-54](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/6874e466-fdfb-4ca0-aa8e-934e2e5c4b9c)

- Check the existing state file using terraform **state file** command.
  ![Screenshot from 2023-09-13 15-47-46](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/058d7630-d11e-496f-9c8e-51b6ea3b7c65)
- Now validate the terraform configuration file for finding systax errors using **terrform validate**
  ![Screenshot from 2023-09-13 15-50-42](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/11856b6d-8b54-459a-afab-3a611b30a9bd)
- Once the validation complete for configuraion file, now you can exicute **terraform plan** and **terraform apply** command.
  ![Screenshot from 2023-09-13 15-54-26](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/ea67f1c5-3c1f-47cb-a4ad-174b42fdbc12)
  ![Screenshot from 2023-09-13 16-00-32](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/960d16ac-b61f-40f1-979c-abf095ef8d4a)
  ![Screenshot from 2023-09-13 16-01-55](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/5f5da0ca-3048-45e5-ac5e-f151928306b7)
  
  **Bhoom..! Bhoom...!! Successfullly Instance Has Been Created & Its Running Now...**
- Now Destory the Resource which we defined in the configuration file using **terrafom destory** command
  
  ![Screenshot from 2023-09-13 16-09-03](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/dda2ef27-54dc-4849-aefe-212b53bfc1b6)
  ![Screenshot from 2023-09-13 16-09-52](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/3ba61593-b8ac-4944-8d90-d2064121b5e3)
  ![Screenshot from 2023-09-13 16-10-44](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/8eb9907e-326b-44b6-ae13-d1ec7a803851)

## Resource Dependencies and Provisioners.
Resource dependencies and provisioners are important concepts in Terraform for managing the order of resource creation and performing actions on those resources after they are created. These concepts are essential for ensuring that your infrastructure is provisioned and configured correctly

## Resource Dependencies:
In Terraform, resources are defined in your configuration files, and they often depend on each other. For example, a virtual machine resource may depend on a virtual network resource. Terraform uses resource dependencies to determine the order in which resources should be created, updated, or destroyed.
  
![Screenshot from 2023-09-13 16-18-22](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/bd7f5673-7334-40c8-960b-fc164ac56fcc)

In above image, the **aws_subnet** resource depends on the **aws_vpc** resource.

## Provisioners:
Provisioners in Terraform allow you to run scripts or perform actions on resources after they have been created or destroyed. Provisioners are useful for tasks like initializing a newly created virtual machine, configuring software, or setting up network resources.
![Screenshot from 2023-09-13 16-27-35](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/da908d3c-9e0c-409f-bdeb-95c181713c5e)

## Lifecycle Managment
Lifecycle management in Terraform refers to the control and management of the various stages of a resource's lifecycle, including creation, updates, and destruction. Terraform provides several mechanisms to define how resources should be managed throughout their lifecycle.
#### create before destroy:
This hook ensures that a new resource is created before the old one is destroyed during an update. This can be useful for zero-downtime deployments or to prevent resource destruction until a replacement is available.

#### prevent destroy:
This hook can be used to prevent the destruction of specific resources, making them "immutable" once created. It can be useful for critical infrastructure components.

Here's an example of how you can use the lifecycle block to configure a prevent_destroy.
![Screenshot from 2023-09-13 16-35-23](https://github.com/Vedvilas/TerraWeek-Repo/assets/113783616/f47bc10e-ee5f-4567-87b3-4fae1924e90f)

## Conclusion:

In this blog, you've created a Terraform configuration file to define an AWS EC2 instance, checked state files, validated the configuration, added a provisioner to configure the resource after creation, and implemented lifecycle management configurations to control resource creation and updates. Terraform offers powerful capabilities for managing infrastructure as code, allowing you to define, provision, and manage your cloud resources efficiently.

HAPPY LEARNING..!








