![](https://img.shields.io/badge/Certification%20Level-Community-28A745?link=https://github.com/cyberark/community/blob/master/Conjur/conventions/certification-levels.md) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# BlobHunter

A tool for scanning Azure blob storage accounts for publicly opened blobs.  
BlobHunter is a part of  "Hunting Blobs For Fun And Glory" research: {TODO: add here link to blog-post.}

## Overview

BlobHunter helps you identify Azure blob storage containers which stored files that are publicly opened to everyone over the internet.  
It can help you check for poorly configured containers storing sensitive data.  
This can be helpful on large Azure subscriptions where there are lots of storage accounts that could be hard to track.  
BlobHunter produces an informative csv result file with important details on each publicly opened container in the scanned environment.

## Requirements

1. Python 3+

2. Azure CLI

3. [`requirements.txt`](requirements.txt) packages

4. Azure user with one of the following [built-in roles](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles):

   -	[Contributor](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#contributor)
   -	[Owner](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#owner)
   -	[Avere Contributor](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#avere-contributor)
   -	[Storage Account Contributor](https://docs.microsoft.com/en-us/azure/role-based-access-control/built-in-roles#storage-account-contributor)
   
   Or any Azure user with a role that allows to perform the following Azure actions:
   
   ```
   Microsoft.Resources/subscriptions/read
   Microsoft.Resources/subscriptions/resourceGroups/read
   Microsoft.Storage/storageAccounts/read
   Microsoft.Storage/storageAccounts/listkeys/action
   Microsoft.Storage/storageAccounts/blobServices/containers/read
   Microsoft.Storage/storageAccounts/blobServices/containers/blobs/read
   ```

## Build

#### Example for installation on Ubuntu:

```bash
curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
```

```bash
pip3 install -r requirements.txt
```

## Usage 

Simply run 

```
python3 BlobHunter.py
```

If you are not logged in in the Azure CLI, a browser window will be prompted at you for inserting your Azure user credentials.

#### Demo

TODO: add here the demo video :)

## References

For any question, please contact [DanielNiv](https://github.com/DanielNiv) and CyberArk Labs.

## Certification level

This repo is a **Community** level project. It's a community contributed project that **is not reviewed or supported  
by CyberArk**. For more detailed information on our certification levels, see [our community guidelines](https://github.com/cyberark/community/blob/master/Conjur/conventions/certification-levels.md#community).

## License

Copyright (c) 2021 CyberArk Software Ltd. All rights reserved. 
Licensed under the MIT License.  
For the full license text see [`LICENSE`](LICENSE).

