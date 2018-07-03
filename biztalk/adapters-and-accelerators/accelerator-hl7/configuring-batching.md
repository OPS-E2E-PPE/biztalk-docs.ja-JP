---
title: バッチ処理の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, configuring
- configuring, batching
ms.assetid: 33c72d5e-31dd-44a8-8418-1faab3239e8e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ea79c4b96ac54e6b2d1eed281b60a261ca5cc1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976331"
---
# <a name="configuring-batching"></a>バッチ処理の構成
使用する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]のバッチを作成する構成エクスプ ローラーでバッチ処理/バッチ送信バッチ処理の利用可能なスキーマを選択して、バッチ処理をします。  
  
> [!NOTE]
>  メッセージのバッチ処理を構成する前に、BizTalk エクスプ ローラーを使用して取引先パートナーを構成する必要があります。  
  
 次に示します、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**バッチ定義**タブ。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")  
  
 次の手順を使用して開きます[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーおよびバッチ処理を構成します。  
  
### <a name="to-enable-message-batching-for-outbound-batching-create-batch"></a>メッセージの送信に (バッチの作成) をバッチ処理のバッチ処理を有効にするには  
  
1.  **開始**] メニューの [open **BizTalk Server 管理**します。  
  
2.  管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalkアプリケーション 1**します。  
  
3.  クリックして**オーケストレーション**を右クリックして**BatchOrchestration.Orchestration_1**、し、**プロパティ**します。  
  
4.  [オーケストレーションのプロパティ] ダイアログ ボックスで、**バインド**コンソール ツリーでします。  
  
5.  **バインド**ウィンドウで、適切なホストを選択**ホスト**します。 **[OK]** をクリックします。  
  
6.  右クリックして**BatchOrchestration.Orchestration_1**、し、**参加**します。  
  
7.  右クリックして**BatchOrchestration.Orchestration_1**、し、**開始**します。  
  
### <a name="to-run-btahl7-configuration-explorer"></a>BTAHL7 構成エクスプ ローラーを実行するには  
  
-   **開始**] メニューの [open **Microsoft BizTalk Accelerator 用 HL7** 、順にクリックします**BTAHL7 構成エクスプ ローラー**します。  
  
### <a name="to-configure-batching"></a>バッチ処理を構成するには  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、 **BTAHL7 構成エクスプ ローラー** ダイアログ ボックスで、**パーティ** タブで、構成するパーティを選択し、**バッチ定義** タブで、次の操作します。  
  
  |プロパティ|目的|  
  |--------------|----------------|  
  |**必要な断片化**|以下のオプションの 1 つを選択します。<br /><br /> -   **[はい]** します。 断片化を有効にします。<br />-   **いいえ**します。 断片化を無効にします。 **注:** 、新しいパーティの**断片化のために必要な**の既定値は**いいえ**します。|  
  |**メッセージを選択します。**|バッチとして送信するメッセージの種類を選択、**使用可能なメッセージ**ウィンドウで、移動、右矢印を順にクリックします (**>>**)。|  
  |**メッセージの受信確認を選択します。**|バッチとして送信する受信確認を求めるメッセージの種類の選択、**使用可能なメッセージの Ack**ウィンドウで、右への移行を順にクリックします (**>>**)。|  
  
  > [!NOTE]
  >  追加するスキーマが表示されない場合がありますで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]プロジェクトで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーが実行されています。 これらのファイルを表示するのには、再起動する必要があります[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
## <a name="see-also"></a>参照  
 [バッチ処理のスケジュール](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)