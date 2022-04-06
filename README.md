
BookStoreAPI
==

### .Net API example

This project is an API project and use a depedency Data Layer to store data

#### Run local with docker
1. Build 

    `docker build -t congdang/bookstoreapi .`

2. Run

    `docker run -p 2001:80 congdang/bookstoreapi` 

3. Run on browser

    `http://localhost:2001/api/books`

4. Push to Docker hub

    `docker login` and `docker push congdang/bookstoreapi:latest`

#### Deploy to Azure Container Instances

1. Create Container Instances on Azure Portal

2. Config to deploy the image from Docker Hub to Container Instances

#### Deploy to Azure Kubenetes

1. Create a resource Group

    `az group create --name myResourceGroup --location eastus`

2. Create AKS cluster

    `az aks create --resource-group myResourceGroup --name myAKSCluster --node-count 1 --enable-addons monitoring --generate-ssh-keys`

3. Connect to the cluster

    - Install `kubectl`
    `az aks install-cli`

    - Get credentials
    `az aks get-credentials --resource-group myResourceGroup --name myAKSCluster`

    - Verify Connection
    `kubectl get nodes`

4. Deploy the App

    `kubectl apply -f deploy-k8s.yaml`

5. Test the application

    `kubectl get service bookstoreapi --watch`

    You will see the public IP of LoadBalancer like below

    ```
    bookstoreapoi   LoadBalancer   10.0.37.27   52.179.23.131   80:30572/TCP   2m
    ```
6. Run API on browser 

    `http://loadblancer-ip/api/books`

#### References

1. [Containerize a .NET Core API and run it on Azure container instance](https://www.youtube.com/watch?v=PMY4vYIqU6I)

2. [Deploy an Azure Kubernetes Service cluster using the Azure CLI](https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough#create-aks-cluster?ocid=AID754288&wt.mc_id=azfr-c9-cxa&wt.mc_id=CFID0517)