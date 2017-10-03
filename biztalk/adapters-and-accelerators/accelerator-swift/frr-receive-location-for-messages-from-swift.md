---
title: "SWIFT からの受信メッセージの場所を FRR |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, receive locations
- receive locations, FRR
ms.assetid: d15989de-56f9-4d62-8394-f4fd6e971495
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d609cfc8c5177581f32ee0957a6a7ae7c1fe9a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="frr-receive-location-for-messages-from-swift"></a>FRR は、SWIFT からのメッセージの場所を受信します。
FIN 対応調整 (FRR) を有効にするのには、FRR を設定する必要があります SAA からメッセージを受信し、による処理の準備を行うのためのパイプライン コンポーネントを受信[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。 受信パイプラインには、次のコンポーネントが含まれています。  
  
-   逆アセンブル ステージに SWIFT 逆アセンブラー  
  
-   デコーダーの段階で SWIFT FRR デコーダー パイプライン コンポーネント  
  
-   パーティの解決ステージに SWIFT FRR 相互関係セット競合回避モジュールのパイプライン コンポーネント  
  
 ときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]パン/NAN を受け取る SWIFT FRR デコーダーは、応答が PAN または NAN がかどうかを判断する MQ フィードバック コンテキスト プロパティを読み取ります。 トランスポートに依存しないを設定して[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck ブール値を true にパンまたは NAN では false。  
  
 SWIFT FRR 相互関係セット競合回避モジュールのパイプライン コンポーネントでは、MQMD で値を持つ、FRR オーケストレーションを使用する応答メッセージの FRRCorrelationToken プロパティが上書きされます。CorrelId プロパティです。