---
title: 'パート 3: バッチの作成シナリオ |Microsoft Docs'
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
ms.openlocfilehash: 7e487bfbe29ee2a34f2e50affa502d7f20592fe0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975955"
---
# <a name="part-3-create-batch-scenario"></a>パート 3: バッチの作成シナリオ
このシナリオには、バッチ メッセージに結合する、およびを先にバッチを送信する 2 つの受信メッセージの受信します。 BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、ソース、宛先からのメッセージに対して生成された 2 つの受信確認を含む、受信確認のバッチを返します。 次の図は、このチュートリアルのこの部分の処理フローを示します。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-create-batch-scenario.gif "hl7_create_batch_scenario")  
  
 **バッチの作成シナリオでのメッセージのフロー**  
  
 このシナリオには、次のワークフローが含まれます。  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] メッセージ ボックス データベースにバッチ定義に準拠しているすべてのメッセージをトラップします。 この定義での入力、**バッチ定義**のタブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。 このチュートリアルで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]トラップして ADT のスキーマと Tutorial_BatchDest に送信されるすべてのメッセージ バッチは ^ A03、および ADT の結果として Tutorial_BatchSource に送信されるすべての受信確認 ^ A03 メッセージ。  
  
- スケジュールされたバッチの送信時間が発生したときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]送信バッチのトランザクションをトリガーするバッチ コントロール メッセージを送信します。 上のスケジュールを定義、**バッチ スケジュール**タブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。 クリックして、プロセスをトリガーすることもできます。**今すぐ送信**同じタブ。  
  
- バッチ オーケストレーションでは、メッセージ ボックス データベース内のトラップ メッセージからメッセージのバッチを形成します。 オーケストレーションには、ファイルのヘッダーとトレーラー、およびバッチ ヘッダーおよびトレーラーのバッチ処理もラップします。 このオーケストレーションは、ネイティブ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]によって追加されたオーケストレーション[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]を BizTalk エクスプ ローラーまたは BizTalk Server 管理コンソールでオーケストレーション ノードの下に記載されているため、BizTalk オーケストレーションのセットに設定します。  
  
- 場合 (Tutorial_BatchSource をここでは) として、送信元パーティの受信確認が定義されて、BizTalk の受信確認をバッチ処理しバッチで (\Tutorial_BatchACKDrop フォルダー) に返します。 このチュートリアルでは、短い遅延の後、バッチ処理された受信確認が送信されます。  
  
- オーケストレーションは、(この場合は、ハード ドライブ上の \Tutorial_BatchMsgDrop フォルダー) を先にバッチ処理されたメッセージを送信する送信ポート (Tutorial_BatchDest) にメッセージをルーティングします。 このチュートリアルでは、バッチ処理されたメッセージは 1 時間後に送信されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: BatchControlPort 受信ポートの構成と有効化](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-and-enable-the-batchcontrolport-receive-port.md)  
  
-   [手順 2: バッチ オーケストレーションの有効化](../../adapters-and-accelerators/accelerator-hl7/step-2-enable-the-batch-orchestration.md)  
  
-   [手順 3: 送信先パーティーの作成と構成](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)  
  
-   [手順 4: バッチの作成シナリオのソース パーティーの構成](../../adapters-and-accelerators/accelerator-hl7/step-4-configure-the-source-party-for-the-create-batch-scenario.md)  
  
-   [手順 5: メッセージ バッチの送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)  
  
-   [手順 6: 受信確認バッチの送信ポートの作成](../../adapters-and-accelerators/accelerator-hl7/step-6-create-the-send-port-for-the-acknowledgment-batch.md)  
  
-   [手順 7: オーケストレーションの開始と BizTalk Server の再起動](../../adapters-and-accelerators/accelerator-hl7/step-7-start-the-orchestration-and-restart-biztalk-server.md)  
  
-   [手順 8: バッチの作成シナリオのテスト](../../adapters-and-accelerators/accelerator-hl7/step-8-test-the-create-batch-scenario.md)