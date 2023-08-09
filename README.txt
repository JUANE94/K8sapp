# K8sapp
# Crear un pod a traves de una imagen de docker
kubectl run miapp --image="imagen docker" --port=80 80

# Ver los pods creados
kubectl get pods
kubectl describe pod miapp

# Exponer servicio
kubectl expose pod miapp --type=LoadBalancer --port 8080 --target-port=80

kubectl get services

# Solicitar a minikube una url para el servicio
minikube service --url

# Solicitar ip para conectarnos a nuestros servicios.
minikube ip

Check minikube docker en
minikube docker-env
To point your shell to minikube's docker-daemon
eval $(minikube -p minikube docker-env)
# Orquestar servicio a servicio
kubectl apply -f "nombrearchivo.yml"

# K8sMicroservicios
# Construis imagenes de nuestra aplicacion
docker build -t billingapp-back:0.0.4 --no-cache --build-arg JAR_FILE=./*.jar .
docker build -t billingapp-front:0.0.4 --no-cache .

# Orquestar todos los servicios
kubectl apply -f ./

#Ver todos los sevicios
kubectl get all

# Eliminar la orquestacion de la carpeta desde donde la ejecutamos
kubectl delete -f ./
