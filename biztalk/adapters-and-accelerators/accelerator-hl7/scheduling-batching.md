---
title: バッチ処理のスケジュール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, scheduling
- scheduling batching
ms.assetid: 037626f1-1b3b-43e6-80eb-5fb900cdbd46
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1522a050fc6cc1b690cdd59adb26ddde5d7449f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289903"
---
# <a name="scheduling-batching"></a>バッチ処理のスケジュール
使用する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]構成エクスプ ローラーでアクティブ化、要求、または、送信バッチを終了します。 2 つの手順から成る、送信バッチをアクティブ化: 時間ベースの構成またはメッセージが条件とし、送信バッチ処理オーケストレーションの開始をカウントします。  
  
 次に示します、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**バッチ スケジュール**タブ。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchsch.gif "hl7_ops_batchsch")  
  
 次の手順を使用して開きます[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーとスケジュールがバッチ処理します。  
  
### <a name="to-open-btahl7-configuration-explorer"></a>BTAHL7 構成エクスプ ローラーを開く  
  
-   クリックして**開始**、 をポイント**プログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、順にクリックします**BTAHL7 構成エクスプ ローラー**します。  
  
### <a name="to-schedule-message-batching"></a>メッセージのバッチ処理をスケジュールするには  
  
1.  BTAHL7 構成エクスプ ローラーを開きます。  
  
2.  BTAHL7 構成エクスプ ローラーでの**BTAHL7 構成エクスプ ローラー**  ダイアログ ボックスの 、**パーティ** タブで、構成するパーティを選択し、**バッチ スケジュール**  タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**時間前に、の最初のバッチします。**|最初のバッチを開始する前に、時間数を入力します。|  
    |**後のバッチを繰り返す**|次のいずれかを選択します。<br /><br /> -   **時間**します。 バッチ処理を繰り返す時間数を入力します。<br />-   **メッセージ**します。 次のバッチ処理する前に処理するメッセージの数を入力を開始します。|  
    |**バッチのコントロール**|次のいずれかを選択します。<br /><br /> -   **スケジュールの開始**:バッチ スケジュールの開始を選択します。<br />-   **今すぐ送信**:選択すると、バッチ処理をすぐに開始します。<br />-   **スケジュールの終了**:現在のバッチ スケジュールの停止を選択します。|  
  
## <a name="see-also"></a>参照  
 [受信確認のバッチ処理の構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)