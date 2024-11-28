# Supplementary Info

## Keyring Interface
The keyring entry is stored with an account name of "MicrosoftGraph.nocae", a label of "MsalClientId", and a service name of "Microsoft.Developer.IdentityService". Precise naming for these attributes is dependent on the relevant keyring implementation, but here I'm using terms from the MacOS Keyring.
Relevant code defining the keyring attribute naming is [here](https://github.com/microsoftgraph/msgraph-cli-core/blob/1b99121285f098c764a46422e3e1d26c55670f22/src/Microsoft.Graph.Cli.Core/IO/AuthenticationCacheManager.cs#L214).

## Cache Format
An example cache entry following authentication to Microsoft Azure PowerShell (client_id=1950a258-227b-4e31-a9cf-717495945fc2). 
```
{
    "AccessToken": {
      "<user_id>.<tenant_id>-login.windows.net-accesstoken-1950a258-227b-4e31-a9cf-717495945fc2-<tenant_id>-email openid profile https://graph.microsoft.com/auditlog.read.all https://graph.microsoft.com/directory.accessasuser.all https://graph.microsoft.com/.default": {
        "home_account_id": "<user_id>.<tenant_id>",
        "environment": "login.windows.net",
        "client_info": "<client_info>",
        "client_id": "1950a258-227b-4e31-a9cf-717495945fc2",
        "secret": "<secret>",
        "credential_type": "AccessToken",
        "realm": "<tenant_id>",
        "target": "email openid profile https://graph.microsoft.com/AuditLog.Read.All https://graph.microsoft.com/Directory.AccessAsUser.All https://graph.microsoft.com/.default",
        "cached_at": "1729375198",
        "expires_on": "1729379268",
        "extended_expires_on": "1729379268",
        "ext_expires_on": "1729379268"
      }
    },
    "RefreshToken": {
      "<user_id>.<tenant_id>-login.windows.net-refreshtoken-1--": {
        "home_account_id": "<user_id>.<tenant_id>",
        "environment": "login.windows.net",
        "client_info": "<client_info>",
        "client_id": "1950a258-227b-4e31-a9cf-717495945fc2",
        "secret": "<secret>",
        "credential_type": "RefreshToken",
        "family_id": "1"
      }
    },
    "IdToken": {
      "<user_id>.<tenant_id>-login.windows.net-idtoken-1950a258-227b-4e31-a9cf-717495945fc2-<tenant_id>-": {
        "home_account_id": "<user_id>.<tenant_id>",
        "environment": "login.windows.net",
        "client_info": "<client_info>",
        "client_id": "1950a258-227b-4e31-a9cf-717495945fc2",
        "secret": "<secret>",
        "credential_type": "IdToken",
        "realm": "<tenant_id>"
      }
    },
    "Account": {
      "<user_id>-<tenant_id>-login.windows.net-<tenant_id>": {
        "home_account_id": "<user_id>.<tenant_id>",
        "environment": "login.windows.net",
        "client_info": "<client_info>",
        "username": "<username>",
        "name": "<display_name>",
        "local_account_id": "<user_id>",
        "authority_type": "MSSTS",
        "realm": "<tenant_id>"
      }
    },
    "AppMetadata": {
      "appmetadata-login.windows.net-1950a258-227b-4e31-a9cf-717495945fc2": {
        "environment": "login.windows.net",
        "client_id": "1950a258-227b-4e31-a9cf-717495945fc2",
        "family_id": "1"
      }
    }
}
```