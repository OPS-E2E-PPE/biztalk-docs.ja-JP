---
title: "静的な受信確認 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- static acknowledgements
- acknowledgements, static acknowledgements
ms.assetid: 1cdd01fc-1dae-4851-917f-4f13a0f9595a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8081dc0f3c37c40cb1103567ae06f80037a12730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="static-acknowledgments"></a>静的な受信確認
BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 元、強化された、遅延、および静的な受信確認 (ACK) モードをサポートします。 パーティの静的 ACK モードを選択するかどうかは[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を成功または失敗を示す値だけを含む静的 Ack が生成されます。 静的 ACK がエラー値で構成し、受信側のシステムが受信され、成功した場合に、メッセージを処理するかどうかを示す[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
 元に強化され、遅延モードの場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]動的 Ack が生成されます。 HL7 でエンコードされたされ MSA.1 受信確認コード フィールドであり、ERR セグメントなどのフィールドが含まれています。 動的 ACK の MSA.1 フィールドが示されますかどうか、エラー条件を拒否するか、別の処理が発生するエラー (を参照してください[メッセージ受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md))。 ERR セグメントは、エラーに関する詳細情報を提供します。 静的 Ack は、このような情報を提供されません。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]動的受信を異なる静的 ACK を処理します。 (これは、ACK を受信した後、次のメッセージが送信のみされます)、双方向の送信ポートを受信した場合、静的 ACK ACK 失敗を示します (または有効 ACK ではありません)、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]はセカンダリ トランスポートに移動するか、メッセージを中断します。 エラー状態に応じて、動的 ACK を受信した場合と同様、メッセージは再試行されません。  
  
 ときに、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]書き込みますパーサーでは、静的な確認を処理する、 **IsStaticAck**メッセージ コンテキストにブール型プロパティです。 シリアライザーでは、この値を使用して、静的な確認メッセージを処理するかどうかを決定  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [メッセージ受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)