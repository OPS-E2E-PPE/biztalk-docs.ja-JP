---
title: Interrogative チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial
- interrogative tutorial, about the tutorial
- tutorials, interrogative tutorial
ms.assetid: 93988429-5544-4920-821f-54f0a67bda72
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd7ae76dc81faf485b8bbe82c66c0253a69f251d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65300065"
---
# <a name="interrogative-tutorial"></a>Interrogative チュートリアル
このチュートリアルには、Microsoft の使用方法を説明する詳細な手順が含まれています。[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]クエリ/応答シナリオでビジネス プロセスを容易にします。  
  
> [!NOTE]
>  このチュートリアルを使用するには、MLLP テスト ツールをインストールする必要があります。 これらのツールは、BTAHL7 の一般的なインストールではインストールされません。 カスタム インストールを実行し、選択する必要があります**MLLP テスト ツール**アダプター フォルダーから、**テスト インスタンス**Artifacts フォルダから。 テスト ツールがインストールされている場合、フォルダーが、システムが含まれます\<*ドライブ*:\>\Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータです。 参照してください[for HL7 の BizTalk アクセラレータのインストール](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)します。  
  
## <a name="interrogative-scenario"></a>Interrogative シナリオ  
 このチュートリアルでは、クエリ/応答または Interrogative シナリオを使用します。 このシナリオでは、ビジネスのフローは次の図に示されている似ています。 次の図は、番号付きリストでは、ワークフローについて説明します。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")  
  
1.  ワークフローの開始、入学退院および転送 (ADT) システムでは、クエリを送信、病院の情報システムへ。 HL7 メッセージで使用する、"**QRY ^ Q01**"スキーマ。 MllpSend ユーティリティが ADT をシミュレートするチュートリアルでは、BTAHL7 の統合エンジンで受信ポートを ADT を介して病院情報システムにクエリ メッセージを送信するシステムです。  
  
2.  BTAHL7 の統合エンジンは ADT system からのクエリ メッセージを受信して検証します。 次に、BTAHL7 のパイプラインは、ADT に戻る受信確認を送信します。  
  
3.  BTAHL7 インターフェイスのエンジンは、メッセージを処理をルート、HIS をパーティの HIS の変換先にクエリ メッセージを送信ポート。  
  
4.  ADT system は、元のクエリから、受信確認を受信した後の応答を待機します。 応答メッセージは、HIS によって再度病院情報システムの送信ポートが表示されます。 このチュートリアルでは、MllpSend ユーティリティは、病院情報システムは応答メッセージの送信をシミュレートします。  
  
5.  BTAHL7 インターフェイスのエンジンは、応答メッセージを処理し、ADT の送信ポート経由の送信先パーティにルーティングします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [チュートリアルを使用する準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)  
  
-   [ステップ 1: 一般的なヘッダーと確認スキーマの作成と展開](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)  
  
-   [手順 2:V2.4 の一般的なスキーマの作成](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)  
  
-   [ステップ 3:トリガー イベント (メッセージ) プロジェクトの作成と展開](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)  
  
-   [手順 4:ADT クエリ メッセージを受け入れるための受信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)  
  
-   [手順 5:HIS メッセージを受け入れるための受信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)  
  
-   [手順 6:クエリ メッセージを配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)  
  
-   [手順 7:応答メッセージを配信する送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)  
  
-   [手順 8:パーティ情報の構成](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)  
  
-   [手順 9:BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)  
  
-   [手順 10: Interrogative シナリオの確認](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-interrogative-scenario.md)  

## <a name="next-step"></a>次の手順  
 [チュートリアルを使用する準備](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)
  
## <a name="see-also"></a>参照  
[BizTalk Accelerator for HL7 の概要](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)