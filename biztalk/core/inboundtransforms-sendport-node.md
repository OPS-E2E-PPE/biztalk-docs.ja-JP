---
title: InboundTransforms (SendPort ノード) |Microsoft Docs
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
ms.openlocfilehash: 59d13d48da9f4b9e3e04cb0753eb302484b6b169
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382183"
---
# <a name="inboundtransforms-sendport-node"></a>InboundTransforms (SendPort ノード)
バインド ファイルの SendPort ノードの InboundTransforms ノードには、バインド ファイルと共にエクスポートされる双方向送信ポートの受信変換のコレクションが含まれています。  
  
## <a name="nodes-in-the-inboundtransforms-node"></a>InboundTransforms ノード内のノード  
 次の表に、バインド ファイルのこのノードに設定できるプロパティを示します。  
  
|**名前**|**ノードの種類**|**[データ型]**|**[説明]**|**制限**|**コメント**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[Transform (InboundTransforms ノード)](../core/transform-inboundtransforms-node.md)|レコード|変換 (ComplexType)|BizTalk Server マップまたは変換で、送信元スキーマと送信先スキーマ間のマッピングを表す項目を指定します。|任意|既定値: なし|