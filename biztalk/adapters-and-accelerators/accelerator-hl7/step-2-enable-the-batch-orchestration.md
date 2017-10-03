---
title: "手順 2: バッチ オーケストレーションの有効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4badf807-f461-4d0a-a3b6-9f671e580d91
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f8b18e41aacf61ac4e55e1c8047e9685179656a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-enable-the-batch-orchestration"></a>手順 2: に、バッチ オーケストレーションが有効にします。
バッチ オーケストレーションは、バッチの作成処理を制御します。 バッチに含まれるすべてのメッセージの参照を保持、送信バッチのトランザクションを制御、バッチ メッセージを生成、送信バッチにルーティングし、入力方向の受信確認のバッチ処理します。 作業を作成するバッチ処理のバッチ オーケストレーションを参加させる必要があります。  
  
### <a name="to-enable-the-batch-orchestration"></a>バッチ オーケストレーションを有効にするには  
  
1.  BizTalk 管理コンソールで、をクリックして**オーケストレーション**を右クリックして**BatchOrchestration.Orchestration_1**、クリックして**プロパティ**です。  
  
2.  [オーケストレーションのプロパティ] ダイアログ ボックスのコンソール ツリーで、**バインド**です。  
  
3.  **バインド**] ウィンドウの**ホスト**[ **BizTalkServerApplication**です。 **[OK]**をクリックします。  
  
4.  BizTalk 管理コンソールで、右クリック**BatchOrchestration.Orchestration_1**、クリックして**Enlist**です。  
  
 進みます[手順 3: を作成し、送信先パーティを構成する](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-configure-a-destination-party.md)です。