# learn-openshift
"Learn OpenShift" is a step by step hands-ob guide which gives you some practical OpenShift-related examples

## Labs
The repository gives a number of folders which proides all files required for a Lab.
The following labs are included

Lab    | Description
------ | -----------
Lab 0  | Creating lab environment (please see below)
Lab 1  | Docker installation
Lab 2  | 1
Lab 3  | 
Lab 4  | Manaing images
Lab 5  | Managing containers
Lab 6  | Using environment variables
Lab 7  | Using persistent storage
Lab 8  | Starting multicontainer applications
Lab 9  | Starting private registry
Lab 10 | Creating new images by docker commit
Lab 11 | Creating a simple Dockerfile
Lab 12 | Importing and exporting images
Lab 13 | Advanced Dockerfile
Lab 14 | Containerizing Jboss EAP


## Creating lab environment
CentOS 7 minimal is required to deploy this lab environment.

### Virtual Machine
The repsitory includes a Vagrantfile which deploys a VM with the following configuration option:

Option   | Value
-------- | -----
RAM      | 6000M
vCPU     | 2
IP       | 172.24.0.11
Hostname | openshift.172.24.0.11.nip.io
Box      | centos/7

### Additional configuration

The VM is customized as follows:
- docker and git packages are installed
- docker Linux groups is created
- the vagrant user is a member of the docker Linux group (this allows to use Docker client under unprivileges user)
- OpenShift 3.11 repository is configured
- OpenShift client utility is installed
- OpebShift cluster is deployed using "oc cluster up"


### Host machine requrements

The host machine can be configured on the following OS:
- MacOS
- Windows
- Fedora Linux
- CentOS 7

The following software is required:
- VirtualBox(Windows and MacOS)
- libvirt(Linux only)
- Vagrant
- git
- vim


### Starting lab environment
The lab environment can be provisioned using Vagrant as follows:

```
git clone https://github.com/li9com/learn-openshift.git
cd learn-openshift
vagrant up
```

### Connecting to Lab VM

Once VM is provisioned, you may connect to VM using SSH as follows:

```
vagrant ssh
```

Note! You will be connected as the "vagrant" user which is allowed to use sudo to run commands under the root account:

```
sudo yum install -y epel-release
```

You may access OpenShift console using the following URL:

```
https://openshift.172.24.0.11.nip.io:8443/console/
```


## Authors
Artemii Kropachev


