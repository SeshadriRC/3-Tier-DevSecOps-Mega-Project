- Create a Slack account and Workspace.
- Install jenkins in EC2.

<img width="1919" height="928" alt="image" src="https://github.com/user-attachments/assets/9ee71f7f-8dff-48a3-8114-1473177b3bc1" />

- We need to create an app inside Slack. For this app we need to setup a token for authentication and need to setup permissions for that app to write it in the slack channel

- Navigate to this [url](https://api.slack.com/apps) and click create app --> from scratch
    - app name: devopsshack
    - select the workspace which you have created

    <img width="1015" height="682" alt="image" src="https://github.com/user-attachments/assets/3b5b7efd-42eb-4c30-932f-d54d5506d303" />

    <img width="989" height="851" alt="image" src="https://github.com/user-attachments/assets/2323b5d5-673a-4c99-a0c7-5f881749ac7b" />

     <img width="779" height="454" alt="image" src="https://github.com/user-attachments/assets/7b2efca2-34db-4c61-9d1a-a33e8bd4ad41" />

- Click incoming webhooks --> Activate incoming webhooks --> --> Add new webhook --> Select the app and click allow

    <img width="1919" height="818" alt="image" src="https://github.com/user-attachments/assets/99a4f6a9-31eb-4943-b7a5-e1e0ee33f07b" />

    <img width="1911" height="827" alt="image" src="https://github.com/user-attachments/assets/b280451b-d0dd-47ae-b372-2832f8e5c7d8" />

- Setup OAuth Scope
     Oauths and permissions -->  Scopes

<img width="1919" height="942" alt="image" src="https://github.com/user-attachments/assets/55ee7b36-0e40-4ffa-a6ce-39d10e8be046" />

<img width="1909" height="807" alt="image" src="https://github.com/user-attachments/assets/3f52f666-867e-4f56-9dc6-9fa6acbad8da" />

- Click install token and select the channel

<img width="1919" height="947" alt="image" src="https://github.com/user-attachments/assets/013bc2ab-204e-4ffe-9e79-c64312601e9c" />

- Then copy the OAuth token

<img width="895" height="240" alt="image" src="https://github.com/user-attachments/assets/3e9a0a48-a1fb-4e8e-ab8a-43835d9746f1" />

- Now login to jenkins and install the slack plugin

<img width="1414" height="335" alt="image" src="https://github.com/user-attachments/assets/c3610811-85e3-4461-8bfb-90c2b3697fa7" />

- Manage Jenkins --> System --> Slack

   - workspace -> enter your workspace name
   - channel -> enter the channel name
   - token -> paste the token which you have copied, test connection . it should get succees

<img width="1417" height="634" alt="image" src="https://github.com/user-attachments/assets/7ee24f2b-1111-44d5-a8fa-c850ec473473" />

- After giving test, it should show like below

<img width="704" height="331" alt="image" src="https://github.com/user-attachments/assets/1a21f9e2-cb3c-4b9c-b0c2-5cf988dd2f97" />

- Add the webhook URL of slack in jenkins

<img width="1919" height="871" alt="image" src="https://github.com/user-attachments/assets/2082724c-a8ea-473c-884d-bf6218fb7655" />


<img width="1440" height="635" alt="image" src="https://github.com/user-attachments/assets/70e0b68a-3dde-4c1f-abaa-7359c4adeb82" />

- Now run the pipeline, code take from the mega project devsecops repo.
- So if it success, it will show in slack

<img width="1392" height="662" alt="image" src="https://github.com/user-attachments/assets/b1ccb373-b035-42b4-8403-620307d8225d" />

- try for failure from ur end.
