# managed-services-deploy

This repository hosts playbooks to install and uninstall OpenShift Dedicated clusters using OCM.


# OpenShift Dedicated install on AWS
Refer [docs](docs/openshift_on_aws.md)


## Quickstart Usage Example

```
- Clone the repo
- Create an inventory file with the intended orchestration host
- Configure the install variables
- Run the install playbook for the desired environment
- Run the uninstall playbook for the desired environment

$ git clone https://github.com/chaitanyaenr/managed-services-deploy.git
$ cd managed-services-deploy
$ cp OCP-4.X/inventory.example inventory
$ # Edit inventory and add your expected orchestration host
$ # Edit deployment variables (Ex vi vars/install-common-vars.yml and vi vars/install-on-aws.yml) or define env variables
$ ansible-playbook -v -i inventory install.yml -e platform=aws
$ ansible-playbook -v -i inventory uninstall.yml
```
