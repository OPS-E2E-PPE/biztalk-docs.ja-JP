---
title: '手順 4: 作成バッチ シナリオでは、送信元パーティの構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 12f7ca9eebb28bb97ae925aec4fc34cefd5a2dcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206402"
---
# <a name="step-4-configure-the-source-party-for-the-create-batch-scenario"></a>手順 4: 作成バッチ シナリオでは、送信元パーティを構成します。
この手順では、バッチの作成シナリオでは、送信元パーティを構成します。 選択することも、受信確認を BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])、バッチ、このパーティ用に定義されています。 受信確認のバッチのスケジュールを設定するように[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージの数が 2 に達した後にバッチを作成します。  
  
> [!NOTE]
>  作成した同じ送信元パーティを使用するこのシナリオで[手順 7: を作成し、送信元パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-7-create-and-configure-a-source-party.md)(断片化された受信バッチのシナリオ) このチュートリアルの第 1 部のです。  
  
### <a name="to-configure-the-source-party-for-the-create-batch-scenario"></a>バッチの作成シナリオでは、送信元パーティを構成するには  
  
1.  BTAHL7 構成エクスプ ローラーで、上、**パーティ**コンソール ツリーで、タブをクリックし**Tutorial_BatchSource**です。  
  
2.  クリックして、**受信確認** タブで、詳細ウィンドウ。 いることを確認、**受信確認の種類**は**OriginalMode**です。  
  
3.  クリックして、**バッチ定義**タブです。[**使用可能なメッセージの Ack**をクリックして**BTAHL7Schemas.ADT_A03_231_GLO_DEF**、右向きの矢印を移動] をクリックして (**>>**)にこのスキーマを追加するには**メッセージの Ack を選択した**、クリックして**保存**です。  
  
4.  クリックして、**バッチ スケジュール**タブです。**後にバッチを繰り返して**セクションで、**メッセージ**、し、入力**2**で、**メッセージ**ボックス。  
  
5.  をクリックして**スケジュールの開始**です。  
  
 進みます[手順 5: メッセージのバッチの送信ポートを作成する](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-send-port-for-the-message-batch.md)です。