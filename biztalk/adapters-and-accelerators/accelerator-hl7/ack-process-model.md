---
title: ACK プロセス モデル |Microsoft Docs
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
ms.openlocfilehash: 98fac157c3c3bfa62825fd3c5cb59c68aac528e6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970635"
---
# <a name="ack-process-model"></a>ACK プロセス モデル
次の一連の手順では、受信確認 (ACK) プロセス モデルについて説明します。  
  
1. 入学担当者は、患者の入院情報入学システム (ADT) にログをシステムは、トリガー イベントを生成します。  
  
2. ADT system には、患者の登録の HL7 でエンコードされたメッセージが生成されます (ADT ^ A04) に BizTalk Accelerator for HL7 配信 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。  
  
3. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システム ADT で、MLLP ラッパーを適用する ^ A04 メッセージにルーティングし、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン。  
  
   -   '元のモード' の受信確認の要件が事前構成済み  
  
   -   MSH 15 および 16 null 値を指定します。  
  
4. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンがメッセージを検証し、検証に成功した場合は、ステータスの確認メッセージを生成します**MSA01 = AA**します。  
  
5. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン変換 ADT ^ A04 メッセージ MLLP ラッパーで囲むと、ラボ情報システム (LIS) にルーティングします。  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 拡張モード ' の受信確認をあらかじめ  
  
   - MSH 15 および 16 = AL  
  
6. LIS インターフェイス レイヤーがメッセージをコミットして受け入れる ACK の状態を生成するヘッダーを検証します**MSA1 = CA**します。 インターフェイス層 MLLP ラッパーを使用してメッセージのルーティング、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン。  
  
7. LIS インターフェイス レイヤーは、メッセージ全体を検証し、アプリケーション ACK の状態が生成されます**MSA1 = AA**します。 インターフェイス層 MLLP ラッパーを使用してメッセージのルーティング、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジン。  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] あらかじめ 'ACK に必要な'、受信確認の受信確認を行う  
  
   - MSH 15 = AL で、受信側のシステムがコミット Accept メッセージと ACK を確認する必要がありますを示します  
  
8. LIS インターフェイス レイヤーは、形式の要件に従って、アプリケーション層にメッセージを配信します。  
  
9. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]インターフェイス エンジンは、(前の手順 7.) 内の LIS インターフェイス レイヤーから受信した ACK を検証し、ステータスの LIS インターフェイス レイヤーに ACK で応答**MSA1 = CA**します。  
  
10. LIS システムのユーザーは、患者の情報を確認します。  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [プログラミング ガイド](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)