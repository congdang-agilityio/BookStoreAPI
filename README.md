
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


[Reference](https://www.youtube.com/watch?v=PMY4vYIqU6I)