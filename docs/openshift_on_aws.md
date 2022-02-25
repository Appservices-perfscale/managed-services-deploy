# OpenShift Dedicated on AWS
The variable file can be found at [vars/install-on-aws.yml](../vars/install-on-aws.yml) and [vars/install-common-vars.yml](../vars/install-common-vars.yml). It will configure the deployment playbook at install.yml to perform a cluster installation on AWS.


## Usage
```
$ cp inventory.example inventory
$ # Edit inventory and add your expected orchestration host
$ # Edit deployment variables or define env variables
$ ansible-playbook -vv -i inventory install.yml -e platform=aws
$ ansible-playbook -vv -i inventory uninstall.yml
```

## Environment variables
Vars in [vars/install-on-aws.yml](../vars/install-on-aws.yml) and [vars/install-common-vars.yml](../vars/install-common-vars.yml) can be defined as environment variables on the host that you will be running the playbooks. [vars/install-common-vars.yml](../vars/install-common-vars.yml) are generic to any cloud platform and [vars/install-on-aws.yml](../vars/install-on-aws.yml) vars are specific to the cloud provider to be able to talk to the respective API.


### AWS_ACCESS_KEY_ID
Default: No default.
The AWS access key.

### AWS_SECRET_ACCESS_KEY
Default: No default.
The AWS secret access key.

### AWS_REGION
Default: us-west-2
The AWS region to install on to.

### AWS_ACCOUNT_ID
Default: No default.
Account ID

### OPENSHIFT_CLEANUP
Default: true
Cleans up the duplicate cluster matching the CLUSTER_NAME if exists

### OPENSHIFT_INSTALL
Default: true
Installs cluster

### OCM_URL
Default: https://api.stage.openshift.com/
OCM URL to connect to

### OCM_API_TOKEN
Default: No default.
API token to login into your console.redhat.com or OCM account

### CCS_ENABLED
Default: true

### CLUSTER_NAME
Default: No default
Name of the cluster

### MANAGED
Default: true

### MULTI_AZ
Default: false
Sets up workers in multiple availability zones when enabled

### COMPUTE_COUNT
Default: 4
Number of computer/worker nodes in the cluster

### COMPUTE_MACHINE_TYPE
Default: m5.2xlarge
Machine type or flavor for the worker/compute nodes in AWS

### OPENSHIFT_VERSION
Default: openshift-v4.9.17
OpenShift version to install

### KUBECONFIG
Default: /root/.kube/config
Location to copy the kubeconfig of the cluster
