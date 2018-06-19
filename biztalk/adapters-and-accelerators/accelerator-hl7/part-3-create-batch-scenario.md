---
title: 'パート 3: 作成バッチ シナリオ |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, creating
- creating, batching
ms.assetid: 02247186-5b21-4738-9110-f0ca0304f0fd
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0949d45fc70ead14338e30b554e0cb4b9694b5d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206202"
---
# <a name="part-3-create-batch-scenario"></a>パート 3: 作成するバッチのシナリオ
このシナリオでは、2 つの受信メッセージの受信、してバッチのメッセージに結合して先にバッチを送信します。 BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ターゲットからソースへのメッセージの生成された 2 つの受信確認を含む、受信確認のバッチを返します。 次の図は、チュートリアルのこの部分のプロセス フローを示しています。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")  
  
 **バッチの作成シナリオでのメッセージのフロー**  
  
 このシナリオには、次のワークフローが含まれます。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ ボックス データベースにバッチの定義に準拠しているすべてのメッセージをトラップします。 この定義でを入力する、**バッチ定義**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。 このチュートリアルでは[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]トラップして ADT のスキーマと Tutorial_BatchDest に送信されるすべてのメッセージをバッチ処理は ^ A03、および ADT の結果として Tutorial_BatchSource に送信されるすべての受信確認 ^ A03 メッセージ。  
  
-   スケジュールされたバッチの送信時の実行時に[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]送信バッチのトランザクションをトリガーするバッチ コントロール メッセージを送信します。 上のスケジュールを定義する、**バッチ スケジュール**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。 クリックして、プロセスをトリガーすることもできます。**今すぐ送信**同じタブにします。  
  
-   バッチ オーケストレーションは、メッセージ ボックス データベース内でトラップ メッセージからメッセージのバッチを形成します。 オーケストレーションでは、ファイルのヘッダーとトレーラー、およびバッチ ヘッダーおよびトレーラーのバッチ処理もラップします。 このオーケストレーションは、ネイティブな[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]によって追加されたオーケストレーション[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]BizTalk エクスプ ローラーまたは BizTalk Server 管理コンソールで [オーケストレーション] ノードの下に記載されているため、BizTalk オーケストレーションのセットに設定します。  
  
-   場合 (この場合の場合と Tutorial_BatchSource)、受信確認が送信元パーティに対して定義されて、BizTalk の受信確認のバッチし (\Tutorial_BatchACKDrop フォルダー) に、バッチの形式で返します。 このチュートリアルでは、短い遅延後にバッチ処理された受信確認が送信されます。  
  
-   オーケストレーションは、(この場合は、ハード ドライブ上の \Tutorial_BatchMsgDrop フォルダー) を変換先にバッチ メッセージを送信する送信ポート (Tutorial_BatchDest) にメッセージをルーティングします。 このチュートリアルでは、バッチ処理されたメッセージは 1 時間後に送信されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: 構成して、受信ポートの有効化、BatchControlPort](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-and-enable-the-batchcontrolport-receive-port.md)  
  
-   [手順 2: に、バッチ オーケストレーションが有効にします。](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)  
  
-   [手順 3: を作成し、送信先パーティを構成します。](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)  
  
-   [手順 4: 作成バッチ シナリオでは、送信元パーティを構成します。](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)  
  
-   [手順 5: メッセージのバッチの送信ポートを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)  
  
-   [手順 6: 受信確認のバッチの送信ポートを作成します。](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)  
  
-   [手順 7: オーケストレーションを開始し、BizTalk Server を再起動](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)  
  
-   [手順 8: 作成するバッチのシナリオをテストします。](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)