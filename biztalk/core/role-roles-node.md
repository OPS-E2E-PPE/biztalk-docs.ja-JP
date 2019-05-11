---
title: Role (Roles ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Role node [binding file]
ms.assetid: dfe2a579-7090-4d85-87e5-d627598c4ee8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 652702d35eb0ab1f9fd974491e5ae94e2a1cec4f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254706"
---
# <a name="role-roles-node"></a>Role (Roles ノード)
バインド ファイルの Roles ノードの Role ノードは、バインド ファイルと共にエクスポートされるサービスにバインドされているロールに関する情報を指定します。  
  
## <a name="nodes-in-the-role-node"></a>Role ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|ロールの名前を指定します。|任意|既定値: 空|  
|RoleLinkTypeName|属性|xs:string|ロールに関連付けられているロール リンクの種類の名前を指定します|任意|既定値: 空|  
|RoleType|属性|RoleRefType (SimpleType)|ロールに関連付けられているロールの種類を指定します。|必須|既定値: なし<br /><br /> 有効な値は次のとおりです。<br /><br /> -不明<br />実装<br />-使用します。|  
|[Enlisted Parties](../core/enlisted-parties-role-node.md)|レコード|ArrayOfEnlistedParty (ComplexType)|このロールにバインドされた参加しているパーティのコンテナー ノードです。|任意|既定値: なし|