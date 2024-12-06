# helm-efs-test

#Deploy with Helmchart for automate deployment on Amazon EKS with  EFS
This guide helps you set up and deploy Pod using Helm, and create an EFS (Elastic File System) for persistent storage.

Prerequisites
AWS CLI v2
Docker
kubectl
eksctl
Helm 3

1. Install Helm
   curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
   chmod 700 get_helm.sh
   ./get_helm.sh

2. Setup AWS CLI
   curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
   sudo apt install unzip
   unzip awscliv2.zip
   sudo ./aws/install -i /usr/local/aws-cli -b /usr/local/bin --update
   aws configure

3. Install kubectl
   curl -o kubectl https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/linux/amd64/kubectl
   chmod +x ./kubectl
   sudo mv ./kubectl /usr/local/bin

4. Install eksctl
   curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
   sudo mv /tmp/eksctl /usr/local/bin

5. Create EKS cluster with defined roles and policies 
6. Create EFS in AWS
   Go to the Amazon EFS console and create a new file system.
   Configure it with default settings and ensure it's in the same VPC as your EKS cluster.
   Note the File System ID.

7. Install Helm chart
   helm install my-nginx . --namespace default



