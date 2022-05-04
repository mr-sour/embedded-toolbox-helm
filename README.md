# embedded-toolbox-helm
For development of my personal connected home. Powered by kubernetes.
# install k3s
1.) `curl -sfL https://get.k3s.io | sh -`
# clone repo
2.) `git clone https://github.com/mr-sour/embedded-toolbox-helm.git`
# cd 
3.) `cd ./embedded-toolbox-helm`
# download dependencys
5.) `helm dependency update`
# bootstrap cluster
4.) `helm install argo ./`
# 
5.) todo: login to argo

This instance of argo-cd will require updates to the image every now and again. https://github.com/argoproj/argo-cd/releases 

#### Operator reference
https://argoproj.github.io/argo-cd/operator-manual/declarative-setup/
# Sign in with the cli 
Install the CLI
https://argoproj.github.io/argo-cd/cli_installation/

Login with this command

![image](https://user-images.githubusercontent.com/2181180/166573169-cd2f8ad7-3813-4c0e-a061-b33d649a292f.png)
