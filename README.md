# Generac Day 2 - Custom K8s with AKS

## Get Connected

1. Open a browser tab 
2. Log into https://portal.azure.com
    1. Use your MSDN account subscription...
    2. List subscriptions (https://portal.azure.com/#blade/Microsoft_Azure_Billing/SubscriptionsBlade)
    3. Note the subscription name. You will need it below when setting the default subscription for our lab session.
3.  Log into you Azure account and set you default subscription
```bash
az login
az account set -s {Your subscription name or id}
az account show
```

## Create k8s Cluster

1. Create a lab resource group 
```bash
az group create --name rg-kubernetes-training --location centralus
```

2. Create your kubernetes cluster using AKS
```bash
az aks create --resource-group rg-kubernetes-training --name aks-k8s-training --node-count 2 
```

3. Connect to your Kubernetes

Please note, you can get this command from the Azure Portal by looking at the AKS overview and clicking "Connect" at the top of page.

```bash
az aks get-credentials --resource-group rg-kubernetes-training --name aks-k8s-training
```

4. Deploy a pod
    1. C

## Exercises website
http://http://13.65.136.154:8890/

## References and additional information 
### AKS Cluster Reference Links
* [AKS Cluster Creation](https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough)
* [Azure AKS Command Reference](https://docs.microsoft.com/en-us/cli/azure/aks?view=azure-cli-latest#commands)

### AKS How to reference
* [How to use mount a FileShare from an Azure Storage Account in AKS](https://docs.microsoft.com/en-us/azure/aks/azure-files-volume)
* [How to ssh into nodes - not a great idea](https://docs.microsoft.com/en-us/azure/aks/ssh)