---
title: OutboundTransforms (ReceivePort ノード) |Microsoft Docs
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
ms.openlocfilehash: 109995aa38731338ce53d4dea58226fa081fd17a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393422"
---
# <a name="outboundtransforms-receiveport-node"></a>OutboundTransforms (ReceivePort ノード)
バインド ファイルの ReceivePort ノードの OutboundTransforms ノードには、出力方向のコレクションが含まれています。 双方向の変換は、バインド ファイルと共にエクスポートされるポートを受信します。  
  
## <a name="nodes-in-the-outboundtransforms-node"></a>OutboundTransforms ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[Transform (OutboundTransforms ノード)](../core/transform-outboundtransforms-node.md)|レコード|変換 (ComplexType)|BizTalk Server マップまたは変換で、送信元スキーマと送信先スキーマ間のマッピングを表す項目を指定します。|任意|既定値: なし|