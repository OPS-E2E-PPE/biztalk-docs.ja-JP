---
title: SWIFT から FRR 受信メッセージの場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, receive locations
- receive locations, FRR
ms.assetid: d15989de-56f9-4d62-8394-f4fd6e971495
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dc4666e90510e7076a3f901ce6fc95b07ef16c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002083"
---
# <a name="frr-receive-location-for-messages-from-swift"></a>SWIFT から FRR 受信メッセージの場所
FIN 応答 reconciliation (FRR) を有効にするのには、FRR を設定する必要があります SAA からメッセージを受信して、による処理の準備を行うのためのパイプライン コンポーネントを受信[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。 受信パイプラインには、次のコンポーネントが含まれています。  
  
- 逆アセンブル ステージで SWIFT 逆アセンブラー  
  
- デコーダーの段階で SWIFT FRR デコーダー パイプライン コンポーネント  
  
- パーティの解決ステージでは、SWIFT FRR CorrelationSet 競合回避モジュールのパイプライン コンポーネント  
  
  ときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]パン/NAN を受け取る SWIFT FRR デコーダーは、応答が、パン、または NAN がかどうかを判断する MQ フィードバック コンテキスト プロパティを読み取ります。 トランスポートに依存しない設定[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck ブール値がパンまたは NAN に対して false の値を true にします。  
  
  SWIFT FRR CorrelationSet 競合回避モジュールのパイプライン コンポーネントでは、MQMD の値と、FRR オーケストレーションを使用する応答メッセージの FRRCorrelationToken プロパティが上書きされます。CorrelId プロパティです。