# Domain 1 - Notes / Key Takeaways

* **Entra P2 Trial Issue:** When I tried to activate the Entra ID P2 trial, the setup wizard didn't upgrade my existing directory. Instead, it created an entirely new isolated tenant (`RickyTrainingLtd.onmicrosoft.com`). This left me with two completely separate tenants, one with Azure Credit, one with Entra P2 licences. I had to manually transfer the subscription to the new tenant. This has now provided me with a suitable environment to test in.

* **Bulk Upload - Create User:** When I first tried to create users with the (`Files/BulkUploadTraining.csv`), I found it was failing to create them. Firstly, I had to identify where to find the failure reason. I found that Azure updates the csv file itself to state the failure reason rather than displaying it on screen, which I wasn't expecting. So that was an interesting learning point in and of itself. However doing that led me to realise the usage location of 'UK' was incorrect. Some additional research showed that it needed to be set to 'GB' instead. This edition then succeded to create the users.

* **Bulk Upload - Create User:** My (`Files/BulkUploadTraining.csv`) file, which is stored in the Files folder for viewing, contains the  initial passwords for the three users that were created. I have ensured to disable these accounts / passwords prior to uploading to github.

