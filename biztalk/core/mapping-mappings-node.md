---
title: Mapping (Mappings ノード) |Microsoft ドキュメント
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
ms.openlocfilehash: b2c62d46e4d5c2b73eee5094ecda0e20c039798a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mapping-mappings-node"></a>Mapping (Mappings ノード)
バインド ファイルの Mapping ノードでは、参加しているパーティのパーティ ポートとロール ポートの操作の間のマッピングを記述します。  
  
## <a name="nodes-in-the-mapping-node"></a>Mapping ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|PortTypeName|属性|xs:string|ポートの種類の名前を指定します。|任意|既定値: 空|  
|OperationName|属性|xs:string|このポートの種類に属する操作を指定します。|任意|既定値: 空|  
|[SendPortRef](../core/sendportref-mapping-node.md)|レコード|SendPortRef (ComplexType)|マッピングに関連付けられている送信ポートの一覧のコンテナー ノードです。|任意|既定値: なし|