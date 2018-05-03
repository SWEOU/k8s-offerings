# AKS Deployment

Azure Container Service (AKS) makes it simple to create, configure, and manage a cluster of virtual machines
that are preconfigured to run containerized applications. This enables you to use your existing skills, or
draw upon a large and growing body of community expertise, to deploy and manage container-based applications on Microsoft Azure.



## Run the following commands to deploy an AKS cluster

Create a resource group in a region that supports AKS 

        az login

        az group create --name myResourceGroup --location eastus

        Note: AKS is supported in the follwing regions at this time. 5/3/18

        Azure Container Service (AKS) is available for preview in the following regions:

        East US
        West Europe
        Central US
        Canada Central
        Canada East

Create the AKS cluster

        az aks create --resource-group myResourceGroup --name myAKSCluster --node-count 1 --generate-ssh-keys

Install the kubectl client on your local machine

        az aks install-cli

Add the credential to the kubectl kubeconfig file

        az aks get-credentials --resource-group myResourceGroup --name myAKSCluster

Verify the cluster is running by issuing the following commands

        kubectl get nodes

You should see something similar to the output shown below

        NAME                              STATUS    ROLES     AGE       VERSION
        aks-nodepool1-23652301-0          Ready     agent     48d       v1.7.9
        virtual-kubelet-connector-linux   Ready     agent     3d        v1.8.3


## Congratulations! You have successfully provisioned an AKS cluster and are ready to start deploying applications and other services for the cluster.