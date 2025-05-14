# cloud_data

--------------------------docker installation steps------------------------

1) sudo apt-get update

2) sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys ED65462EC8D5E4C5
[if update is not working coz no pubkey is included then add pub key and do this command]

3) sudo apt-get install ca-certificates curl

4) sudo install -m 0755 -d /etc/apt/keyrings

5) sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc

6) sudo chmod a+r /etc/apt/keyrings/docker.asc

7) 
    echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "bookworm") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

9) sudo apt-get update

10) ──(kali㉿kali)-[~]
└─$ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

11) ──(kali㉿kali)-[~]
└─$ sudo docker run hello-world



------------------------------install kubectl---------------------------------


1) └─$ sudo rm /usr/local/bin/kubectl

2) sudo apt install kubectl


------------------------minikube install----------------------------------------

uninstall - $ sudo rm /usr/bin/minikube  

1) curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

2) chmod +x minikube-linux-amd64

3) sudo mv minikube-linux-amd64 /usr/local/bin/minikube



---------------------------------------------------------------------------------

1. Pull Image from repo https://hub.docker.com/r/nigga4059/dc4-qemu using command 

 docker pull nigga4059/dc4-qemu

2. Then do 

docker run -it --privileged -p 80:80 --name dc4_container nigga4059/dc4-qemu

wait for some time .....
you will get some loading message in terminal 

[ if docker container already present then use sudo docker rm dc4_container]

3. Try to get ip of continaer using the command

  docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' dc4_container

RUn this in differnt terminal.

4. You will get a ip 
5. When you go to that ip, you will get login form.

6. Use Burpsuite to do brute force . For more details follow this page https://c15c01337.medium.com/dc-4-vulnerable-machine-walkthrough-12e1dd63a11e

7. make sure firefox have burpsuite certificate in it .


-----------------------------------------------------------------------------------------------------------------


if he tell to create pods and add dc4 in that steps - 

$ sudo systemctl status docker 

$ sudo systemctl enable docker

$ minikube version

$ kubectl version --client 

$ minikube status

$ minikube start --driver=docker

$ minikube status

$ kubectl get pods 
NAME                    READY   STATUS             RESTARTS       AGE
kali                    0/1     Error              0              6d22h
kali-5dfd64b7c8-bs8b6   0/1     CrashLoopBackOff   43 (29s ago)   6d22h

$ kubectl delete pod kali-5dfd64b7c8-gh4h8

$ kubectl delete pod kali 

$ kubectl get pods                        
NAME                    READY   STATUS      RESTARTS       AGE
kali-5dfd64b7c8-bs8b6   0/1     Completed   44 (56s ago)   6d22h

$ kubectl run kali --image=kalilinux/kali-rolling --restart=Never -- /bin/sh -c "while true; do sleep 3600; done"
pod/kali created

$ kubectl get pods                                                                                               
NAME                    READY   STATUS             RESTARTS     AGE
kali                    1/1     Running            0            6s
kali-5dfd64b7c8-bfqfn   0/1     CrashLoopBackOff   3 (6s ago)   64s

$ kubectl run dc4 --image=nginx --restart=Never -- /bin/sh -c "while true; do sleep 3600; done"    

pod/dc4 created

$ kubectl get pods
NAME                    READY   STATUS             RESTARTS       AGE
dc4                     1/1     Running            0              54s
kali                    1/1     Running            0              12m
kali-5dfd64b7c8-bfqfn   0/1     CrashLoopBackOff   7 (106s ago)   13m




kubectl get pods -o wide 

kubectl exec -it kali -- /bin/bash

kali shell will be running with minimum:

apt update && apt install -y iputils-ping curl nmap netcat 

apt update && apt install -y iputils-ping


aws link

https://adityabh333.signin.aws.amazon.com/console
pratik , sarkar@1234


To install docker in kali if sudo doesn't work 

=> apt update
=> apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin



Optional: To run Docker without sudo (add current user to docker group):

sudo usermod -aG docker $USER
newgrp docker



