<!-- This template removes the micro tutorial for a quicker post and removes images for a full template check out the 000-DAY-ARTICLE-LONG-TEMPLATE.MD-->

# [7/100] AZ-303 Azure Storage Security

## Introduction

- I learn how to configure security on storage accounts. 
- How to manage access to blobs and how to setup policy to audit anonymous access.

## Use Case

- Every application needs some kind of storage ex. Web App need to store they assets
- As Solution Architect I should know how to secure infrastructure and how to monitor access to resources.

## Cloud Research

- Be default Storage Accounts allow public access to resources but containers are by default set to private only.

> The AllowBlobPublicAccess property is not set by default and does not return a value until you explicitly set it. The storage account permits public access when the property value is null or when it is true.

- To manage access we can use Portal, CLI or REST.
- To properly manage access we can use SAS tokens together with Policies on container level

### Helpful PowerShell script
This script helps to verify status of blob container
```
$url = "<absolute-url-to-blob>"
$downloadTo = "<file-path-for-download>"
Invoke-WebRequest -Uri $url -OutFile $downloadTo -ErrorAction Stop
```

### Azure Policy
This policy allow to audit if any storage account has enabled public access.
```
{
  "if": {
    "allOf": [
      {
        "field": "type",
        "equals": "Microsoft.Storage/storageAccounts"
      },
      {
        "not": {
          "field":"Microsoft.Storage/storageAccounts/allowBlobPublicAccess",
          "equals": "false"
        }
      }
    ]
  },
  "then": {
    "effect": "audit"
  }
}
```



## Social Proof

[Twitter](https://twitter.com/maciejgos/status/1302287071311286274)