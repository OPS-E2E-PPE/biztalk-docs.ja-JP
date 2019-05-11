---
title: 静的受信確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- static acknowledgements
- acknowledgements, static acknowledgements
ms.assetid: 1cdd01fc-1dae-4851-917f-4f13a0f9595a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c9c310dde71d50dcf49fe4d54e2e5679f899de6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291593"
---
# <a name="static-acknowledgments"></a>静的受信確認
BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 元、強化された、遅延、および静的受信確認 (ACK) モードをサポートします。 パーティの静的 ACK モードを選択するかどうかは[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]の成功または失敗を示す値のみが含まれている静的 Ack が生成されます。 静的、ACK はエラー値で構成し、受信側のシステムが受信され、成功のメッセージを処理するかどうかを示します[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
 元の次のように強化、および遅延モードでは、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]動的 Ack が生成されます。 HL7 エンコードされ、MSA.1 受信確認コード フィールドや、ERR セグメントなどのフィールドを含めます。 動的 ACK の MSA.1 フィールドはエラー状態が、拒否するかエラーが発生するさまざまな処理がかどうかを示します (を参照してください[メッセージ受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md))。 ERR セグメントは、エラーに関する詳細情報を提供します。 静的 Ack はこのような情報を提供します。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 動的な確認のとは異なる静的確認を処理します。 (ACK を受信した後の次のメッセージは送信のみ) を双方向送信ポートを受信した場合、静的 ACK と、確認失敗を示します (または有効な ACK ではありません)、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]はセカンダリ トランスポートに移動するか、メッセージを中断します。 エラーの状態に応じて、動的 ACK を受信した場合と、メッセージは再試行されません。  
  
 ときに、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]書き込みますパーサーでは、静的な確認を処理する、 **IsStaticAck**メッセージ コンテキストにブール型プロパティ。 シリアライザーでは、この値を使用して、静的な確認としてのメッセージを処理するかどうかを判断  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [メッセージ受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)