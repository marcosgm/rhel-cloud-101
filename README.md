# Overview

[![Git](https://app.soluble.cloud/api/v1/public/badges/6ac7fce7-4acb-43a0-ab26-84adecb0afd4.svg?orgId=568518005652)](https://app.soluble.cloud/repos/details/github.com/marcosgm/rhel-cloud-101?orgId=568518005652)  

GOAL: help with the first steps for a Red Hat customer on public clouds 

This repository contains everythign you need to start (from scratch) managing RHEL on the cloud.

Initial focus is AWS and Azure. Using Ansible playbooks, you'll learn how to manage RHEL and its lifecycle on two clouds.

# Prerequisites
## How to get access to Red Hat software
visit developer.redhat.com and register, for free.

## How to execute Ansible in my computer
In Linux, simply "yum install ansible" or "apt-get install ansible"
You also need python's pip: "yum install python-pip" or "apt-get install python-pip"

In MacOS, follow 
- https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#latest-releases-via-pip

- https://docs.ansible.com/ansible/2.6/scenario_guides/guide_aws.html

## How to create a cloud account at AWS and Azure


# First Playbook
First launch

`ansible-galaxy install -r requirements.yml `

then

`ansible-playbook bootstrap/setup-workstation.yml`

It will install the aws and azure CLI, ask you to initialize your account using root credentials (via web)

then

`ansible-playbook bootstrap/setup-ansible-credentials.yml`
Using the CLI, it will add an Ansible account and it will configure non-root ansible credentials in your in your local folder

# AWS Basic Setup
`ansible-playbook bootstrap/setup-aws.yml -e username=$(whoami)` 

It will connect to AWS using your root account, create a IAM admin account with the same name as your shell account, configure a basic VPC with a default security group