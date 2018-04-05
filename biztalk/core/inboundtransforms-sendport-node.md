---
title: InboundTransforms (SendPort ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- InboundTransforms node [binding file]
ms.assetid: 5ed239b9-13d8-4099-b779-08f589a722e9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03567b5ea6095e38370260e1f17055ab40da4d6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="inboundtransforms-sendport-node"></a>InboundTransforms (SendPort ノード)
バインド ファイルの SendPort ノードの InboundTransforms ノードには、バインド ファイルと共にエクスポートされる双方向送信ポートの受信変換のコレクションが含まれています。  
  
## <a name="nodes-in-the-inboundtransforms-node"></a>InboundTransforms ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[Transform (InboundTransforms ノード)](../core/transform-inboundtransforms-node.md)|レコード|Transform (ComplexType)|BizTalk Server マップまたは変換を指定します。これは送信元スキーマと送信先スキーマのマッピングを表す項目です。|任意|既定値: なし|