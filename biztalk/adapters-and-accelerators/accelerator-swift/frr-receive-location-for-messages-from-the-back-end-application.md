---
title: バックエンド アプリケーションから FRR 受信メッセージの場所 |Microsoft Docs
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
ms.assetid: da0ad616-800f-493f-822f-eca1224722ab
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9133a4499e655003ec2cc3d2e0d654e5a225f58b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981531"
---
# <a name="frr-receive-location-for-messages-from-the-back-end-application"></a>バックエンド アプリケーションから FRR 受信メッセージの場所
FIN 応答 reconciliation (FRR) を有効にするのには、FRR を設定する必要がありますをバックエンド アプリケーションからメッセージを受信し、FRR オーケストレーションでの消費量の BizTalk メッセージ ボックスにルーティングする受信場所。 受信場所は、次のパイプライン コンポーネントで作成する必要があるカスタム FRR 受信パイプライン経由でメッセージをルーティングします。  
  
- 逆アセンブル ステージで SWIFT 逆アセンブラー  
  
- デコーダーの段階で SWIFT FRR デコーダー パイプライン コンポーネント  
  
- パーティの解決ステージでは、SWIFT FRR CorrelationSet 競合回避モジュールのパイプライン コンポーネント  
  
  受信ポートを持つメッセージを処理する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed False = = と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND True = =。 トランスポート メカニズムでは、バックエンド アプリケーションによって決まります。  
  
  この受信ポートは、SWIFT からのメッセージを受信場所で使用されている同じカスタム受信パイプラインを使用します。 ただし、パイプラインは、2 つの受信場所に対して、さまざまな機能を実行します。 バックエンド アプリケーションからのメッセージの受信場所では、SWIFT FRR CorrelationSet 競合回避モジュールのパイプライン コンポーネントは、関連付けトークンを初期化します。