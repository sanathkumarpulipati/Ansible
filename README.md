# Ansible
Kubernetes Playbooks
Ansible playbooks that creates a Kubernetes 1.28 cluster running on Ubuntu 22.04 LTS. Additional playbooks contain Metallb and Nginx Ingress controller creation.

Prerequisites :
1 Master and Worker VM's with minimum 2CPU and 2GB RAM
2 Ansible VM
3 Password less SSH to master and worker VM's from ansible VM
4 Update the available IP address range in ip_address_range.yml file in templates folder
5 Update k8's master and worker IP's in hosts file

Files :

1 hosts - contains master and worker ips

2 install_k8s.yml - installs kubernetes cluster dependencies

3 master.yml - initiates master node and cni setup

4 worker.yml - worker node joins

5 install_helm.yml - helm installation

6 metallb.yml - metallb installation

7 nginx_ingress.yml - nginx ingress installation

8 template - ip_address_range.yml and advertise.yml files

Playbooks execution :

kubernetes cluster creation: 

1 ansible-playbook -i hosts install_k8s.yml

2 ansible-playbook -i hosts master.yml

3 ansible-playbook -i hosts worker.yml

Helm Installation :

1 ansible-playbook -i hosts install_helm.yml

MetalLB Installation :

1 ansible-playbook -i hosts metallb.yml

Nginx Ingress Installation :

1 ansible-playbook -i hosts nginx_ingress.yml

2 test
