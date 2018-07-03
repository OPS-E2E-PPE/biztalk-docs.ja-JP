---
title: 'パート 2: バッチのバッチのシナリオ |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, outbound batches
- batching, inbound batches
ms.assetid: 36b9d927-f5b7-4c1a-9163-9e79d17c3e9e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 593f1e57b12eb30f47db65bfacd34a988f701f07
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975419"
---
# <a name="part-2-batch-inbatch-out-scenario"></a>パート 2: 内のバッチ/バッチ アウト シナリオ
このチュートリアルでは、HL7 エンコード バッチ ファイル、渡す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]せず、最適化、および変換先にそのままのバッチ ファイルを送信します。 次の図は、このプロセスのフローと、以下のサブセクションには、ワークフローがについて説明します。  
  
> [!NOTE]
>  チュートリアルのこの部分を開始する前に、コマンド プロンプトを閉じることで、第 1 部で使用した MllpReceive および MllpSend ツール オフにします。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-batch-in-batch-out-scenario.gif "hl7_batch_in_batch_out_scenario")  
  
 **バッチ内のメッセージのフローで/バッチ アウト シナリオ**  
  
 このシナリオには、次のワークフローが含まれます。  
  
1. 基幹業務アプリケーションに、Microsoft BizTalk Accelerator for HL7 メッセージのバッチを送信するときに、ワークフローが開始されます ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) の統合エンジンが、ファイル プロトコルを使用します。 バッチには ADT の 2 つのバージョンが含まれています ^ A03 メッセージ。 元のアプリケーションは、Tutorial_BatchSource パーティに属しています。  
  
2. 統合エンジン ファイルのバッチを受信する受信ポート、およびメッセージのバッチを検証します。 (検証のレベルでの送信元パーティ用に選択された設定によって異なります[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。)。  
  
3. 設定に基づいて[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン、パーティのバッチの断片化を無効にする構成エクスプ ローラーで個別のメッセージにバッチを解析できませんはバッチとバッチを残します。 送信元パーティの選択した設定に基づいて、個々 のメッセージを検証します[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
4. インターフェイスのエンジンが受信確認の定義の設定に基づいて、バッチ メッセージの受信確認を生成、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パーティの構成エディター。 ここでは、インターフェイス エンジン メッセージ ヘッダーと本文の両方を検証した後、メッセージ バッチの 1 つアプリケーションに同意の確認が生成されますので、元の受信確認のモードを選択します。 エンジンは、ACK_024_GLO_DEF スキーマに基づいて、受信確認をビルド、受信確認の MSA2 フィールドに"AA"を入力し、MSH3、送信先パーティが入力したうえで、MSH5 で送信元パーティを入力します。  
  
5. ファイルからソースへの受信確認のバッチがパーティ インターフェイス エンジンのルートでは、アダプターの受信確認を処理するように設定を送信します。 この場合、 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] \Tutorial_BatchACKDrop フォルダーにバッチをルーティングします。  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 先にメッセージのバッチに指定された送信先パーティでは、この場合フォルダー \Tutorial_BTAHL7Drop を送信します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: バッチ イン/バッチ アウトのパーティー情報の構成](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-party-information-for-batch-in-batch-out.md)  
  
-   [手順 2: 送信ポートと受信ポートの変更または作成](../../adapters-and-accelerators/accelerator-hl7/step-2-modify-or-create-the-send-and-receive-ports.md)  
  
-   [パート 3: バッチ イン/バッチ アウト シナリオのテスト](../../adapters-and-accelerators/accelerator-hl7/step-3-test-the-batch-in-batch-out-scenario.md)