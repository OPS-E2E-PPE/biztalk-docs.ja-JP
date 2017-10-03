---
title: "パート 1: 断片化した受信バッチ シナリオ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- batching tutorial, fragmenting messages
- fragmenting messages
ms.assetid: 8adf2c17-5f66-408d-b30b-51b22d8e71fa
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8891bd09c803c77e1878b304f5db5b71a26ab9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a>パート 1: 断片化した受信バッチのシナリオ
このチュートリアルには、個別のメッセージにフラグメント、および、先に個々 のメッセージを送信、HL7 でエンコードされたバッチを受信します。 次の図は、このプロセスの流れを示しています。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")  
  
 このシナリオには、次のワークフローが含まれます。  
  
1.  基幹業務アプリケーションにメッセージ バッチを送信するときに、ワークフローが開始され、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]最小限下位層プロトコル (MLLP) プロトコルを使用して統合エンジンです。 バッチが、ADT の 2 つのバージョンを含む ^ A03 メッセージ。 送信元アプリケーションは、Tutorial_BatchSource パーティに属しています。  
  
2.  インターフェイス エンジン、MLLP にバッチを受信する受信ポート、およびメッセージのバッチを検証します。 (検証のレベル設定によって異なります BTAHL7 構成エクスプ ローラーで送信元パーティ用に選択します。)  
  
3.  BTAHL7 構成エクスプ ローラーでバッチの断片化をできるようにする設定に基づき、インターフェイス エンジンを解析してバッチに 2 つの個別 ADT ^ A03 メッセージ。 BTAHL7 構成エクスプ ローラーで送信元パーティ用に選択された設定に基づいて、個々 のメッセージを検証します。  
  
4.  インターフェイスのエンジンは、BTAHL7 構成エクスプ ローラーで受信確認の定義の設定に基づいて、各メッセージの受信確認を生成します。 このチュートリアルでは、ため、インターフェイス エンジンは、メッセージ ヘッダーと本文の両方を検証した後のメッセージごとに 1 つ、アプリケーションは、受け入れ確認の生成元の受信確認モードを選択します。 エンジンは、ACK_024_GLO_DEF スキーマに基づいて、受信確認をビルド、受信確認の MSA2 フィールドに"AA"を入力し、MSH3、送信先パーティを入力したうえで、MSH5 で送信元パーティを入力します。  
  
5.  インターフェイスのエンジンは、各受信確認の MLLP ラッパーし、ルート ソースに受信確認が MLLP 送信アダプターを使ってパーティが受信確認を処理する設定。  
  
6.  インターフェイス エンジンは、各メッセージ、および各メッセージに MLLP を個別に送信ポートの非受信確認メッセージを処理するを設定するルート ラッパー MLLP を配置します。  
  
7.  BTAHL7 では、その MSH5 フィールドで指定した宛先に別の MLLP 送信ポートを通じて各メッセージを送信します。  
  
8.  BTAHL7 送信先パーティに送信するアプリケーションに受け入れられるように、受信した各メッセージの受信確認します。  
  
9. インターフェイス エンジンでは、各受信確認を受信します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: ヘッダーと受信確認スキーマを追加します。](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [手順 2: v2.3.1 の一般的なスキーマを追加します。](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [手順 3: トリガー イベント (メッセージ) のスキーマを追加します。](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [手順 4: 作成、バッチ メッセージを受け入れるための受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [手順 5: メッセージを配信する送信ポートを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [手順 6: 受信確認を配信する送信ポートを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [手順 7: を作成し、送信元パーティを構成します。](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [手順 8: BizTalk Server を再起動します。](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [手順 9: 断片化した受信バッチのシナリオを確認してください。](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)