- Follow this [doc](https://github.com/SeshadriRC/3-Tier-DevSecOps-Mega-Project/blob/main/eks-steps.md) to provision EKS using terraform, create RBAC.
- Post that provision another EC2 (t2.medium), storage (30GB)  --> 2 instances ( one for ec2 and other for sonarqube )
- Install Jenkins and Sonarqube on the respective server. And also in jenkins server also you need to install docker.
- In Sonar server run below commands

  ```bash
   sudo usermod -aG docker ubuntu
   newgrp docker
  ```
