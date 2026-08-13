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


<img width="961" height="616" alt="image" src="https://github.com/user-attachments/assets/e4433a15-5864-4b62-8022-b0129bd05bc6" />



---

**Github Organization Access**

<img width="1272" height="557" alt="image" src="https://github.com/user-attachments/assets/d710ac12-6506-4158-89a9-5c58d4b53cee" />


<img width="828" height="553" alt="image" src="https://github.com/user-attachments/assets/72593602-97a3-4cc2-b4c5-8a99af1198e0" />


- Create github organization


<img width="1076" height="675" alt="image" src="https://github.com/user-attachments/assets/cd8c3640-064e-4c80-8da9-5d721d849ccb" />


<img width="900" height="375" alt="image" src="https://github.com/user-attachments/assets/f8c16570-cc6e-42f1-ba20-27084a8f44c8" />

- Organization is ready


<img width="1316" height="681" alt="image" src="https://github.com/user-attachments/assets/5903b73e-8a4e-4fe5-9687-44fb56536541" />


- Invite member to org


<img width="1211" height="575" alt="image" src="https://github.com/user-attachments/assets/7d86b840-1e06-4e40-bee4-149130ddddcb" />

- Remove all permissions


<img width="1549" height="750" alt="image" src="https://github.com/user-attachments/assets/5fb3b9a1-57bd-4d8e-885b-65ff8bb301ce" />

- Create a new team


<img width="1404" height="727" alt="image" src="https://github.com/user-attachments/assets/c1db1f1f-8651-4e56-b2ee-b798d1d2380e" />


<img width="996" height="613" alt="image" src="https://github.com/user-attachments/assets/b596864a-bb28-49ee-9937-74e6e96e3388" />

- Assign the role to the new team


<img width="1550" height="739" alt="image" src="https://github.com/user-attachments/assets/084fd22a-a817-46c1-be99-9d65e81839a8" />

---


