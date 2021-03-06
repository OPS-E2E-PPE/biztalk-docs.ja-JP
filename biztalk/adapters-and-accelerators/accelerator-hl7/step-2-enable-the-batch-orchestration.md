---
title: 手順 2:バッチ オーケストレーションを有効にする |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4badf807-f461-4d0a-a3b6-9f671e580d91
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0afe72cdf0ea747e5236f02577de16acb685061
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288619"
---
# <a name="step-2-enable-the-batch-orchestration"></a>手順 2:バッチ オーケストレーションを有効にします。
バッチ オーケストレーションでは、バッチの作成処理を制御します。 バッチに含まれるすべてのメッセージの参照を保持、送信バッチのトランザクションを制御、バッチ メッセージを生成、送信のバッチをルーティングし、受信確認のバッチを処理します。 作業を作成するバッチ処理のバッチ オーケストレーションを参加させる必要があります。  
  
### <a name="to-enable-the-batch-orchestration"></a>バッチ オーケストレーションを有効にするには  
  
1. BizTalk 管理コンソールで、次のようにクリックします。**オーケストレーション**、を右クリック**BatchOrchestration.Orchestration_1**、 をクリックし、**プロパティ**します。  
  
2. オーケストレーションのプロパティ] ダイアログ ボックスのコンソール ツリーで [**バインド**します。  
  
3. **バインド**ウィンドウの**ホスト**を選択します**BizTalkServerApplication**します。 **[OK]** をクリックします。  
  
4. 右クリックし、BizTalk 管理コンソールで**BatchOrchestration.Orchestration_1**、 をクリックし、**参加**します。  
  
   続行する[手順 3。作成し、送信先パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)します。