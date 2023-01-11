## [Action Fails after Login via Az module](https://github.com/Azure/powershell/issues/73)

Action demonstrating the issue:
[![Fail-AzurePowerShellLoginWithScript](https://github.com/ptsouk/AzurePowerShellLoginSample/actions/workflows/Fail-AzurePowerShellLoginWithScript.yml/badge.svg)](https://github.com/ptsouk/AzurePowerShellLoginSample/actions/workflows/Fail-AzurePowerShellLoginWithScript.yml)

Workaround:
[![Success-AzurePowerShellLoginWithScript](https://github.com/ptsouk/AzurePowerShellLoginSample/actions/workflows/Success-AzurePowerShellLoginWithScript.yml/badge.svg)](https://github.com/ptsouk/AzurePowerShellLoginSample/actions/workflows/Success-AzurePowerShellLoginWithScript.yml)

[Configure a service principal with a secret](https://github.com/Azure/login#configure-a-service-principal-with-a-secret)

    `az ad sp create-for-rbac --name "myApp" --role contributor \
                            --scopes /subscriptions/{subscription-id}/resourceGroups/{resource-group} \
                            --sdk-auth`

## Contents of `${{secrets.AZURE_CREDENTIALS}}`

    {
      "clientId": "***",
      "clientSecret": "***",
      "subscriptionId": "***",
      "tenantId": "***",
      "activeDirectoryEndpointUrl": "https://login.microsoftonline.com",
      "resourceManagerEndpointUrl": "https://management.azure.com/",
      "activeDirectoryGraphResourceId": "https://graph.windows.net/",
      "sqlManagementEndpointUrl": "https://management.core.windows.net:8443/",
      "galleryEndpointUrl": "https://gallery.azure.com/",
      "managementEndpointUrl": "https://management.core.windows.net/"
    }
