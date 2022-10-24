# Project-15-Modified-Terraform-cloud
Modified project 15 repo run from terraform cloud

In this project we will migrate our codes to Terraform Cloud and manage our AWS infrastructure from there.

I created a new repository in your GitHub and call it **"Project-15-modified-terraform-cloud"**, and pushed my Terraform codes developed in the previous projects to the repository.

Configured Terraform cloud workspace to connect to the above rew repo in Github. 

Now it is time to run our Terrafrom scripts, but we be using Packer to build our images, and Ansible to configure the infrastructure, so for that we are going to make few changes to our our existing respository from the previous project.

The folders that would be added are:

ami: for building packer images
ansible: for Ansible scripts to configure the infrastucture

Before you proceed ensure you have the following tools installed on your local machine;

1. packer
2. Ansible

In the **Project-15-Modified**, we had to use an ami image-id and manually configure our servers including bastion, nginx and the compute servers. But in this project we are going to use parker to build our image. Because the shell script parsed for configuring the servers which contains the end points of the resources created by terraform, it will be difficult for terraform to run those scripts while creating the resources. So we will find a way of parsing the endpoints so that the servers will be properly configured.

In summary, the ami folder will contain the .pkr.hcl files and the shell scripts for all the servers, which will be used to build the ami, then we will copy the ami-id and update our terraform .auto.tfvars file, run the terraform and then use the codes inside the ansible folder to configure the servers using ansible.


