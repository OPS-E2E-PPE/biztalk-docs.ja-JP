---
title: "バッチ処理のスケジュール設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, scheduling
- scheduling batching
ms.assetid: 037626f1-1b3b-43e6-80eb-5fb900cdbd46
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 790cf5cb853da211d5e8928f398ecc1a2b3fe0ba
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="scheduling-batching"></a>バッチ処理のスケジュール設定
使用する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]をアクティブ化、要求、または送信バッチが終了するエクスプ ローラーを構成します。 送信バッチをアクティブ化する 2 つの手順で構成されています: 時間ベースの構成またはメッセージが条件とし、送信バッチ処理オーケストレーションの開始をカウントします。  
  
 次の図に示しています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**バッチ スケジュール**タブです。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")  
  
 開くには、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エクスプ ローラーの構成とスケジュールがバッチ処理します。  
  
### <a name="to-open-btahl7-configuration-explorer"></a>BTAHL7 構成エクスプ ローラーを開く  
  
-   をクリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、クリックして**BTAHL7 構成エクスプ ローラー**です。  
  
### <a name="to-schedule-message-batching"></a>メッセージのバッチ処理をスケジュールするには  
  
1.  BTAHL7 構成エクスプ ローラーを開きます。  
  
2.  BTAHL7 構成エクスプ ローラーで、、 **BTAHL7 構成エクスプ ローラー**ダイアログ ボックスの**パーティ** タブで、構成するパーティを選択し、**バッチ スケジュール**  タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**時間前に、の最初のバッチします。**|最初のバッチを開始する前に、時間数を入力します。|  
    |**後にバッチを繰り返す**|次のいずれかを選択します。<br /><br /> -   **時間**です。 バッチ処理を繰り返す時間数を入力します。<br />-   **メッセージ**です。 次のバッチ処理する前に処理するメッセージの数を入力を開始します。|  
    |**バッチの制御**|次のいずれかを選択します。<br /><br /> -   **スケジュールの開始**: バッチ スケジュールの開始を選択します。<br />-   **今すぐ送信**: バッチを開始する選択をすぐに処理します。<br />-   **スケジュールを停止**: 現在のバッチ スケジュールを停止する場合に選択します。|  
  
## <a name="see-also"></a>参照  
 [受信確認のバッチ処理の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)