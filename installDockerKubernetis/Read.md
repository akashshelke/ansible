Step1. run the ansibel script 
#ansible-playbook kubeadm_docker_install.yml

Step2:
on master node run kubeadm init
#kubeadm init --pod-network-cidr=192.168.0.0/16 --control-plane-endpoint=kube-master 

control-plane-endpoint is kind of hostname alias, this helps when more master are added in future. You can add this alias to your master node in /etc/hosts or dns of every worker node
#cat /etc/hosts |grep mater
<ip of master> <fqdn of master> kube-master 

step3: above commands will return some more commands and instruction, please folloe those as it is 

setp4:initiate calico network before joining network like below 
systemctl enable docker.service;systemctl enable kubelet.service
   40  kubectl apply -f https://docs.projectcalico.org/manifests/calico.yaml
   41  kubeadm join kube-master:6443 --token <token>     --discovery-token-ca-cert-hash <hash>

 for more calico and kubeadm
 https://docs.projectcalico.org/getting-started/kubernetes/quickstart
 https://medium.com/platformer-blog/running-a-kubernetes-cluster-on-ubuntu-with-calico-9e372fb9175e
