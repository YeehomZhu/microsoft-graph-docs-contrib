---
title: "Update cloudPcProvisioningPolicy"
description: "Update the properties of a cloudPcProvisioningPolicy object."
author: "AshleyYangSZ"
ms.localizationpriority: medium
ms.subservice: "cloud-pc"
doc_type: apiPageType
---

# Update cloudPcProvisioningPolicy

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) object.

[!INCLUDE [national-cloud-support](../../includes/global-us.md)]

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "cloudpcprovisioningpolicy_update" } -->
[!INCLUDE [permissions-table](../includes/permissions/cloudpcprovisioningpolicy-update-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
PATCH /deviceManagement/virtualEndpoint/provisioningPolicies/{id}
```

## Request headers

| Name          | Description                |
| :------------ | :------------------------  |
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|
| Content-Type  | application/json. Required.|

## Request body

In the request body, supply a JSON representation of the [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md) object.

The following table shows the properties that can be updated for the [cloudPcProvisioningPolicy](../resources/cloudpcprovisioningpolicy.md).

|Property|Type|Description|
|:---|:---|:---|
|autopatch|[cloudPcProvisioningPolicyAutopatch](../resources/cloudpcprovisioningpolicyautopatch.md)|The specific settings for Windows Autopatch that enable its customers to experience it on Cloud PC. The settings take effect when the tenant enrolls in Windows Autopatch and the **managedType** of the **microsoftManagedDesktop** property is set as `starterManaged`.|
|description|String|The provisioning policy description.|
|displayName|String|The display name for the provisioning policy. |
|domainJoinConfigurations|[cloudPcDomainJoinConfiguration](../resources/cloudpcdomainjoinconfiguration.md) collection|Specifies a list ordered by priority on how Cloud PCs join Microsoft Entra ID.|
|enableSingleSignOn|Boolean|`True` if the provisioned Cloud PC can be accessed by single sign-on. `False` indicates that the provisioned Cloud PC doesn't support this feature. Default value is `false`. Windows 365 users can use single sign-on to authenticate to Microsoft Entra ID with passwordless options (for example, FIDO keys) to access their Cloud PC. Optional.|
|imageDisplayName|String|The display name for the OS image you're provisioning.|
|imageId|String|The ID of the OS image you want to provision on Cloud PCs. The format for a gallery type image is: {publisher_offer_sku}. Supported values for each of the parameters are as follows: <ul><li>publisher: Microsoftwindowsdesktop.</li> <li>offer: windows-ent-cpc.</li> <li>sku: 21h1-ent-cpc-m365, 21h1-ent-cpc-os, 20h2-ent-cpc-m365, 20h2-ent-cpc-os, 20h1-ent-cpc-m365, 20h1-ent-cpc-os, 19h2-ent-cpc-m365 and 19h2-ent-cpc-os.</li></ul>|
|imageType|cloudPcProvisioningPolicyImageType|The type of OS image (custom or gallery) you want to provision on Cloud PCs. Possible values are: `gallery`, `custom`.|
|microsoftManagedDesktop|[microsoftManagedDesktop](../resources/microsoftmanageddesktop.md)|The specific settings to **microsoftManagedDesktop** that enables Microsoft Managed Desktop customers to get device managed experience for Cloud PC. To enable **microsoftManagedDesktop** to provide more value, an admin needs to specify certain settings in it.|
|windowsSetting|[cloudPcWindowsSettings](../resources/cloudpcwindowssetting.md)|Indicates a specific Windows setting to configure during the creation of Cloud PCs for this provisioning policy. Supports `$select`. |
|domainJoinConfiguration (deprecated)|[cloudPcDomainJoinConfiguration](../resources/cloudpcdomainjoinconfiguration.md)|Specifies how Cloud PCs join Microsoft Entra ID.  The **domainJoinConfiguration** property is deprecated and will stop returning data on May 31, 2024. Going forward, use the **domainJoinConfigurations** property.|
|onPremisesConnectionId (deprecated)|String|The ID of the cloudPcOnPremisesConnection. To ensure that Cloud PCs have network connectivity and that they domain join, choose a connection with a virtual network that’s validated by the Cloud PC service.  The **onPremisesConnectionId** property is deprecated and will stop returning data on May 31, 2024. Going forward, use the **domainJoinConfigurations** property.|
|windowsSettings (deprecated)|[cloudPcWindowsSettings](../resources/cloudpcwindowssettings.md)|Specific Windows settings to configure during the creation of Cloud PCs for this provisioning policy. Supports `$select`. The **windowsSettings** property is deprecated and will stop returning data on January 31, 2024. Going forward, use the **windowsSetting** property.|

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request

The following example shows a request.

<!-- {
  "blockType": "request",
  "name": "update_provisioningpolicy"
}
-->

``` http
PATCH https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/provisioningPolicies/{id}
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.cloudPcProvisioningPolicy",
  "displayName": "HR provisioning policy",
  "description": "Provisioning policy for India HR employees",
  "onPremisesConnectionId": "4e47d0f6-6f77-44f0-8893-c0fe1701ffff",
  "imageId": "Image ID value",
  "imageDisplayName": "Image Display Name value",
  "imageType": "custom",
  "windowsSettings": {
    "language": "en-US"
  },
  "windowsSetting": {
    "locale": "en-US"
  },
  "microsoftManagedDesktop": {
    "managedType": "starterManaged",
    "profile": null
  },
  "autopatch": {
    "autopatchGroupId": "91197a0b-3a74-408d-ba88-bce3fdc4e5eb"
  }
}
```

### Response

The following example shows the response.

<!-- {
  "blockType": "response",
  "truncated": true,
}
-->
``` http
HTTP/1.1 204 No Content
```
