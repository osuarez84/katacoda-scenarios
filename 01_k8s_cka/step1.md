This scenario will give you a sandbox with kubeadm pre-installed to play
with an environment of Kubernetes.


We first check the installed version of kubeadm on each node:

`kubeadm version`{{execute HOST1}}
`kubeadm version`{{execute HOST2}}

We must update to the latest version of kubeadm and kubelet on each node:

Host1:
`apt-get update && apt-get install -y --allow-change-held-packages kubeadm=1.20.0-00`{{execute HOST1}}
`apt-get update && apt-get install -y --allow-change-held-packages kubelet=1.20.0-00 kubectl=1.20.0-00`{{execute HOST1}}

Host2:
`apt-get update && apt-get install -y --allow-change-held-packages kubeadm=1.20.0-00`{{execute HOST2}}
`apt-get update && apt-get install -y --allow-change-held-packages kubelet=1.20.0-00 kubectl=1.20.0-00`{{execute HOST2}}

Restart the kubelet:

Host1:
`sudo systemctl daemon-reload`{{execute HOST1}}
`sudo systemctl restart kubelet`{{execute HOST1}}

Host2:
`sudo systemctl daemon-reload`{{execute HOST2}}
`sudo systemctl restart kubelet`{{execute HOST2}}
