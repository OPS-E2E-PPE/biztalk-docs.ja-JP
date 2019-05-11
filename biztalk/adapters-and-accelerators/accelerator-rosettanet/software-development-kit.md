---
title: BizTalk Server で、RosettaNet アクセラレータのソフトウェア開発キット |Microsoft Docs
description: BizTalk Server の BTARN SDK のユーティリティとサンプルの一覧
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36a1b283-26e1-407e-afc4-8879ef0d1672
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64585ba6078ff93201c37fcda2d31d7dcd43efbc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281817"
---
# <a name="software-development-kit"></a>ソフトウェア開発キット
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]完全なプログラマのリファレンスとガイドが含まれるソフトウェア開発キット (SDK) が含まれています。 さらに、SDK には、ユーティリティと簡単にすることが、操作とバックエンド統合サンプルが含まれます。  

## <a name="utilities"></a>ユーティリティ  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、次のサンプルが含まれています。  


|                                                                ユーティリティ                                                                 |                                                                                                                    新しく使用する機能                                                                                                                    |
|----------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                           [BtarnClean](../../adapters-and-accelerators/accelerator-rosettanet/btarnclean.md)                           | すべて展開解除する[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]から成果物、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ホスト コンピューターのグループ |
|                          [BtarnConfig](../../adapters-and-accelerators/accelerator-rosettanet/btarnconfig.md)                          |                                                                                                  構成データをインポートまたはエクスポート                                                                                                   |
|                           [CertWizard](../../adapters-and-accelerators/accelerator-rosettanet/certwizard.md)                           |                                                                                                          証明書をインポートするには                                                                                                          |
|                       [LOBApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)                       |                                                                                       取引先のアクションまたは応答メッセージを送信するには                                                                                        |
|                    [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)                    |                                                                              取引先パートナーに ASPX ページからアクションまたは応答メッセージを送信するには                                                                               |
|                             [Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)                             |                                          ループバック アグリーメントの設定を生成する[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]1 台のコンピューターがセットアップ                                          |
|    [メッセージ エディター パイプライン コンポーネント](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-component.md)    |                                                                          受信パイプラインまたは送信内のマルチパート メッセージの一部を自動的に編集するには                                                                          |
| [Message Inspector パイプライン コンポーネント](../../adapters-and-accelerators/accelerator-rosettanet/message-inspector-pipeline-component.md) |                                                                                 マルチパート メッセージとメッセージ コンテキストのすべての部分を確認するには                                                                                  |
|                      [SchemaValidator](../../adapters-and-accelerators/accelerator-rosettanet/schemavalidator.md)                      |                                                                                             メッセージ インスタンスに関する問題のトラブルシューティング                                                                                              |
|                           [TestCrypto](../../adapters-and-accelerators/accelerator-rosettanet/testcrypto.md)                           |                                                                                              メッセージの暗号化解除エラーのトラブルシューティング                                                                                              |

## <a name="samples"></a>サンプル  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK には、次のサンプルが含まれています。  


|                                                                                                            サンプル                                                                                                            |                                                                               使用例                                                                                |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                              [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)                                                              |                                                           メッセージが到着したときに通知を送信する方法                                                            |
|                                                               [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)                                                               |                                  取引先からオーケストレーションで受信メッセージに対して特別な検証ルールを実行する方法                                  |
|                                                            [FileTransport サンプル](../../adapters-and-accelerators/accelerator-rosettanet/filetransport-sample.md)                                                            |                                                                SQL ポートではなくファイルのポートを使用する方法                                                                |
|                                                              [GetMessages サンプル](../../adapters-and-accelerators/accelerator-rosettanet/getmessages-sample.md)                                                              |                                否認不可テーブルの 1 つまたは判読できる形式で LOB テーブルからメッセージを取得する方法                                |
|                                                  [メッセージ送信 ASPX サンプル](../../adapters-and-accelerators/accelerator-rosettanet/message-submission-aspx-sample.md)                                                  |                                                            Service content をプライベート プロセスに送信する方法                                                             |
|                                                                 [Tracking サンプル](../../adapters-and-accelerators/accelerator-rosettanet/tracking-sample.md)                                                                 |                                                        メッセージおよびプロセスの現在の状態を表示する方法                                                        |
|                       [ビジネス ルールを使用した 3A4 プライベート レスポンダー オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)                       |                                                ビジネス ルールの応答側プライベート プロセスを実装する方法                                                 |
|                                       [ダブルアクション PIPAutomation オーケストレーション](../../adapters-and-accelerators/accelerator-rosettanet/double-action-pipautomation-orchestration.md)                                       |                        ダブル アクションの Partner Interface Process (Pip) の応答を自動的に生成するためのオーケストレーションを実装する方法                         |
|                                          [3A2 要求から 3A2 応答へのマップ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)                                          |                                                                3 a 2 要求を 3 a 2 応答にマップする方法                                                                 |
|                                          [3A4 要求から 3A4 応答へのマップ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)                                          |                                                                3A4 要求を 3A4 応答にマップする方法                                                                 |
|                                                         [PrivateInitiator サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)                                                         |                                                              開始側プライベート プロセスを実装する方法                                                               |
|                                                         [PrivateResponder サンプル](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)                                                         |                                                              応答側プライベート プロセスを実装する方法                                                               |
|                                                              [HubScenario サンプル](../../adapters-and-accelerators/accelerator-rosettanet/hubscenario-sample.md)                                                              |                                                           ハブ シナリオでのメッセージ送信を管理する方法                                                            |
|                                                                   [送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/send-pipeline.md)                                                                   |                                                                     送信パイプラインを実装する方法                                                                      |
|                                                                [受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/receive-pipeline.md)                                                                |                                                                    受信パイプラインを実装する方法                                                                    |
|                                                  [メッセージ エディタ パイプライン サンプル](../../adapters-and-accelerators/accelerator-rosettanet/message-editor-pipeline-sample.md)                                                  |                                                             受信メッセージの内容を変更する方法                                                             |
|                                                                  [スキーマのサンプル](../../adapters-and-accelerators/accelerator-rosettanet/schema-samples.md)                                                                  |                                                                           スキーマを変更する方法                                                                           |
|                                                                        [RNIFSend](../../adapters-and-accelerators/accelerator-rosettanet/rnifsend.md)                                                                        |                             RNIF 処理用メッセージを準備し、応答側の RNIFReceive.aspx ページにメッセージを送信する方法                              |
|                                                                     [RNIFReceive](../../adapters-and-accelerators/accelerator-rosettanet/rnifreceive.md)                                                                     | RNIF メッセージを受信しで処理するために準備する方法、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パブリック プロセス |
| [プログラミングによるオーケストレーション、送信ポート、受信場所の停止および開始](../../adapters-and-accelerators/accelerator-rosettanet/code-to-stop-and-start-orchestrations-send-ports-and-receive-locations.md) |                                                             停止して、これらの成果物を動的に起動する方法                                                             |

## <a name="see-also"></a>参照  
 [BizTalk Server に BizTalk Accelerator for RosettaNet の追加](../../adapters-and-accelerators/accelerator-rosettanet/what-biztalk-accelerator-for-rosettanet-adds-to-biztalk-server.md)   
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [サンプル](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)