---
title: (Service ノード) の役割 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Roles node [binding file]
ms.assetid: 847755c9-1697-41a0-b870-f9e795a1a2a6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ff156bce1fa4114aac34641ce52d28cdf182ecd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240403"
---
# <a name="roles-service-node"></a>Roles (Service ノード)
バインド ファイルの Roles ノードは、すべては、バインド ファイルと共にエクスポートされるサービスにバインドされている各ロールに関する情報を提供するロール ノードの親ノードです。  
  
## <a name="nodes-in-the-roles-node"></a>[ロール] ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[ロール](../core/role-roles-node.md)|レコード|RoleRef (ComplexType)|バインド ファイルと共にエクスポートされるサービスにバインドされているロールに関する情報を指定します。|任意|既定値: なし|