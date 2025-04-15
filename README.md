# Ansible
Kubernetes Playbooks
Ansible playbooks that creates a Kubernetes 1.28 cluster running on Ubuntu 22.04 LTS. Additional playbooks contain Metallb and Nginx Ingress controller creation.

Prerequisites
Master and Worker VM's with minimum 2CPU and 2GB RAM
Ansible VM
Password less SSH to master and worker VM's from ansible VM
Update the available IP address range in ip_address_range.yml file in templates folder
Update k8's master and worker IP's in hosts file
Files
hosts - contains master and worker ips
install_k8s.yml - installs kubernetes cluster dependencies
master.yml - initiates master node and cni setup
worker.yml - worker node joins
install_helm.yml - helm installation
metallb.yml - metallb installation
nginx_ingress.yml - nginx ingress installation
template - ip_address_range.yml and advertise.yml files
Playbooks execution
kubernetes cluster creation

ansible-playbook -i hosts install_k8s.yml

ansible-playbook -i hosts master.yml

ansible-playbook -i hosts worker.yml

Helm Installation

ansible-playbook -i hosts install_helm.yml

MetalLB Installation

ansible-playbook -i hosts metallb.yml

Nginx Ingress Installation

ansible-playbook -i hosts nginx_ingress.yml

test
