the ansibel script is just to install packages and not actual installation 

You can now join any number of control-plane nodes by copying certificate authorities
and service account keys on each node and then running the following as root:

  kubeadm join kube-master:6443 --token em4nui.rd0r2pjmnfaqek6l \
    --discovery-token-ca-cert-hash sha256:7bdf1818546290b8b7e6bef875c611f578cefc113e1d81331f5b374a82848b78 \
    --control-plane 

Then you can join any number of worker nodes by running the following on each as root:

kubeadm join kube-master:6443 --token em4nui.rd0r2pjmnfaqek6l \
    --discovery-token-ca-cert-hash sha256:7bdf1818546290b8b7e6bef875c611f578cefc113e1d81331f5b374a82848b78 

    workernodes activities
    -just install compatibale docker and kubeadm 
    then run output of that kubeadm init 


 for calico
 https://docs.projectcalico.org/getting-started/kubernetes/quickstart
 https://medium.com/platformer-blog/running-a-kubernetes-cluster-on-ubuntu-with-calico-9e372fb9175e
