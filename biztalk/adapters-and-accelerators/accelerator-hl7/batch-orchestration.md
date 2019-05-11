---
title: バッチ処理オーケストレーション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bbc6c257d0df78816f242b534e703c6c306ce14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247491"
---
# <a name="batch-orchestration"></a>バッチ オーケストレーション
Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) のバッチを処理するために使用できるオーケストレーション (BatchOrchestration.dll) を提供します。 このオーケストレーションは、HL7 エンコード (2.X) メッセージや受信確認 (Ack) のバッチを処理できます。 オーケストレーションは、ネイティブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]によって追加されたオーケストレーション[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)](BizTalk エクスプ ローラーでオーケストレーション下に表示) と、BizTalk オーケストレーションのセットに設定します。  
  
 オーケストレーションがバッチのアクティベーション、バッチの終了を操作し、メッセージのバッチ タイマー[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用してバッチを制御します。 またこれは、受信バッチ制御ポートと連携して、オーケストレーション ポート[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]コントロール メッセージのバッチを処理するためにインストールします。  
  
## <a name="see-also"></a>参照  
 [バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [BizTalk Accelerator for HL7 コンポーネント](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)