---
title: "ACK メッセージ モード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 122f0851005c7d8abba6c1739ae86a1d65d89625
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ack-message-modes"></a>ACK メッセージ モード
確認 (ACK) メッセージの[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 受信確認モードおよびを生成する ACK の MSH15 および MSH16 フィールドを設定するために使用する値を決定します。 これらの値は、取引先管理 (TPM) 構成内に存在します。 次の値は、ACK モードの可能な。  
  
> [!NOTE]
>  次の一覧には、HL7 仕様は、1 ~ 3 のアイテムと MSH15 と MSH16 の値が含まれている定められています。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]項目を受信確認を生成されないことを示すために 4 を定義します。  
  
1.  元のヘッダーと本文の検証後に送信された 1 つ確認します。 このモードには、スキーマの検証が含まれます。  
  
2.  拡張 - 2 つの ACK メッセージが送信されます。  
  
    -   ACK – を受け入れる受信側システムでは、ヘッダーの検証後にこの種類の確認を送信します。 この確認は、メッセージがデータベースにコミットされることを発信側アプリケーションに通知します。  
  
    -   アプリケーション ACK の受信側システムでは、ヘッダーおよび本文を含む、完全なメッセージの検証後にこの種類の確認を送信します。  
  
3.  遅延の 2 つの ACK メッセージが送信されます。  
  
    -   元のモード: 受信側システムは、ヘッダーと本文の検証後にこの種類の確認を送信します。 このモードには、スキーマの検証が含まれます。  
  
    -   遅延モード: 処理した後、基幹業務アプリケーションがメッセージを確認します。 アプリケーション メッセージを配信の遅延を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、スタンドアロンのメッセージとして処理され、送信先に配信します。  
  
4.  静的 - 成功した場合に、または送信される ACK エラー発生時にします。  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [ACK プロセス モデル](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)   
 [静的な受信確認](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)