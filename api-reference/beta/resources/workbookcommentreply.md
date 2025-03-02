---
title: "workbookCommentReply resource type"
description: "Definition of workbookCommentReply resource type"
ms.localizationpriority: medium
author: "grangeryy"
ms.subservice: "excel"
doc_type: "resourcePageType"
toc.title: Comment reply
---

# workbookCommentReply resource type

Namespace: microsoft.graph

Represents a reply to an excel comment.

## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [List replies](../api/workbookcomment-list-replies.md) | [workbookCommentReply](workbookcommentreply.md) collection | Retrieve a list of workbookcommentreply objects. |
| [Get reply](../api/workbookcommentreply-get.md) | [workbookCommentReply](workbookcommentreply.md) | Read properties and relationships of workbookCommentReply object. |
| [Create reply](../api/workbookcomment-post-replies.md) | [workbookCommentReply](workbookcommentreply.md) | Create a new workbookCommentReply. |

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|content|String|The content of replied comment.|
|contentType|String|Indicates the type for the replied comment.|
|id|String|Represents the comment identifier. Read-only.|

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|task|[workbookDocumentTask](workbookdocumenttask.md)|The task associated with the comment thread.|

## JSON representation

The following JSON representation shows the resource type.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.workbookCommentReply",
  "keyProperty": "id"
}-->

```json
{
  "content": "String",
  "contentType": "String",
  "id": "String (identifier)"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "workbookCommentReply resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


