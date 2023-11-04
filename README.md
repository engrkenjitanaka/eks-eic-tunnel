# SSH tunnels through EC2 Instance Connect (EIC) endpoint to access EKS



A simple script to create a SSH tunnel through EC2 Instance Connect (EIC) endpoint to access EKS.

How to use the script:
```
eic-cluster-connect -p <aws_profile> -r <aws_region> -u <bastion_user> -c <eks_cluster> 
```

Caveats:
```
1. You would need to have an EC2 instance to tunnel into -- scripts defaults to EC2 instances with the tag (eic: bastion-eic).
2. The tunnels only lasts for upto 60 minutes due to some API constraints from AWS.
3. Backup your kubeconfig file. This will delete the existing one.
4. You can loop through this script to create multiple tunnels for multiple EKS clusters.
```