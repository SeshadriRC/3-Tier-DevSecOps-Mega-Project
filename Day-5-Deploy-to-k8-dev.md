# CI 
- Follow this [doc](https://github.com/SeshadriRC/3-Tier-DevSecOps-Mega-Project/blob/main/eks-steps.md) to provision EKS using terraform, create RBAC.
- Post that provision another EC2 (t2.medium), storage (30GB)  --> 2 instances ( one for ec2 and other for sonarqube )
- Install Jenkins and Sonarqube on the respective server. And also in jenkins server also you need to install
   - docker
   - gitleaks (`sudo apt install gitleaks`)
   - trivy ( follow the official doc )
   - plugin -> nodejs
- In Sonar server run below commands

  ```bash
   sudo usermod -aG docker ubuntu
   newgrp docker
  ```

- In Jenkins server run below commands

```bash
sudo usermod -aG docker jenkins
newgrp docker
```

- Copy the Jenkinsfile from `deploy-to-dev-k8` branch ( copy upto Build-Tag & Push Frontend Docker Image stage ) and create a pipeline. Discard old builds and max of #2
- In jenkins UI, configure tools -> Nodejs, Creds for docker and sonar, System -> Sonarserver and scanner, Plugin -> docker pipeline, kubernetes, kubernetes credentials, kubernetes cli
- In sonarqube UI, configure webhook for sonar quality gate
- Click build now and check pipeline is working fine or not. Pipeline should get successfull. So CI is success

---

# CD

- Create a token for `jenkins` service account. you can find the steps in RBAC page.
- Apply the `yml` file in `dev` namespace. Run this in first EC2 which we have created.
---
