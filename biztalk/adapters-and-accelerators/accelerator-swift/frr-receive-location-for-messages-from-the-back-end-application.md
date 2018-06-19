---
title: バックエンド アプリケーションからの受信メッセージの場所を FRR |Microsoft ドキュメント
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
ms.openlocfilehash: 41d50f83feceac0238742cd474f70ecc1449f906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207538"
---
# <a name="frr-receive-location-for-messages-from-the-back-end-application"></a>FRR は、バックエンド アプリケーションからのメッセージの場所を受信します。
FIN 対応調整 (FRR) を有効にするのには、FRR を設定する必要があります受信場所をバックエンド アプリケーションからメッセージを受信し、それを FRR オーケストレーションによって消費の BizTalk メッセージ ボックスにルーティングします。 受信場所には、次のパイプライン コンポーネントで作成する必要がありますカスタム FRR 受信パイプラインでメッセージがルーティングします。  
  
-   逆アセンブル ステージに SWIFT 逆アセンブラー  
  
-   デコーダーの段階で SWIFT FRR デコーダー パイプライン コンポーネント  
  
-   パーティの解決ステージに SWIFT FRR 相互関係セット競合回避モジュールのパイプライン コンポーネント  
  
 受信ポートを持つメッセージを処理する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = False と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND = = True です。 トランスポート機構では、バックエンド アプリケーションによって決まります。  
  
 この受信ポートは、SWIFT からのメッセージを受信場所で使用される同じカスタム受信パイプラインを使用します。 ただし、パイプラインは、2 つの受信場所に対して、さまざまな機能を実行します。 バックエンド アプリケーションからのメッセージを受信場所では、SWIFT FRR 相互関係セット競合回避モジュールのパイプライン コンポーネントは、関連付けトークンを初期化します。