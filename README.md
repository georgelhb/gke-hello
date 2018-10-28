#### The code shows how to use Cloud Build to build a Docker image and deploy it to a GKE cluster.
---
1) Start the Cloud Build by running the following command: <br/>
```
gcloud builds submit --config cloudbuild.yaml .
```
2) Creating a GKE cluster and get authentication credentials for the cluster <br/>
3) Creates a new Deployment named hello-server: <br/>
```
kubectl run hello-server --image [CONTAINER_IMAGE] --port 8080
```
4) Expose the deployment to the Internet: <br/>
```
kubectl expose deployment hello-server --type LoadBalancer --port 80 --target-port 8080
```
5) Inspect the hello-server Service: <br/>
```
kubectl get service hello-server
```
6) View the application from your web browser using the external IP address: <br/>
```
http://[EXTERNAL_IP]/
```
