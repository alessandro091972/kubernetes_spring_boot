# kubernetes Spring Boot

## Docker
Start Docker Dekstop on your machine (must have been previously installed)

login Docker 

By cmd/dos:

docker login

Username: [your Docker Username]

Email: [your Docker email]

Password: [your Docker password] 

## Delete all previous instances
kubectl delete all -l app=currency-exchange

kubectl delete all -l app=currency-conversion

## Create deployment
kubectl apply -f deployment-currency-exchange.yaml

kubectl apply -f deployment-currency-conversion.yaml

Inside the yaml files are links to my docker repository images for two spring boot projects.

Yaml files include services, replicaset, configmap, etc


## List services:
kubectl get services

## List pod:
kubectl get pods

## List replicaset:
kubectl get replicaset
kubectl get rs

## Watch services:
kubectl get svc --watch

## List deployments:
kubectl get deployments

## List all elements:
kubectl get all

## Get configmap:
kubectl get configmap

## Get logs:
kubectl get pods
kubectl logs -f [NAME]


## Get  health
http://localhost:8000/actuator

http://localhost:8000/actuator/health

http://localhost:8000/actuator/health/liveness


## autoscale
kubectl autoscale deployment currency-exchange --min=1 --max=3 --cpu-percent=70

It means that if the cpu is greater than 70%, a new pod will be created up to a maximum of 3

## Get deployment history
kubectl rollout history deployment currency-conversion

kubectl rollout history deployment currency-exchange

## Url 
Currency Exchange Service   http://localhost:8000/currency-exchange/from/USD/to/INR

Currency Conversion Service http://localhost:8100/currency-conversion-feign/from/USD/to/INR/quantity/10
