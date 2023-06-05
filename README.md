

# install eksctl on your architecture


sudo snap install helm --classic

sudo snap install kubectl --classic


## for ARM systems, set ARCH to: `arm64`, `armv6` or `armv7`
```
ARCH=arm64
PLATFORM=$(uname -s)_$ARCH

curl -sLO "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$PLATFORM.tar.gz"

curl -sL "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_checksums.txt" | grep $PLATFORM | sha256sum --check

tar -xzf eksctl_$PLATFORM.tar.gz -C /tmp && rm eksctl_$PLATFORM.tar.gz

sudo mv /tmp/eksctl /usr/local/bin

```

# install aws cli


curl "https://awscli.amazonaws.com/awscli-exe-linux-aarch64.zip" -o "awscliv2.zip"

sudo apt install unzip

unzip awscliv2.zip

sudo ./aws/install --bin-dir /usr/bin --install-dir /usr/aws-cli --update

aws --version

aws configure

eksctl create cluster demo

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm search repo ingress-nginx --versions

helm install ingress-nginx ingress-nginx/ingress-nginx 

kubectl get svc

kubectl apply -f deployment-foo.yaml
kubectl apply -f deployment-bar.yaml

kubectl apply -f ingress.yaml
# ingress-controller
