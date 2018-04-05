---
title: OutboundTransforms (ReceivePort ノード) |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- OutboundTransforms node [binding file]
ms.assetid: 6deea062-4eb0-47ed-869c-ed6ec9290ea7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc6fa0bc804fad0d0ddea79614c392769452f1c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="outboundtransforms-receiveport-node"></a>OutboundTransforms (ReceivePort ノード)
バインド ファイルの ReceivePort ノードの OutboundTransforms ノードには、バインド ファイルと共にエクスポートされる双方向受信ポートの送信変換のコレクションが含まれます。  
  
## <a name="nodes-in-the-outboundtransforms-node"></a>OutboundTransforms ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノード型**|**データ型**|**Description**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[Transform (OutboundTransforms ノード)](../core/transform-outboundtransforms-node.md)|レコード|Transform (ComplexType)|BizTalk Server マップまたは変換を指定します。これは送信元スキーマと送信先スキーマのマッピングを表す項目です。|任意|既定値: なし|