# Criando-Pods-com-Kubectl-usando-Minikube

https://www.youtube.com/watch?v=OjwQMwgACJk

https://raw.githubusercontent.com/RodrigoMvs123/Criando-Pods-com-Kubectl-usando-Minikube/main/README.md




Criando Pods com Kubectl usando Minikube

Kubernetes - Criando Pods com Kubectl usando Minikube

4:41 

https://docs.docker.com/desktop/windows/install/

https://minikube.sigs.k8s.io/docs/start/
https://github.com/kubernetes/minikube/releases

https://www.youtube.com/watch?v=UE1UqcaSYpM
https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/
kubectl get pods -n kube-system
kubectl version - - client
cat ~/.kube/config

kubectl get pods - - kubeconfig=C:\kube\config -n kube-system

kind
K3s
https://k3d.io/v5.4.3/ 
Instalando a ferramenta kubeadm | Kubernetes

MinuKube ( Cluster de nó único contido em uma máquina virtual VM ) 

Terminal 
Kubernetes:
minikube status
minikute start 
cls 

kube status
kubectl cluster-info 
kubectl get all 

Iperativa 
Diz ao Kubernetes o que fazer.
Usando o kubectl e seus diversos parametros
ideal para aprendizado, fazer experimentos iterativos, testes, debugar serviços
Exemplo: kubectl run nginx  - - image nginx 

Declarativa 
Usa arquivos de manifesto no formato YAML ( ou JSON ) e aplica usando o comando kubectl apply 
Diz ao kubernetes o que você quer. 
Ideal para implantar serviços de forma controlada
Recomendado para gerenciar aplicações kubernetes em produção 
Exemplo : kubectl apply -f newpod.yaml 

Arquivos Manifestos YAML 
Os arquivos YAML contém as definições de 
deployments, 
services, 
pods,
namespaces,
replicasets,
configmaps,
secrets, 
nodes, 
e outros objetos que queremos definir.

Pod 
apiVersion: v1 ( indica a versão da API kubernetes usada para criar o objeto )

Kind: Pod (define o tipo do objeto a ser criado: Pod, Deployment, ReplicaSet, Service, Namespace ) 

metadata: ( define os dados do objeto como: name, labels ( é um dicionário ) 
name: pod-nginx

spec: 
 containers:
image: cont-nginx 
name: nginx 
ports:
containerPort: 80 
pod1.yaml ( kubectl apply -f pod1.yaml

Obs: spec define as especificações do objeto que desejamos criar. Varia conforme o objeto que vamos criar. Aqui estamos criando um pod com um container usando a imagem o nginx na porta 80.
Container é uma lista ou um Array pois um pod pode conter múltiplos containers ( indicamos uma lista com “-” )



Criando um Pod 
Pod é a menor unidade de um cluster Kubernetes que roda nos Nodes e onde são executados os containers.

Cluster ( Contem 1 ou mais Worder Nodes ( Hardware ou VM ) 
Node ( Pode conter 1 ou mais Pods )

Pod ( Menor unidade do Kubernetes )
Obs: os pod tem um ciclo de vida contendo status 
Pending / Running / Succeed / Failed 


Declarativa 
Definir arquivo manifesto YAML / Enviar o manifesto para a API server / Pod

Imperativa ( Usar o Kubectl ) 
Definir arquivo manifesto YAML / Enviar o manifesto para a API server / Pod 

cls 
Criar um Pod na forma Iterativa 

kuberun pod-nginx - - image nginx 
kubectl get all
kubectl get pods 
kubectl get nodes
kubectl describe pods 
cls

kubectl get all
kubectl delete pod pod-nginx
kubectl get all ( Cluster ) 


Criar um Pod na forma declarativa

dir 
Visual Studio Code 
Extension Kubernetes

apiVersion: v1 ( indica a versão da API kubernetes usada para criar o objeto )

Kind: Pod (define o tipo do objeto a ser criado: Pod, Deployment, ReplicaSet, Service, Namespace ) 

metadata: ( define os dados do objeto como: name, labels ( é um dicionário ) 
name: pod-nginx

spec: 
 containers:
image: cont-nginx 
name: nginx 
ports:
containerPort: 80 

Criar 
Pod ( Kubernetes Pod ) 
apiVersion: v1
kind: pod
metadata: 
 name: myapp
 labels :
  name: myapp
spec: 
 containers:
name: myapp
image: <image>
resources: 
limits: 
 memory: “128mi”
cpu: “500m
   ports: 
containerPort: <Port>

Criar 
Kubernetes deployment 

apiVersion: app/v1 
kind: Deployment
metadata: 
 name: myapp
spec:
 selector: 
 matchLabels:
  app: myapp 
 template: 
  metadata:
   labels: 
    app: myapp
       spec: 
        containers: 
name: myapp
image: <image> 
resources:
  limits: 
    memory: “128Mi” 
    cpu: “500m”
ports:
containerPort: <Port> 


cls 
kubectl get all ( Cluster ) 
kubectl apply -f pod1.yaml
kubectl get all
kubectl get pods 
kubectl get nodes
kubectl describe pods 
cls


kubectl get all
kubectl exec -ti pod-nginx - - sh ( Comando Shell ) 
# ls

# ls - l 
exit 

kubectl get all ( Running ) 

