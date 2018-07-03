---
title: '手順 4: バッチの作成シナリオでは、送信元パーティの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b06b6545-4c2e-4a56-9feb-bd3f9574d4d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbb4e172c88c179ea53f1e48d1e08dcb63458607
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999827"
---
# <a name="step-4-configure-the-source-party-for-the-create-batch-scenario"></a>手順 4: バッチの作成シナリオでは、送信元パーティを構成します。
この手順では、バッチの作成シナリオでは、送信元パーティを構成します。 選択することも、受信確認を BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) バッチがこのパーティ用に定義されています。 受信確認のバッチのスケジュールを設定するように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージ数が 2 に到達した後にバッチを作成します。  
  
> [!NOTE]
>  作成した同じ送信元パーティを使用するこのシナリオで[手順 7: を作成し、送信元パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)(断片化された受信バッチのシナリオ) このチュートリアルの第 1 部の。  
  
### <a name="to-configure-the-source-party-for-the-create-batch-scenario"></a>バッチの作成シナリオでは、送信元パーティを構成するには  
  
1. BTAHL7 構成エクスプ ローラーでの**パーティ**コンソール ツリーで、タブをクリックして**Tutorial_BatchSource**します。  
  
2. をクリックして、**受信確認**詳細ペインでタブ。 いることを確認、**受信確認の種類**は**OriginalMode**します。  
  
3. をクリックして、**バッチ定義**タブ。**使用可能なメッセージの Ack**、 をクリックして**BTAHL7Schemas.ADT_A03_231_GLO_DEF**、右矢印を移動 をクリックして (**>>**)にこのスキーマを追加するには**メッセージの Ack を選択した**、 をクリックし、**保存**します。  
  
4. をクリックして、**バッチ スケジュール**タブ。**後にバッチを繰り返す**セクションで、**メッセージ**、し、入力**2**で、**メッセージ**ボックス。  
  
5. クリックして**スケジュールの開始**します。  
  
   進みます[手順 5: メッセージ バッチの送信ポートを作成する](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)します。