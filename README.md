# linode ssh key add ?
ssh-keygen -t rsa
Enter x 3
ls -la
cd .ssh/
cat ~/.ssh/id_rsa.pub
then,copy
add on linode's add key
login : root
pass : type yours

# # #

sudo apt update -y && sudo apt upgrade -y
sudo reboot
sudo apt install docker.io
sudo usermod -aG docker $USER && newgrp docker
sudo apt install -y curl wget apt-transport-https
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube version


curl -LO https://storage.googleapis.com/kubernetes-release/release/`
curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

chmod +x kubectl
sudo mv kubectl /usr/local/bin
kubectl version -o yaml
minikube start - vm-driver=docker

minikube status
kubectl version
kubectl get nodes

#First Node Create
vim Day04.yml

kind: Pod                              
apiVersion: v1                     
metadata:                           
  name: testpod                  
spec:                                    
  containers:                      
    - name: c00                     
      image: ubuntu              
      command: ["/bin/bash", "-c", "while true; do echo Hello-Kubernetes; sleep 5 ; done"]
    - name: container2
      image: ubuntu
      command: ["/bin/bash", "-c", "while true; do echo Second Container is still running; sleep 3 ; done"]
  restartPolicy: Never

  #Deploy pod
  kubectl apply -f Day04.yml
  kubectl get pods
  kubectl logs -f pod1

#To check the logs of the primary container, specify the container name:

kubectl logs -f pod1 -c container1

#To check the logs of the second container, specify the container name:

kubectl logs -f pod1 -c container2

Delete the Pod:

To delete the pod, use this command:

kubectl delete pod pod1

To list the IP of the pod, use the below command.

kubectl pod pod1 -c container1 — hostname -i

kubectl delete -f Day04.yml




