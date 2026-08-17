### Continuous Delivery 

- Some manual approval is required here to deploy the application

### Continuous Deployment

- Its completely Automatic, no manual approval is required.
- If you removal the approval step, then it will become continuous deployment.

<img width="1107" height="524" alt="image" src="https://github.com/user-attachments/assets/426f4b09-7aec-43c7-af03-e2e66bcd11e5" />


- Follow the process which is in Day-5 for EKS setup, tools installations, Plugins, RBAC and configuration of tools, however jenkins file you need to use from `main` branch. And for RBAC, please create a namespace `prod` instead of `dev`
- Create a pipeline upto `Build-Tag & Push Frontend Docker Image`stage and test it. It should be successfull
  
- Now Configure the webhook. Install the plugin

<img width="1412" height="530" alt="image" src="https://github.com/user-attachments/assets/20d89a47-97ad-4ce4-95fb-8df5d59a6f25" />

- Pipeline --> Configure --> Generic webhook trigger --> post content parameters

<img width="1378" height="484" alt="image" src="https://github.com/user-attachments/assets/114b8932-f46d-43dd-b28d-ecbee03e36af" />

- write a token name

<img width="1387" height="457" alt="image" src="https://github.com/user-attachments/assets/65ea9900-3f55-41cc-87fb-31a277d06d18" />

- Input a optional filter

<img width="1415" height="485" alt="image" src="https://github.com/user-attachments/assets/4adef49e-7830-4ca2-ba20-c98caf6623ff" />

- Configure the payload URL and add it inside the github repo, so that github will trigger the pipeline

<img width="1370" height="352" alt="image" src="https://github.com/user-attachments/assets/33fe7d88-ac92-4fda-8d1a-bd06906d8cd4" />

- Settings --> webhooks -> Add webhook --> authenticate github mobile. select push event and click add webhook

<img width="1323" height="271" alt="image" src="https://github.com/user-attachments/assets/f7346ba1-e8fb-452d-9002-7d6221e1a191" />

<img width="1222" height="556" alt="image" src="https://github.com/user-attachments/assets/e0e5b04f-0a1b-4f9b-993d-3d3cd3ee72f4" />

- In recent deliveries, it should show fine

<img width="1500" height="364" alt="image" src="https://github.com/user-attachments/assets/9d2bb0f8-5139-498b-8a94-c29a5abf7aac" />

- Just modify something in github and check the pipeline is triggering or not. It should trigger.
- Now you can paste full code and try.
- If incase certificate is showing not valid, then do the below steps

<img width="999" height="206" alt="image" src="https://github.com/user-attachments/assets/8b015afc-c81f-4aef-bb15-f77adcbbd097" />

<img width="1496" height="748" alt="image" src="https://github.com/user-attachments/assets/2d2e7f57-88c2-4357-a498-9aeb114e908f" />
