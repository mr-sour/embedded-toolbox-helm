# embedded-toolbox-helm
For development of my personal connected home. Powered by kubernetes, yocto , labgrid, tekton
tested on fedora 35 but should work anywhere argocd will depoy (helm required)
#### install k3s 
`sudo kubectl config view --raw > ~/.kube/config`
`sudo chmod 644 /etc/rancher/k3s/k3s.yaml`
#### clone repo
`git clone https://github.com/mr-sour/embedded-toolbox-helm.git`
# cd 
`cd ./embedded-toolbox-helm`
#### download dependencys
`helm dependency update`
#### bootstrap cluster
`helm upgrade --install argo ./`
#### portforward for local access
`kubectl port-forward svc/argocd-server 8080:443`
#### get inital admin password
`kubectl  get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo`
#### goto localhost:8080
user:admin pw:xxxxx


This instance of argo-cd will require updates to the image every now and again. https://github.com/argoproj/argo-cd/releases 

#### Operator reference
https://argoproj.github.io/argo-cd/operator-manual/declarative-setup/
# Sign in with the cli 
Install the CLI
https://argoproj.github.io/argo-cd/cli_installation/

Login with this command

![image](https://user-images.githubusercontent.com/2181180/166573169-cd2f8ad7-3813-4c0e-a061-b33d649a292f.png)
