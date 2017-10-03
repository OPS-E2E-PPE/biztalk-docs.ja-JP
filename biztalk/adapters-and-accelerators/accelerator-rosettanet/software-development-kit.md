---
title: "BizTalk Server で RosettaNet accelerator 用ソフトウェア開発キット |Microsoft ドキュメント"
description: "BizTalk Server の BTARN SDK のユーティリティとサンプルの一覧"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36a1b283-26e1-407e-afc4-8879ef0d1672
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81bf0f7f0947875540d835ced3726224525f23a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="software-development-kit"></a>ソフトウェア開発キット
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]完全プログラマのリファレンスとガイドを含むソフトウェア開発キット (SDK) が含まれています。 さらに、SDK には、操作とバックエンド統合を容易にすることができるユーティリティとサンプルが含まれています。  
  
## <a name="utilities"></a>ユーティリティ  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] には、次のサンプルが含まれています。  
  
|Utility|新しく使用する機能|  
|-------------|---------|  
|[BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md)|ホスト コンピュータの [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] グループからすべての [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] アイテムの展開を解除します。|  
|[BtarnConfig](../../adapters-and-accelerators/accelerator-rosettanet/btarnconfig.md)|構成データをインポートまたはエクスポートします。|  
|[CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)|証明書をインポートします。|  
|[LOBApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)|アクションまたは応答メッセージを取引先へ送信します。|  
|[LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)|ASPX ページから取引先へアクションまたは応答メッセージを送信します。|  
|[ループバック](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)|ループバック アグリーメントを生成して、1 台のコンピュータに [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] をセットアップします。|  
|[メッセージ エディタ パイプライン コンポーネント](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-component.md)|送信または受信パイプライン内のマルチパート メッセージの一部を自動的に編集します。|  
|[Message Inspector パイプライン コンポーネント](../../adapters-and-accelerators/accelerator-rosettanet/message-inspector-pipeline-component.md)|マルチパート メッセージとメッセージの内容のすべての部分を確認します。|  
|[SchemaValidator](../../adapters-and-accelerators/accelerator-rosettanet/schemavalidator.md)|メッセージ インスタンスに関する問題のトラブルシューティングを行います。|  
|[TestCrypto](../../adapters-and-accelerators/accelerator-rosettanet/testcrypto.md)|メッセージの暗号化の解除で発生したエラーのトラブルシューティングを行います。|  
  
## <a name="samples"></a>サンプル  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] には、次のサンプルが含まれています。  
  
|サンプル|使用例|  
|------------|------------------|  
|[ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)|メッセージの受信時に通知を送信する方法|  
|[ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)|取引先からオーケストレーションによって受信したメッセージに対して特別な検証ルールを実行する方法|  
|[FileTransport サンプル](../../adapters-and-accelerators/accelerator-rosettanet/filetransport-sample.md)|SQL ポートの代わりにファイル ポートを使用する方法|  
|[GetMessages サンプル](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)|否認不可テーブルまたは LOB テーブルから、読み取り可能な形式でメッセージを取得する方法|  
|[メッセージ送信 ASPX サンプル](../../adapters-and-accelerators/accelerator-rosettanet/message-submission-aspx-sample.md)|Service Content をプライベート プロセスに送信する方法|  
|[追跡のサンプル](../../adapters-and-accelerators/accelerator-rosettanet/tracking-sample.md)|メッセージとプロセスの現在の状態を表示する方法|  
|[ビジネス ルールを使用して、3A4 プライベート応答側オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)|ビジネス ルールを組み込んでいる応答側のプライベート プロセスを実装する方法|  
|[ダブル アクション PIPAutomation オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)|オーケストレーションを実装して、ダブル アクションの PIP (Partner Interface Processes) の応答を自動的に生成する方法|  
|[3 a 2 要求 3 a 2 応答へマップのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)|3A2 要求を 3A2 応答にマップする方法|  
|[3A4 要求から 3A4 応答のマップ サンプルへ](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)|3A4 要求を 3A4 応答にマップする方法|  
|[PrivateInitiator サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)|開始側プライベート プロセスを実装する方法|  
|[PrivateResponder サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)|応答側のプライベート プロセスを実装する方法|  
|[HubScenario サンプル](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)|ハブ シナリオでのメッセージの送信を管理する方法|  
|[送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/send-pipeline.md)|送信パイプラインを実装する方法|  
|[受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/receive-pipeline.md)|受信パイプラインを実装する方法|  
|[メッセージ エディター パイプライン サンプル](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-sample.md)|着信メッセージの内容を変更する方法|  
|[スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)|スキーマを変更する方法|  
|[RNIFSend](../../adapters-and-accelerators/accelerator-rosettanet/rnifsend.md)|RNIF 処理のためのメッセージを用意し、応答側の RNIFReceive.aspx ページへメッセージを送信する方法|  
|[RNIFReceive](../../adapters-and-accelerators/accelerator-rosettanet/rnifreceive.md)|RNIF メッセージを受信し、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] パブリック プロセスによって処理するための準備を行う方法|  
|[停止および開始オーケストレーション、送信ポート、および受信場所をプログラムで](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md)|これらのアイテムを動的に停止および開始する方法|  
  
## <a name="see-also"></a>参照  
 [BizTalk Server に BizTalk Accelerator for RosettaNet の追加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [サンプル](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)