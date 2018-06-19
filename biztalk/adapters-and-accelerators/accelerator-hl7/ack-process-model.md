---
title: ACK 処理モデル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, process flow
- ACK process model
ms.assetid: 3c6a5eef-57ef-41f7-9782-e1cbc4dd78e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 846ecf4d8eee4eca0e8a75a3444a1478b7db5910
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205922"
---
# <a name="ack-process-model"></a>ACK プロセス モデル
次の一連の手順では、受信確認 (ACK) プロセス モデルについて説明します。  
  
1.  受付担当者ログオンと受付の患者情報受付システム (ADT) に、システムは、トリガー イベントを生成します。  
  
2.  ADT システムの患者情報登録の HL7 でエンコードされたメッセージが生成されます (ADT ^ A04) しに BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。  
  
3.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システム、ADT に MLLP ラッパーを適用する ^ A04 メッセージ ルーティング、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンです。  
  
    -   '元のモード' の受信確認の要件が事前に構成します。  
  
    -   MSH 15、16 null 値を設定します。  
  
4.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンがメッセージを検証し、検証が成功した場合は、ステータスの確認メッセージが生成されます**MSA01 AA =** です。  
  
5.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン変換、ADT ^ MLLP ラッパーで囲むと、ラボ情報システム (LIS) へのルーティングでメッセージを A04 です。  
  
    -   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]'拡張モード' の受信確認をあらかじめ構成しておきます  
  
    -   MSH 15、16 AL を =  
  
6.  LIS インターフェイス レイヤーがメッセージをコミットして受け入れる ACK の状態を生成するヘッダーを検証**MSA1 = CA**です。 インターフェイス レイヤーが MLLP のラッパーを持つメッセージをルーティング、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンです。  
  
7.  LIS インターフェイス層は、メッセージ全体を検証し、アプリケーション ACK の状態が生成されます**MSA1 AA =** です。 インターフェイス レイヤーが MLLP のラッパーを持つメッセージをルーティング、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンです。  
  
    -   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]'確認が必要'、受信確認の受信確認をあらかじめ構成しておきます  
  
    -   MSH 15 = AL で、受信側のシステムがコミット Accept メッセージと ACK を確認する必要がありますを示します  
  
8.  LIS インターフェイス層は、形式の要件に従って、アプリケーション層にメッセージを配信します。  
  
9. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン LIS インターフェイス レイヤー (手順 7. 上) から受信した確認を検証し、ステータスの LIS インターフェイス レイヤーに ACK で応答**MSA1 = CA**です。  
  
10. LIS システムのユーザーは、患者の情報を確認します。  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)