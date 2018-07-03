---
title: メッセージの受信確認セグメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, acknowledgements
- acknowledgements, segments
ms.assetid: 6f2b9f6f-a328-4a0f-9e7d-edba32cc045a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f771968e6d7c7f58ccd8d3e68b43aac0eb64e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968499"
---
# <a name="message-acknowledgment-segment"></a>メッセージの受信確認セグメント
受信確認 (ACK) メッセージのメッセージ受信確認 (MSA) セグメントでは、ACK を受信する、システムが送信を示し、どのようなメッセージの受信確認の種類を識別します。 2 つの必須セグメントで構成されています。 受信確認、コードとメッセージのコントロール id。  

## <a name="acknowledgment-code-msa1"></a>受信確認コード: MSA1  
 次の表では、メッセージの受信の結果を示す MSA1 の使用可能なフィールド値を示します。  

|値|説明|説明|  
|-----------|-------------|-----------------|  
|AA|アプリケーションの受信確認|システムがメッセージを受信してそれを問題なく処理します。|  
|AE|アプリケーション エラー|受信側のアプリケーション メッセージまたはその構造に関連する処理の問題が発生しました。 送信元システムは、診断し、メッセージの再送を試行する前に、問題を修正する必要があります。|  
|AR|アプリケーションの却下|MSH9 の値に関連する受信場所で、いずれかの問題が発生しました (メッセージの種類)、MSH11 (ID を処理)、または MSH12 (バージョン ID) の場合、送信元システムが診断し、メッセージを再送信する前に問題が解決する必要がありますまたは、メッセージや場合、送信元システムがメッセージを変更しなくても、適切な期間の後にメッセージを再送する必要があります、その構造に関連した受信側のシステムで問題が発生しました。|  

## <a name="message-control-id-msa2"></a>メッセージのコントロール ID (MSA2)  
 MSA2 フィールドには、ACK が受信確認メッセージが識別されます。 Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 受信確認のモードに基づいて MSA2 で値が生成されます。 この値は、メッセージを送信側と受信側アプリケーションを有効にし、受信確認を同期します。 次の表では、MSA2 フィールドに使用できる値を示します。  


|            受信確認のモード            |                                                           MSA2 内の値                                                            |
|-------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|               元のモード               |                  転置、MSH10 内の値の値 (コントロールの ID をメッセージ)、元のメッセージのフィールド                   |
|   拡張モード: コミットの確認    |                  転置、MSH10 内の値の値 (コントロールの ID をメッセージ)、元のメッセージのフィールド                   |
| 拡張モード: アプリケーションの受信確認 | によって生成された GUID[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信確認の場合 |

## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK メッセージ スキーマの種類](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [Ack を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [受信確認エラーの条件](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)