# n00bernetes
Learning Kubernetes locally with Minikube. 

**Not for production.**
<br/>
<br/>

# About
This is a repo of 5 microservices built with NodeJS, and a React frontend. 

There is a focus on building each part from scratch although it's not realistic in a production setting.

Data for **Comments** and **Posts** are stored in their own DBs for self-containment & isolation. 

When new data is created, the data is duplicated in the **Query** service's DB, so users can fetch necessary data with 1 request to the **Query** service.

<hr/>

I Dockerized the applications so I can create **deployments** with Kubernetes. 

The pods of different microservices communicate with each other via HTTP requests to Cluster IP Services. 

The entrypoint into the Kubernetes cluster is a Load Balancer service mapped to an Ingress Controller using [nginx-ingress](https://github.com/kubernetes/ingress-nginx). 

<hr/>

[Skaffold](https://github.com/GoogleContainerTools/skaffold) was used to update my cluster when a relevant file was changed, making for a pleasant experience during development.
