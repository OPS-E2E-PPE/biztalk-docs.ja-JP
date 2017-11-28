---
title: "バックエンド アプリケーションからの受信メッセージの場所を FRR |Microsoft ドキュメント"
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
ms.assetid: da0ad616-800f-493f-822f-eca1224722ab
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41d50f83feceac0238742cd474f70ecc1449f906
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="frr-receive-location-for-messages-from-the-back-end-application"></a><span data-ttu-id="2e7cc-102">FRR は、バックエンド アプリケーションからのメッセージの場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="2e7cc-102">FRR Receive Location for Messages from the Back-End Application</span></span>
<span data-ttu-id="2e7cc-103">FIN 対応調整 (FRR) を有効にするのには、FRR を設定する必要があります受信場所をバックエンド アプリケーションからメッセージを受信し、それを FRR オーケストレーションによって消費の BizTalk メッセージ ボックスにルーティングします。</span><span class="sxs-lookup"><span data-stu-id="2e7cc-103">To enable FIN response reconciliation (FRR), you must set up an FRR receive location that receives messages from the back-end application and routes them to the BizTalk MessageBox for consumption by the FRR orchestration.</span></span> <span data-ttu-id="2e7cc-104">受信場所には、次のパイプライン コンポーネントで作成する必要がありますカスタム FRR 受信パイプラインでメッセージがルーティングします。</span><span class="sxs-lookup"><span data-stu-id="2e7cc-104">The receive location routes a message through a custom FRR receive pipeline that you must create with the following pipeline components:</span></span>  
  
-   <span data-ttu-id="2e7cc-105">逆アセンブル ステージに SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="2e7cc-105">The SWIFT disassembler in the Disassemble stage</span></span>  
  
-   <span data-ttu-id="2e7cc-106">デコーダーの段階で SWIFT FRR デコーダー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2e7cc-106">The SWIFT FRR Decoder pipeline component in the Decoder stage</span></span>  
  
-   <span data-ttu-id="2e7cc-107">パーティの解決ステージに SWIFT FRR 相互関係セット競合回避モジュールのパイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2e7cc-107">The SWIFT FRR CorrelationSet Resolver pipeline component in the Party Resolution stage</span></span>  
  
 <span data-ttu-id="2e7cc-108">受信ポートを持つメッセージを処理する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = False と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND = = True です。</span><span class="sxs-lookup"><span data-stu-id="2e7cc-108">The receive port handles messages that have [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed==False and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND==True.</span></span> <span data-ttu-id="2e7cc-109">トランスポート機構では、バックエンド アプリケーションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="2e7cc-109">The transport mechanism is whatever the back-end application dictates.</span></span>  
  
 <span data-ttu-id="2e7cc-110">この受信ポートは、SWIFT からのメッセージを受信場所で使用される同じカスタム受信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e7cc-110">This receive port uses the same custom receive pipeline that is used by the receive location for messages from SWIFT.</span></span> <span data-ttu-id="2e7cc-111">ただし、パイプラインは、2 つの受信場所に対して、さまざまな機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e7cc-111">However, the pipeline performs different functions for the two receive locations.</span></span> <span data-ttu-id="2e7cc-112">バックエンド アプリケーションからのメッセージを受信場所では、SWIFT FRR 相互関係セット競合回避モジュールのパイプライン コンポーネントは、関連付けトークンを初期化します。</span><span class="sxs-lookup"><span data-stu-id="2e7cc-112">In the receive location for messages from the back-end application, the SWIFT FRR CorrelationSet Resolver pipeline component initializes the correlation token.</span></span>