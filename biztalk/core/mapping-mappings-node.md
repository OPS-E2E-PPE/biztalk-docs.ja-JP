---
title: Mapping (Mappings ノード) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Mapping node [binding file]
ms.assetid: bc54c476-505c-4020-b7df-1d19f86329aa
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e227dd0c22734e0d448aebc0bbf4a8960575a5e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325666"
---
# <a name="mapping-mappings-node"></a>Mapping (Mappings ノード)
バインド ファイルの Mapping ノードでは、パーティのポートとロール ポートの種類操作に参加しているパーティ間のマッピングについて説明します。  
  
## <a name="nodes-in-the-mapping-node"></a>Mapping ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|PortTypeName|属性|xs:string|ポートの種類の名前を指定します。|任意|既定値: 空|  
|OperationName|属性|xs:string|このポートの種類に属する操作を指定します。|任意|既定値: 空|  
|[SendPortRef](../core/sendportref-mapping-node.md)|レコード|SendPortRef (ComplexType)|マッピングに関連付けられている送信ポートの一覧のコンテナー ノードです。|任意|既定値: なし|