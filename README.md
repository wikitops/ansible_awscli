# Ansible : Playbook Awscli
The aim of this project is to deploy the AWS command line on Vagrant.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

What things you need to run this Ansible playbook :

* [Vagrant](https://www.vagrantup.com/docs/installation/) must be installed on your computer
* Update the Vagrant file based on your computer (CPU, memory), if needed
* You must have download the ubuntu Xenial64 vagrant box :

```
vagrant box add https://app.vagrantup.com/ubuntu/boxes/xenial64
```
* Create some IAM account on AWS and configure the default awscli variable
* Ensure the Unix user exist on remote instance, the role does not manage Unix users directly

### Usage

A good point with Vagrant is that you can create, update and destroy all architecture easily with some commands.

Be aware that you need to be in the Vagrant directory to be able to run the commands.

#### Build Environment

Vagrant needs to init the project to run and build it :

```
vagrant up
```

After build, you can check which virtual machine Vagrant has created :

```
vagrant status
```

If all run like it is expected, you should see something like this :

```
$ vagrant status

Current machine states:

awscli01                   running (virtualbox)
```

#### Deployment

To deploy the Awscli, you just have to run the Ansible playbook awscli.yml with this command :

```
ansible-playbook awscli.yml
```

If everything run has expected, you should manage your AWS account via the command line.

For example, to list the document in the s3.wikitops.io bucket :

```
$ aws s3 ls s3://wikitops.io
```

#### Destroy

To destroy on what Vagrant has created, just run this command :

```
vagrant destroy
```

## Author

Member of Wikitops : https://www.wikitops.io/
