---
title: "Samples3 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SDK samples
- examples, developing
- developing, examples
ms.assetid: b940111e-4f71-494b-b7a3-d2e8310bea51
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d81e5fe477aca032714ca124d8300c9b6c2d5ba
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="samples"></a>サンプル
このセクションでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ソフトウェア開発キット (SDK) に含まれているサンプルについて説明します。 ここでは、サンプルの構築方法、実行方法、予想される実行結果など、各サンプルについて詳しく説明します。  
  
 サンプルが含まれている、 \<*ドライブ*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk\ フォルダーです。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   アダプター サンプル フォルダー  
  
    -   [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)です。 メッセージ通知メカニズムを組み込む方法を示します。  
  
    -   [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)です。 メッセージに対して特別な検証ルールを実行する方法を示します。  
  
-   メッセージング サンプル フォルダー  
  
    -   [FileTransport サンプル](../../adapters-and-accelerators/accelerator-rosettanet/filetransport-sample.md)です。 ファイル ポートを使用するように BTARN を設定する方法を示します。  
  
    -   [GetMessages サンプル](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)です。 否認不可テーブル、基幹業務 (LOB) テーブルのいずれかからメッセージを取得する方法を示します。  
  
    -   [メッセージ送信 ASPX サンプル](../../adapters-and-accelerators/accelerator-rosettanet/message-submission-aspx-sample.md)です。 Service Content をプライベート プロセスに送信するためのサンプルの .aspx コードを提供します。 また、PIP (Partner Interface Process) アクション メッセージをその Service Content に送信するための HTML も提供します。  
  
    -   [Tracking サンプル](../../adapters-and-accelerators/accelerator-rosettanet/tracking-sample.md)です。 BTARN を使用して送受信されるメッセージの状態を表示するためのサンプルの .aspx コードを提供します。  
  
-   オーケストレーション サンプル フォルダー  
  
    -   [ビジネス ルールを使用して、3A4 プライベート応答側オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)です。 マップを使用して要求メッセージを応答メッセージに変換することにより、PIP 関連のビジネス プロセスを自動化する方法を示します。  
  
    -   [ダブル アクション PIPAutomation オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)です。 着信メッセージのタイプに基づいて応答メッセージのタイプを自動的に判断することにより、ビジネス プロセスを自動化する方法を示します。  
  
    -   [3 a 2 応答へマップのサンプルの 3 a 2 要求](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)です。 3A2 要求スキーマを 3A2 応答スキーマにマップする方法を示します。  
  
    -   [3A4 要求から 3A4 応答のマップ サンプルへ](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)です。 3A4 要求スキーマを 3A4 応答スキーマにマップする方法を示します。  
  
    -   [PrivateInitiator サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)です。 開始側プライベート プロセス オーケストレーションを作成する方法を示します。  
  
    -   [PrivateResponder サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)です。 応答側プライベート プロセス オーケストレーションを作成する方法を示します。  
  
    -   [HubScenario サンプル](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)です。 中間ハブに送信されたメッセージを最終的な受信者に送信されるメッセージに変換する方法を示します。  
  
-   パイプライン サンプル フォルダー  
  
    -   [送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/send-pipeline.md)です。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] パイプラインを使用して送信 XML メッセージを同等の RNIF メッセージに変換する方法を示します。  
  
    -   [受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/receive-pipeline.md)です。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] パイプラインを使用して着信 RNIF メッセージを同等の XML メッセージに変換する方法を示します。  
  
    -   [メッセージ エディター パイプライン サンプル](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-sample.md)です。 カスタム パイプライン コンポーネントを作成して着信メッセージを編集する方法を示します。  
  
-   スキーマ サンプル フォルダー  
  
    -   [スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)です。 PIP XML スキーマ、RosettaNet 次世代スキーマ、RNIF スキーマなど、SDK に含まれているサンプル スキーマについて説明します。 これらのスキーマの使用手順にもリンクされています。  
  
-   Web アプリケーション サンプル フォルダー  
  
    -   [RNIFSend](../../adapters-and-accelerators/accelerator-rosettanet/rnifsend.md)です。 開始側から応答側に RNIF メッセージを送信する ASPX ページをカスタマイズする方法を示します。  
  
    -   [RNIFReceive](../../adapters-and-accelerators/accelerator-rosettanet/rnifreceive.md)です。 応答側で RNIF メッセージを受信する ASPX ページをカスタマイズする方法を示します。  
  
-   [停止および開始オーケストレーション、送信ポート、および受信場所をプログラムで](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)です。 すべてのオーケストレーション、送信ポート、および受信場所の停止および開始をまとめて行ったり、1 つずつ行ったりする方法を示します。