---
title: Enlisted Party (Enlisted Parties ノード) |Microsoft Docs
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
ms.openlocfilehash: 034cc538bb358f887cda761bb0cf6a0d9d1116e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389075"
---
# <a name="enlisted-party-enlisted-parties-node"></a>Enlisted Party (Enlisted Parties ノード)
バインド ファイルの Enlisted Party ノードには、バインド ファイルと共にエクスポートされるロールに関連付けられた参加しているパーティに関する特定の情報が含まれています。  
  
## <a name="nodes-in-the-enlisted-party-node"></a>Enlisted Party ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|名前|属性|xs:string|参加しているパーティの名前を指定します|任意|既定値: 空|  
|[マッピング](../core/mappings-enlisted-party-node.md)|レコード|ArrayOfEnlistedPartyMapping (ComplexType)|パーティ ポートとロール ポートの種類の操作間のマッピングのコンテナー ノードです。|任意|既定値: なし|