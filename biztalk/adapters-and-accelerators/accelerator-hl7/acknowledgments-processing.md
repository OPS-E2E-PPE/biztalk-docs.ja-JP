---
title: 受信確認の処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, processing
ms.assetid: 705bc12d-69ac-4641-a45e-4f1fab507e4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b726eb4698eaa9887703d7df01dc0f6cadf5eefc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgments-processing"></a>受信確認の処理
HL7 仕様では、2 つの形式でメッセージの交換をサポートします。  
  
-   要請されていない更新プログラムとその確認 (ACK)  
  
-   クエリとその応答  
  
 発信側アプリケーションからメッセージに応答して、応答側のアプリケーションはデータや、エラーを示す値を含むメッセージに応答します。 発信側アプリケーションは、応答側のアプリケーションを受信しなかったこと、メッセージ正常を示す応答側アプリケーションから却下ステータスを受信する可能性があります。 どちらの場合は、メッセージ交換処理には、2 つのエンティティ、発信側と応答側のアプリケーションが含まれます。 各は送信者とメッセージの受信先の両方です。 発信側アプリケーションでは、最初に送信し、受信、応答のシステムの受信、送信中。  
  
## <a name="unsolicited-updates"></a>要請されていない更新プログラム  
 要請されていない更新プログラムは、基幹業務 (LOB) アプリケーション、メッセージを公開するか、トリガー イベントが発生したときに情報の転送を開始するときに発生します。 たとえば、患者の実験の結果が使用できる場合は、ある可能性がありますテスト結果を他のいくつかのシステムに送信する必要があります。 これらは、要請されていない更新プログラムの ACK が応答します。  
  
## <a name="queries"></a>クエリ  
 クエリの場合は、情報を必要とするアプリケーションでは、別のアプリケーションにクエリを送信し、受信側のアプリケーションがクエリに応答します。 やなどの薬局アプリケーション可能性があります、注文エントリ (組織) のシステムの患者の ID 番号を含む要求メッセージの送信、注文に関する処理を許可するように必要なデータを含む応答を受信します。 この要求を行ったトランザクションは、クエリであり、要請されていない更新プログラムとは異なる。 2 つのアプリケーション間をフローする情報は、応答に含まれます。 応答には、4 番目のメッセージの受信確認は不要です。 ただし、ACK で応答する一部の環境で変更することができます。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ように構成されている場合は、ACK で応答します。 クエリ/応答のやり取りの例は、次を参照してください。 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [メッセージの検証](../../adapters-and-accelerators/accelerator-hl7/validating-messages.md)  
  
-   [ACK メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)  
  
-   [ACK プロセス モデル](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)