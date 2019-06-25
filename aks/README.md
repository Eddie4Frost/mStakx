
This playbook deploy a AKS cluster on Azure

prerequisites:
Ansible 2.6 or higher
```
$ sudo apt-get update
$ sudo apt-get install software-properties-common
$ sudo apt-add-repository --yes --update ppa:ansible/ansible
$ sudo apt-get install ansible
```

To execute the command line of Ansible for azure resources it's necessary install the Azure Ansible SDK

```
pip install 'ansible[azure]'
```

Credentials
The most usefull method to play this playbook is define the variables after play this

AZURE_CLIENT_ID
AZURE_SECRET
AZURE_SUBSCRIPTION_ID
AZURE_TENANT

It's possible create a file $HOME/.azure/credentials with the credentials. See below.
```
[default]
subscription_id=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
client_id=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
secret=xxxxxxxxxxxxxxxxx
tenant=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Using it:

Create a cluster:
```
export ENVIRONMENT=level1
export SSH_KEY=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
export AZURE_CLIENT_ID=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
export AZURE_SECRET=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
export AZURE_SUBSCRIPTION_ID=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
export AZURE_TENANT=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ansible-playbook create-k8s-cluster.yml
```

Delete a cluster
```
export ENVIRONMENT=DEV
export AZURE_CLIENT_ID=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
export AZURE_SECRET=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
export AZURE_SUBSCRIPTION_ID=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
export AZURE_TENANT=xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ansible-playbook delete-k8s-cluster.yml
```
