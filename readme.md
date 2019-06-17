# Recovery Service Vault

## Introduction

This template is used to create [Recovery Service Vaults](<https://docs.microsoft.com/en-us/azure/templates/microsoft.recoveryservices/2016-06-01/vaults>)

## Security Controls

The following security controls can be met through configuration of this template:

* [Backups](documentation/backup.md): CP-9.a, CP-9.b, CP-9 (5)

## Dependancies

The following items are assumed to exist already in the deployment:

* * [Resource Group](<https://github.com/canada-ca-azure-templates/resourcegroups>)

## Parameter format

```JSON
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "parameters": {
        "backupVaultName": {
            "value": "backup-sbx-vault"
        },
        "backupVaultRGName": {
            "value": "backups-sbx-rg"
        }
    }
}
```

## Parameter Values

### Main Template

|Name        |Type   |Required |Value                               |
|------------|-------|---------|------------------------------------|
|backupVaultName |string |Yes      |The name of the recovery serice vault |
|backupVaultRGName |string |Yes      |The name of the resource group to place the vault in  |

## Additional Notes

In the vault properties you need to upgrade the vm backup stack to v2 to support SSD and drives larger than 4TB.  

## History

|Date       |Release| Change                |
|-----------|-------|-----------------------|
| 20190516 | [20190516](https://github.com/canada-ca-azure-templates/recovery-service-vault/tree/20190516) | Created test validation.                                   |
| 20190617 | [20190617](https://github.com/canada-ca-azure-templates/recovery-service-vault/tree/20190617) | Support for passing in a [unique] tag in the name that will be replaced.                                   |