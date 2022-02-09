This application code is configured to build and deploy on kubernets on mac.  

Step1: Run this command before building docker image. This is required for minikube.  
`eval $(minikube docker-env)`  

Step 2: Build docker image  
`docker build -t frontend-react-app-image -f docker/Dockerfile .`  

Step 3: Create deployment and service on kubernetes  
`kubectl apply -f deployment/deployment.yaml -n <kubernetes-namespace>`  
`kubectl apply -f deployment/service.yaml -n <kubernetes-namespace>`  

Step 4: Open your app in browser  
`minikube service frontend-app-service -n <kubernetes-namespace>`   