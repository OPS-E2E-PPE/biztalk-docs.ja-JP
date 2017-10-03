---
title: "メッセージの検証 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- validating, acknowledgements
- messages, acknowledgements
- acknowledgements, validating
- validating, messages
- acknowledgements, messages
- messages, validating
ms.assetid: 7dba0f40-5e19-4598-82cb-22c71e9536c6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1edaffcab50d6a8af508cb16c9eede39c5ddb952
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="validating-messages"></a>メッセージの検証
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) アプリケーションから受信メッセージの受信確認 (ACK) の送信または取引先、HL7 への変換が必要な HL7 XML 受信確認の形式でのサポートは ACK メッセージをエンコードします。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]通常、関連する受信 (取引先形式) ドキュメントの仕様に対して受信メッセージを確認した後は、受信確認を生成します。 すべてのセグメントは、検証を渡すときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]をアプリケーションに同意を示す受信確認を返します。 それ以外の場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エラーか失敗か拒否を示す確認メッセージが生成されます。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK 伝送 HL7 標準に対する構文とスキーマのエラーが報告されました。 検証が失敗した場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]ドキュメントを保留中のメッセージ キューに配置し、却下の詳細を示す受信確認を返します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサーは、データ型、構文、およびスキーマの検証チェックを含む検証を実行します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信場所の詳細と共にを解析中に発生したスキーマ エラーを記録します。  
  
 時間を構成、作成する必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] ACK を応答に必要な成果物 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーサーは、HL7 正規 ACK XML インスタンスを作成します。 BizTalk では、これを適切な BizTalk マップで必要なバージョンの形式に変換および変換先の形式を検証します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]シリアライザーは、HL7 でエンコードされたインスタンスにメッセージを変換します。  
  
> [!NOTE]
>  受信メッセージの区切り記号の間に競合があるしで指定された場合、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成し、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]受信メッセージの同じ区切り記号を使用し、構成を上書き ACK メッセージが生成されます設定。  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [ACK メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)