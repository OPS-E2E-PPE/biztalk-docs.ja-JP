---
title: "Interrogative チュートリアル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interrogative tutorial
- interrogative tutorial, about the tutorial
- tutorials, interrogative tutorial
ms.assetid: 93988429-5544-4920-821f-54f0a67bda72
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 642f2521917dd87b60ee43a4cd7decaeeb1f1365
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="interrogative-tutorial"></a>Interrogative チュートリアル
このチュートリアルには、使用する方法を説明する詳しい手順が含まれています。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]クエリ/応答シナリオでビジネス プロセスを容易にします。  
  
> [!NOTE]
>  このチュートリアルを使用するのには、MLLP テスト ツールをインストールする必要があります。 BTAHL7 の一般的なインストールでは、これらのツールはインストールされません。 カスタム インストールを実行しを選択する必要があります**MLLP テスト ツール**アダプター フォルダーからおよび**テスト インスタンス**Artifacts フォルダからです。 テスト ツールがインストールされている場合、システムがフォルダーに含まれます\<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータです。 参照してください[用 HL7 BizTalk アクセラレータをインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)です。  
  
## <a name="interrogative-scenario"></a>Interrogative シナリオ  
 このチュートリアルでは、クエリ/応答または Interrogative シナリオを使用します。 このシナリオでは、ビジネスのフローは、次の図に示されるに似ています。 次の図に、番号付きリストでは、ワークフローについて説明します。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")  
  
1.  ワークフローの開始、受付放電転送 (ADT) システムが病院情報システムにクエリを送信します。 HL7 メッセージを使用して、"**クエリ ^ Q01**"スキーマです。 MllpSend ユーティリティが、ADT をシミュレートする、チュートリアルでは、ADT により、病院情報システムをクエリ メッセージを送信するシステムの受信ポート、BTAHL7 統合エンジンでします。  
  
2.  BTAHL7 統合エンジンは、ADT システムからクエリ メッセージを受信し、それを検証します。 その後、BTAHL7 パイプラインは、ADT に戻る受信確認を送信します。  
  
3.  BTAHL7 インターフェイス エンジンは、メッセージを処理し、ルート、HIS を通じて HIS 変換先にクエリ メッセージのパーティ ポート。  
  
4.  元のクエリから、受信確認を受信した後は、ADT システムは、応答を待ちます。 受信ポートに、HIS によって応答メッセージが再度病院情報システム送信します。 このチュートリアルでは、MllpSend ユーティリティは、応答メッセージを送信する、病院情報システムをシミュレートします。  
  
5.  BTAHL7 インターフェイス エンジンは、応答メッセージを処理し、ADT 送信ポート経由の送信先パーティにルーティングします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [チュートリアルを使用する準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)  
  
-   [手順 1: 一般的なヘッダーと確認スキーマの作成と展開](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)  
  
-   [手順 2: V2.4 の一般的なスキーマの作成](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)  
  
-   [手順 3: トリガー イベント (メッセージ) プロジェクトの作成と展開](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)  
  
-   [手順 4: ADT クエリ メッセージを受け入れるための受信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)  
  
-   [手順 5: HIS メッセージを受け入れるための受信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)  
  
-   [手順 6: クエリ メッセージを配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)  
  
-   [手順 7: 応答メッセージを配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)  
  
-   [手順 8: パーティ情報の構成](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)  
  
-   [手順 9: BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)  
  
-   [手順 10: Interrogative シナリオの確認](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-interrogative-scenario.md)  

## <a name="next-step"></a>次の手順  
 [チュートリアルを使用する準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)
  
## <a name="see-also"></a>参照  
[BizTalk Accelerator for HL7 の概要](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)