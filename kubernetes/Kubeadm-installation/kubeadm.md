# Install-Kubernetes-Kubeadm-on-Ubuntu for ALL Nodes ( Master and Worker) both 

rm -rf kubernetes
git clone https://github.com/SumonPaul18/kubernetes.git
chmod -R +x kubernetes/install-kubeadm
. kubernetes/install-kubeadm/install-kubeadm-allnode.sh

# Only On Master-Node 

rm -rf kubernetes
git clone https://github.com/SumonPaul18/kubernetes.git
chmod -R +x kubernetes/install-kubeadm
. kubernetes/install-kubeadm/kubeadm-master.sh

# Joining worker node to a Kubernetes Cluster (Note : use your join command )
kubeadm join 192.168.1.71:6443 --token 8quago.4ftd2ds092wbb95h --discovery-token-ca-cert-hash sha256:f2e7f356a7f84f05b1623d926868a9c98ba6fe59914067ccbc61764843b71cfd 

# then verify on master node 
kubectl get nodes

# then label the nodes as worker 
kubectl label node <your-node-name> node-role.kubernetes.io/worker=worker


