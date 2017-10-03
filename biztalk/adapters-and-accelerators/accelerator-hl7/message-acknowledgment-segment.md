---
title: "メッセージの受信確認セグメントが |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- segments, acknowledgements
- acknowledgements, segments
ms.assetid: 6f2b9f6f-a328-4a0f-9e7d-edba32cc045a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9547b6d8ddf3013facd94930b5d91ec42db0e5d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-acknowledgment-segment"></a>メッセージ受信確認セグメント
確認 (ACK) メッセージのメッセージ受信確認 (MSA) セグメントでは、ACK の受信確認は、システムが送信を示し、どのようなメッセージの受信確認の種類を識別します。 2 つの必須セグメントで構成されます。 受信確認コードとメッセージのコントロール id。  
  
## <a name="acknowledgment-code-msa1"></a>受信確認コード: MSA1  
 次の表は、メッセージ受信の結果を示す MSA1 の使用可能なフィールド値を一覧表示します。  
  
|値|意味|Description|  
|-----------|-------------|-----------------|  
|AA|アプリケーションの受信確認|システムがメッセージを受信してを問題なく処理します。|  
|AE|アプリケーション エラー|受信アプリケーション メッセージまたはその構造に関連する処理の問題が発生しました。 送信側システムは、診断し、メッセージの再送を試行する前に問題を解決する必要があります。|  
|AR|アプリケーションの拒否|MSH9 の値に関連する受信場所で、いずれかの問題が発生しました (メッセージの種類)、MSH11 (ID の処理)、または MSH12 (バージョン ID)、その場合、送信側システムは診断し、メッセージを再送信する前に、問題が解決する必要がありますまたは、受信側システムをメッセージまたは送信側システムのケースがメッセージに変更なしの適切な時間が経過したらメッセージを再送する必要があります、その構造に関連した問題が発生しました。|  
  
## <a name="message-control-id-msa2"></a>コントロールのメッセージ ID (MSA2)  
 MSA2 フィールドでは、ACK の受信確認メッセージを識別します。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、受信確認モードに応じて MSA2 で値が生成されます。 この値は、メッセージを送信側と受信側アプリケーションを有効にし、受信確認を同期します。 次の表は、MSA2 フィールドの使用可能な値を一覧表示します。  
  
|受信確認モード|MSA2 内の値|  
|-------------------------|-------------------|  
|元のモード|転置結果の値、MSH10 内の値の (コントロールの ID をメッセージ)、元のメッセージのフィールド|  
|拡張モード: コミットの確認|転置結果の値、MSH10 内の値の (コントロールの ID をメッセージ)、元のメッセージのフィールド|  
|アプリケーションの受信確認を強化モード:|によって生成された GUID[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信確認の場合|  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK メッセージ スキーマの種類](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [Ack を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [受信確認エラー条件](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)