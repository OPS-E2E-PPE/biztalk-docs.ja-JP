---
title: "パート 2: バッチのバッチにシナリオを |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, outbound batches
- batching, inbound batches
ms.assetid: 36b9d927-f5b7-4c1a-9163-9e79d17c3e9e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56ffac38676fe6b163a39ff06be5fe0538800d2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="part-2-batch-inbatch-out-scenario"></a>パート 2: バッチのシナリオをバッチ処理/
このチュートリアルでは、HL7 エンコード バッチ ファイルを受け取る、渡す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]せず、断片化を解消し、変換先にそのままバッチ ファイルを送信します。 次の図は、このプロセスのフローと下記のサブセクションで、ワークフローを記述します。  
  
> [!NOTE]
>  このチュートリアルのこの部分を開始する前に、コマンド プロンプトを閉じて、第 1 部で使用した MllpReceive および MllpSend ツールは、オフにします。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")  
  
 **バッチ内のメッセージのフローのシナリオをバッチ処理/**  
  
 このシナリオには、次のワークフローが含まれます。  
  
1.  基幹業務アプリケーションにメッセージ バッチを送信するときに、ワークフローが開始され、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) の統合エンジン ファイル プロトコルを使用します。 バッチが、ADT の 2 つのバージョンを含む ^ A03 メッセージ。 送信元アプリケーションは、Tutorial_BatchSource パーティに属しています。  
  
2.  統合エンジンは、受信ファイルのバッチの受信ポート、およびメッセージのバッチを検証します。 (検証のレベルでの送信元パーティ用に選択された設定によって異なります[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。)。  
  
3.  設定に基づいて[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンは、このパーティのバッチの断片化を無効にする構成エクスプ ローラーは、個別のメッセージにバッチを解析できませんが、バッチとバッチのままにします。 ソース パーティ用に選択された設定に基づいて、個々 のメッセージを検証して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
4.  インターフェイスのエンジンが、受信確認の定義の設定に基づいて、バッチ メッセージの受信確認を生成、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーティの構成エディター。 ここでは、インターフェイス エンジンでは、メッセージ ヘッダーと本文の両方を検証した後、単一アプリケーションの同意の受信確認メッセージ バッチが生成されるため、元の受信確認モードを選択します。 エンジンは、ACK_024_GLO_DEF スキーマに基づいて、受信確認をビルド、受信確認の MSA2 フィールドに"AA"を入力し、MSH3、送信先パーティを入力したうえで、MSH5 で送信元パーティを入力します。  
  
5.  ファイルをパーティの受信確認のバッチにソース インターフェイス エンジンのルートは、アダプターの受信確認を処理する設定を送信します。 この場合、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] \Tutorial_BatchACKDrop フォルダーをバッチにルーティングします。  
  
6.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージのバッチ、変換先に指定された送信先パーティのここではフォルダー \Tutorial_BTAHL7Drop を送信します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: 構成内のバッチの情報をパーティ/アウト バッチ](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [手順 2: 変更または作成、送信および受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [手順 3: テストのバッチ処理/シナリオをバッチ処理](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)