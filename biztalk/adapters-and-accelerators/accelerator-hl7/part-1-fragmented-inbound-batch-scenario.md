---
title: 作業 1:受信バッチのシナリオを断片化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- batching tutorial, fragmenting messages
- fragmenting messages
ms.assetid: 8adf2c17-5f66-408d-b30b-51b22d8e71fa
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d334c9cee7da4cca1a28268f0d693b5a7813839
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290041"
---
# <a name="part-1-fragmented-inbound-batch-scenario"></a>作業 1:断片化した受信バッチのシナリオ
このチュートリアルには、個別のメッセージにフラグメントが、および、変換先に個々 のメッセージを送信、HL7 でエンコードされたバッチを受信します。 次の図は、このプロセスの流れを示しています。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-fragmented-inbound-batching-scenario.gif "hl7_fragmented_inbound_batching_scenario")  
  
 このシナリオには、次のワークフローが含まれます。  
  
1. 基幹業務アプリケーションは、Microsoft にメッセージのバッチを送信するときに、ワークフローが開始[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]統合エンジンが、最小限の下位レイヤー プロトコル (MLLP) プロトコルを使用します。 バッチには ADT の 2 つのバージョンが含まれています ^ A03 メッセージ。 元のアプリケーションは、Tutorial_BatchSource パーティに属しています。  
  
2. インターフェイスのエンジン、MLLP でバッチを受信する受信ポート、およびメッセージのバッチを検証します。 (検証のレベルは、BTAHL7 構成エクスプ ローラーで送信元パーティの選択した設定に依存)。  
  
3. バッチの断片化をできるようにする BTAHL7 構成エクスプ ローラーの設定に基づいて、インターフェイス エンジン バッチの解析に 2 つの個別 ADT ^ A03 メッセージ。 BTAHL7 構成エクスプ ローラーで送信元パーティの選択した設定に基づいて、個々 のメッセージを検証します。  
  
4. インターフェイスのエンジンは、BTAHL7 構成エクスプ ローラーで受信確認の定義の設定に基づいて、各メッセージの受信確認を生成します。 このチュートリアルでは、インターフェイス エンジンでは、メッセージごとに単一アプリケーションの同意の確認を生成、メッセージ ヘッダーと本文の両方を検証した後、元の受信確認のモードを選択します。 エンジンは、ACK_024_GLO_DEF スキーマに基づいて、受信確認をビルド、受信確認の MSA2 フィールドに"AA"を入力し、MSH3、送信先パーティが入力したうえで、MSH5 で送信元パーティを入力します。  
  
5. インターフェイス エンジンが MLLP の受信確認は、各ラッパーを配置し、受信確認を処理するよう MLLP 送信アダプターでパーティのソースに受信確認のルートを設定します。  
  
6. インターフェイスのエンジンは、MLLP ラッパーは各メッセージ、および、MLLP を個別に各メッセージの送信ポートの受信確認ではないメッセージを処理するように設定するルートを配置します。  
  
7. BTAHL7 では、その MSH5 フィールドで指定した変換先に別の MLLP 送信ポートを通じて各メッセージを送信します。  
  
8. BTAHL7 送信先パーティに送信、受信した各メッセージの受信確認をアプリケーションに承認します。  
  
9. インターフェイスのエンジンは、各受信確認を受信します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ステップ 1: ヘッダーと受信確認スキーマの追加](../../adapters-and-accelerators/accelerator-hl7/step-1-add-header-and-acknowledgment-schemas.md)  
  
-   [手順 2:v2.3.1 の一般的なスキーマの追加](../../adapters-and-accelerators/accelerator-hl7/step-2-add-common-schemas-for-v2-3-1.md)  
  
-   [ステップ 3:トリガー イベント (メッセージ) スキーマの追加](../../adapters-and-accelerators/accelerator-hl7/step-3-add-a-trigger-event-message-schema.md)  
  
-   [手順 4:バッチ メッセージを受け入れるための受信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-4-create-a-receive-port-for-accepting-the-batch-message.md)  
  
-   [手順 5:メッセージを配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md)  
  
-   [手順 6:受信確認を配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md)  
  
-   [手順 7:ソース パーティの作成と構成](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)  
  
-   [手順 8:BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md)  
  
-   [手順 9:断片化した受信バッチのシナリオの確認](../../adapters-and-accelerators/accelerator-hl7/step-9-verify-the-fragmented-inbound-batch-scenario.md)