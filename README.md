# This repo is being deprecated. Please check out https://github.com/cdxvirt/k8sup

#hyperkube-utils-on-coreos

Deploy a Kubernetes HA Cluster on CoreOS using hyperkube

### First node ######

`$ git clone https://github.com/hsfeng/hyperkube-utils-on-coreos.git`

`$ cd hyperkube-utils-on-coreos`

`$ sudo ./coreos-config <node ip address>`

`$ sudo reboot`

### Other nodes ####

`$ git clone https://github.com/hsfeng/hyperkube-utils-on-coreos.git`

`$ cd hyperkube-utils-on-coreos`

`$ source ./init-etcd-members <first node ip>`

`$ sudo -E ./coreos-config <node ip address>`

`$ sudo reboot`



### Run kube-up ####

After ETCD cluster has been initialized. Run kube-up on each node

`$ ./kube-up <node ip address>`


### Create kube-system namespace ###
`$ wget https://raw.githubusercontent.com/kubernetes/kubernetes/master/cluster/mesos/docker/kube-system-ns.yaml`

`kubectl create -f kube-system-ns.yaml`
