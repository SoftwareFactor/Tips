# Azure App Service Continuous Deployment from Gitlab

## Configure a project which should be deployed 
1. Create a ".deployment" file to the root of Git repository with the following content. "project" variable should point to the main project file that needs to be deployed:
  ```
  [config]
  project = Test.API/Test.API.csproj
  ```
_Note: for more options related to this, please check: https://github.com/projectkudu/kudu/wiki/Customizing-deployments_

## Configure App Service to fetch code from your git branch
1. Open app service in Azure Portal
2. Go to "Deployment options"
3. Configure deployment from an external Git repository and your chosen Git branch. Use SSH access URL for configuration (git@...)

## Add permissions for App Service to access your repository in Gitlab
1. Open app service in Azure Portal
2. Go to "Advanced Tools", you will be redirected to an url like this: https://yourappservice.scm.azurewebsites.net
3. Add "/api/sshkey?ensurePublicKey=1" at the end of the url, so you now are at "https://yourappservice.scm.azurewebsites.net/api/sshkey?ensurePublicKey=1"
4. Copy the SSH key from the output of this URL
5. Go to Gitlab repo > Settings > Repository > Deploy Keys
6. Add a name for your deploy key, e.g. "yourappservice PROD"
7. Paste the SSH key you copied from Azure (without quotes)
8. You can leave "Write access allowed" unchecked, there is no need for it
9. Click "Add key" button

## Set up a trigger that will start deployment as soon as new change in your Git branch is detected
1. Open app service in Azure Portal
2. Go to "Properties"
3. Copy "DEPLOYMENT TRIGGER URL"
4. Go to Gitlab repo > Settings > Integrations
5. Paste the URL from Azure Portal to "URL" field
6. Leave "Secret Token" field empty
7. Select "Push events" trigger
8. Leave "Enable SSL verification" checked
9. Click "Add webhook"

## Verify that automatic deployment is working
1. Open app service in Azure Portal
2. Go to "Deployment options"
3. There you will see a list of all deployment attempts with error messages if there are any issues
4. You will likely see a failed deployment in the list and may need to click "Sync" to initiate a new deployment with newest settings
5. In case clicking "Sync" results in one more failure, follow instructions in error messages
