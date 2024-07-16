# In-Class-Activity-2
Creating cluster: “gcloud container clusters create  app --zone us-central1-a --num-nodes 2 --machine-type e2-medium --disk-size 10GB”
 
Creating Namespace
    kubectl create namespace nginx-proxy
    kubectl create namespace wordpress
    kubectl create namespace mariadb
    
Deploy MariaDB
    kubectl apply -f db/secret.yaml
    kubectl apply -f db/deployment.yaml
    kubectl apply -f db/service.yaml
    
Deploy WordPress
    kubectl apply -f wordpress/deployment.yaml
    kubectl apply -f wordpress/service.yaml
    
Deploy Nginx Proxy
    kubectl apply -f nginx/configmap.yaml
    kubectl apply -f nginx/deployment.yaml
    kubectl apply -f nginx/service.yaml

get pods
        kubectl get pods -n mariadb
        kubectl get svc -n mariadb
 
login in to pods
       kubectl exec -it mariadb-deployment-67f94dd4fd-flnm2 -n mariadb -- /bin/bash

log into db
        mariadb -uuser -ppassword wordpress

delete pod to test persistant
        kubectl delete pod mariadb-deployment-67f94dd4fd-flnm2
 
Checking Deployment
    Nginx-service Endpoints: 34.41.166.165:80 
 
 
 
