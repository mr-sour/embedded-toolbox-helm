# embedded-toolbox-helm
For development of my personal connected home. Powered by kubernetes, yocto , labgrid, tekton
tested on fedora 35 but should work anywhere kubernetes will depoy (helm required)
#### bootstrap kubernetes cluster
https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-using-native-package-management
https://www.talos.dev/v1.0/introduction/quickstart/

#### clone repo
`git clone https://github.com/mr-sour/embedded-toolbox-helm.git`
# cd 
`cd ./embedded-toolbox-helm`
#### download dependencys
`helm dependency update`
#### bootstrap cluster
`helm upgrade --install argo ./ -n argocd --create-namespace`
#### make ssh secret for argocd
`ssh-keygen -t ed25519 `
#### upload public key to repository of chosing
`kubectl create secret generic ssh-keys --from-file=id=/home/YOUR_USERNAME/.ssh/id_ed25519 --from-file=id_pub=/home/YOUR_USERNAME/.ssh/id_ed25519.pub`
#### get inital admin password
`kubectl  get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo`
#### portforward for local access
`kubectl port-forward svc/argocd-server 8080:443`
#### goto localhost:8080
user:admin pw:xxxxx

setup terminal
sudo screen /dev/ttyUSB0 115200
press button to get into uboot

todo (uboot config to yaml)

This instance of argo-cd will require updates to the image every now and again. https://github.com/argoproj/argo-cd/releases 

#### Operator reference
https://argoproj.github.io/argo-cd/operator-manual/declarative-setup/
# Sign in with the cli 
Install the CLI
https://argoproj.github.io/argo-cd/cli_installation/

Login with this command

![image](https://user-images.githubusercontent.com/2181180/166573169-cd2f8ad7-3813-4c0e-a061-b33d649a292f.png)
