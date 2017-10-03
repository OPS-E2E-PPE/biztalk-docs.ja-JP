---
title: "オーケストレーションがバッチ処理 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, acknowledgements
- acknowledgements, batching
- batch orchestration
- orchestrations, batch orchestration
- messages, batching
- batching, batch orchestration
- batching, messages
ms.assetid: b449d8d5-72a2-46c8-a2b1-380431175f4d
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9db6ee8b4fd3dec8e2902642634b701889866cf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="batch-orchestration"></a>バッチ オーケストレーション
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) バッチの処理に使用できるオーケストレーション (BatchOrchestration.dll) を提供します。 このオーケストレーションは、HL7 エンコード (2.X) メッセージや受信確認 (Ack) のバッチを処理できます。 オーケストレーションは、ネイティブな[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]によって追加されたオーケストレーション[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](BizTalk エクスプ ローラーでオーケストレーション下に表示) と、BizTalk オーケストレーションのセットに設定します。  
  
 オーケストレーションはバッチのアクティベーション、バッチの終了で動作し、メッセージのバッチ タイマー[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を使用してバッチを制御します。 オーケストレーションがバッチ コントロール ポート、受信のでもポート[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コントロール メッセージのバッチを処理するインストールします。  
  
## <a name="see-also"></a>参照  
 [バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)