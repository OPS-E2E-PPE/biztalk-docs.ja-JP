---
title: "バッチ処理の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching, configuring
- configuring, batching
ms.assetid: 33c72d5e-31dd-44a8-8418-1faab3239e8e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9ab9ead01273e54826db670e7e6d6a2e9af6200
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-batching"></a>バッチ処理の構成
使用する[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]バッチを作成する構成エクスプ ローラーでバッチ/バッチ送信バッチ処理の利用可能なスキーマを選択して、バッチ処理をします。  
  
> [!NOTE]
>  メッセージのバッチ処理を構成する前に、BizTalk エクスプ ローラーを使用して取引先を構成する必要があります。  
  
 次の図に示しています、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー**バッチ定義**タブです。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-ops-batchdef.gif "hl7_ops_batchdef")  
  
 開くには、次の手順を使用して[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーとバッチ処理を構成します。  
  
### <a name="to-enable-message-batching-for-outbound-batching-create-batch"></a>メッセージの送信に (バッチの作成) をバッチ処理のバッチ処理を有効にするには  
  
1.  **開始** メニューの 開いている**BizTalk Server 管理コンソール**です。  
  
2.  管理コンソールで  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalkアプリケーション 1**です。  
  
3.  をクリックして**オーケストレーション**を右クリックして**BatchOrchestration.Orchestration_1**、し、**プロパティ**です。  
  
4.  [オーケストレーションのプロパティ] ダイアログ ボックスで、**バインド**コンソール ツリーでします。  
  
5.  **バインド** ウィンドウで、適切なホストを選択して**ホスト**です。 **[OK]**をクリックします。  
  
6.  右クリック**BatchOrchestration.Orchestration_1**、し、 **Enlist**です。  
  
7.  右クリック**BatchOrchestration.Orchestration_1**、し、**開始**です。  
  
### <a name="to-run-btahl7-configuration-explorer"></a>BTAHL7 構成エクスプ ローラーを実行するには  
  
-   **開始**メニューの 開く**Microsoft BizTalk Accelerator 用 HL7** 、クリックして**BTAHL7 構成エクスプ ローラー**です。  
  
### <a name="to-configure-batching"></a>バッチ処理を構成するには  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーで、 **BTAHL7 構成エクスプ ローラー** ダイアログ ボックスで、**パーティ** タブで、構成するパーティを選択し、**バッチ定義** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**断片化が必要**|以下のオプションの 1 つを選択します。<br /><br /> -   **[はい]**です。 断片化を有効にします。<br />-   **いいえ**です。 断片化を無効にします。 **注:** 、新しいパーティの**断片化のために必要な**の既定値は**いいえ**です。|  
    |**メッセージを選択します。**|バッチとして送信するメッセージの種類を選択して、**使用可能なメッセージ** ウィンドウで、移動、右矢印をクリックして (**>>**)。|  
    |**メッセージの受信確認を選択します。**|バッチとして送信する受信確認を求めるメッセージの種類を選択して、**使用可能なメッセージの Ack**ウィンドウで、右へ移動をクリックし、(**>>**)。|  
  
    > [!NOTE]
    >  追加するスキーマが表示されない場合がありますで[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]プロジェクト内で[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーが実行されています。 これらのファイルを表示するのを再起動する必要があります[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラー。  
  
## <a name="see-also"></a>参照  
 [バッチ処理のスケジュール設定](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)