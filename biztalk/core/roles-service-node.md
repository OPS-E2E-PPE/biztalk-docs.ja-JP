---
title: Roles (Service ノード) |Microsoft ドキュメント
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
ms.openlocfilehash: b47f5ae94326b0555c0c9cd84752cb9f1c409daa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268402"
---
# <a name="roles-service-node"></a>Roles (Service ノード)
バインド ファイルの Roles ノードは、そのバインド ファイルと共にエクスポートされるサービスにバインドされている各ロールに関する情報を提供するすべての Role ノードの親ノードです。  
  
## <a name="nodes-in-the-roles-node"></a>Roles ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[ロール](../core/role-roles-node.md)|レコード|RoleRef (ComplexType)|バインド ファイルと共にエクスポートされるサービスにバインドされたロールに関する情報を指定します。|任意|既定値: なし|