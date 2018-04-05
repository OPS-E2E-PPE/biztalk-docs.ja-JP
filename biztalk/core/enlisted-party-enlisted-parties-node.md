---
title: Enlisted Party (Enlisted Parties ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enlisted Parties node [binding file]
ms.assetid: 2ff7b563-17c5-48e9-b33e-62c821188448
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 624f74d3b49b80e8000723c3f7451c52b37c8d3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enlisted-party-enlisted-parties-node"></a>Enlisted Party (Enlisted Parties ノード)
バインド ファイルの Enlisted Party ノードには、バインド ファイルと共にエクスポートされるロールに関連付けられた参加しているパーティに関する情報が含まれます。  
  
## <a name="nodes-in-the-enlisted-party-node"></a>Enlisted Party ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|参加しているパーティの名前を指定します。|任意|既定値: 空|  
|[マッピング](../core/mappings-enlisted-party-node.md)|レコード|ArrayOfEnlistedPartyMapping (ComplexType)|パーティ ポートとロール ポートの種類の操作の間のマッピングのコンテナー ノードです。|任意|既定値: なし|