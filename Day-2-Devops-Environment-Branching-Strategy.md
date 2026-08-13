**Devops Environment**

Dev(development) - new feature will be devoloped here
QA(Quality Assurance) - main task is remove all bugs, code is properly tested
Stage(pre prod)- before prod, we will deploy here
Prod - Live environment, its most important .
DR (disaster recovery) - If prod got crashed, immediately it should switchover to DR. user should able to access from DR, until we fix the error.

<img width="1221" height="677" alt="image" src="https://github.com/user-attachments/assets/fe82cd53-d545-4211-890c-8fa7ba9ef2b6" />

---

**Branching Strategy**

Dev branch --> new feature will be developed by multiple developers and then it got merged to QA branch ( dev branch -> RC-1, RC-2, RC-3 , RC means release candidate. will make sure all issues are fixed in RC-3 )
QA branch --> Here multiple testing will be happen, if any bug is there then they will create a new bug fix branch , then fix and merge back to QA. so once all good QA branch is merged to PPD branch
PPD branch --> here we won't make any changes, we will deploy the application and monitor. if all looks good then it will be merged to main branch.
Prod --> then from the main branch, app will be deployed to prod and monitored. if in case any issue then we will create a hot fix branch and merged to main, then redeploy to prod
DR --> finally we are merging to DR branch and deploying to DR environment


So totally 5 kubernetes clusters

---

**Github Organization Access**

<img width="1272" height="557" alt="image" src="https://github.com/user-attachments/assets/d710ac12-6506-4158-89a9-5c58d4b53cee" />



---


<img width="1028" height="635" alt="image" src="https://github.com/user-attachments/assets/86ee80fd-d7a1-4ac8-8787-8aeec59e33ae" />

<img width="828" height="553" alt="image" src="https://github.com/user-attachments/assets/72593602-97a3-4cc2-b4c5-8a99af1198e0" />


---


