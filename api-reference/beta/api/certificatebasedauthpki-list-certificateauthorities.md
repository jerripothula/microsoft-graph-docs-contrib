---
title: "List certificateAuthorityDetail objects"
description: "Get a list of the certificateAuthorityDetail objects and their properties."
author: "suawat"
ms.localizationpriority: medium
ms.subservice: "entra-sign-in"
doc_type: apiPageType
---

# List certificateAuthorityDetail objects

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [certificateAuthorityDetail](../resources/certificateauthoritydetail.md) objects and their properties.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "certificatebasedauthpki_list_certificateauthorities" } -->
[!INCLUDE [permissions-table](../includes/permissions/certificatebasedauthpki-list-certificateauthorities-permissions.md)]

[!INCLUDE [rbac-cert-based-authpkis-apis](../includes/rbac-for-apis/rbac-cert-based-authpkis-apis.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /directory/publicKeyInfrastructure/certificateBasedAuthConfigurations/{certificateBasedAuthPkiId}/certificateAuthorities
```

## Optional query parameters

This method supports the `$filter` (`eq`, `startswith`), `$top`, `$orderby`, and `$count` OData query parameters to help customize the response. For `$top`, the default page size is 100 and max is 999. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required. Learn more about [authentication and authorization](/graph/auth/auth-concepts).|

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [certificateAuthorityDetail](../resources/certificateauthoritydetail.md) objects in the response body.

## Examples

### Request

The following example shows a request.
<!-- {
  "blockType": "request",
  "name": "list_certificateauthoritydetail"
}
-->
``` http
GET https://graph.microsoft.com/beta/directory/publicKeyInfrastructure/certificateBasedAuthConfigurations/{certificateBasedAuthPkiId}/certificateAuthorities
```


### Response

The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.certificateAuthorityDetail)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.certificateAuthorityDetail",
      "id": "90777c92-2eb3-4a68-931d-4a3e1e1c741f",
      "deletedDateTime": null,
      "certificateAuthorityType": "root",
      "certificate": "Binary",
      "displayName": "Contoso2 CA1",
      "issuer": "Contoso2",
      "issuerSubjectKeyIdentifier": "C0E9....711A",
      "createdDateTime": "2024-10-25T18:05:28Z",
      "expirationDateTime": "2027-08-29T02:05:57Z",
      "thumbprint": "C6FA....4E9CF2",
      "certificateRevocationListUrl": null,
      "deltacertificateRevocationListUrl": null,
      "isIssuerHintEnabled": true
    }
  ]
}
```

