# K8sapp
Crear un pod a traves de una imagen de docker
kubectl run miapp --image="imagen docker" --port=80 80
# Ver los pods creados
kubectl get pods
kubectl describe pod miapp
# Exponer servicio
kubectl expose pod miapp --type=LoadBalancer --port 8080 --target-port=80
kubectl get services
# Solicitar a minikube una url para el servicio
minikube service --url miapp
