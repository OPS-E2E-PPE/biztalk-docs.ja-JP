---
title: ACK メッセージ モード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181617a41ba892a8ac04f2bf2154bbe78e8c892e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967857"
---
# <a name="ack-message-modes"></a>ACK メッセージ モード
確認 (ACK) メッセージ、Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 受信確認モードおよび生成する ACK の MSH15 および MSH16 フィールドを設定するために使用する値を決定します。 これらの値は、取引先管理 (TPM) の構成に存在します。 次の値は ACK モードのことです。  
  
> [!NOTE]
>  次の一覧で、HL7 仕様には、1 ~ 3 のアイテムと MSH15 と MSH16 の値が含まれていることが定められています。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 受信確認を生成しないことを示すために 4 項目を定義します。  
  
1. 元のヘッダーと本文の検証後に送信された 1 つ確認します。 このモードには、スキーマの検証が含まれます。  
  
2. 拡張 - 2 つの ACK メッセージが送信されます。  
  
   -   ACK – を受け入れ、受信側システム ヘッダーの検証後にこの種類の確認を送信します。 この確認は、メッセージがデータベースにコミットである、発信側アプリケーションに通知します。  
  
   -   アプリケーション ACK が受信側システムでは、ヘッダーおよび本文を含む、完全なメッセージの検証後にこの種類の確認を送信します。  
  
3. 遅延された - 2 つの ACK メッセージを送信します。  
  
   - 元のモード: ヘッダーと本文の検証後に、この種類の確認が受信側のシステムに送信します。 このモードには、スキーマの検証が含まれます。  
  
   - 遅延モード: 基幹業務アプリケーションは、処理した後、メッセージを確認します。 アプリケーションに遅延メッセージを配信する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、スタンドアロンのメッセージとして処理することと、変換先に配信します。  
  
4. 静的 - 成功した場合にまたはエラー発生時の確認を送信します。  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [ACK プロセス モデル](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)   
 [静的受信確認](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)