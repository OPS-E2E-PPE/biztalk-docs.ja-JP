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
# <a name="frr-receive-location-for-messages-from-the-back-end-application"></a><span data-ttu-id="251fc-102">バックエンド アプリケーションから FRR 受信メッセージの場所</span><span class="sxs-lookup"><span data-stu-id="251fc-102">FRR Receive Location for Messages from the Back-End Application</span></span>
<span data-ttu-id="251fc-103">FIN 応答 reconciliation (FRR) を有効にするのには、FRR を設定する必要がありますをバックエンド アプリケーションからメッセージを受信し、FRR オーケストレーションでの消費量の BizTalk メッセージ ボックスにルーティングする受信場所。</span><span class="sxs-lookup"><span data-stu-id="251fc-103">To enable FIN response reconciliation (FRR), you must set up an FRR receive location that receives messages from the back-end application and routes them to the BizTalk MessageBox for consumption by the FRR orchestration.</span></span> <span data-ttu-id="251fc-104">受信場所は、次のパイプライン コンポーネントで作成する必要があるカスタム FRR 受信パイプライン経由でメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="251fc-104">The receive location routes a message through a custom FRR receive pipeline that you must create with the following pipeline components:</span></span>  
  
- <span data-ttu-id="251fc-105">逆アセンブル ステージで SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="251fc-105">The SWIFT disassembler in the Disassemble stage</span></span>  
  
- <span data-ttu-id="251fc-106">デコーダーの段階で SWIFT FRR デコーダー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="251fc-106">The SWIFT FRR Decoder pipeline component in the Decoder stage</span></span>  
  
- <span data-ttu-id="251fc-107">パーティの解決ステージでは、SWIFT FRR CorrelationSet 競合回避モジュールのパイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="251fc-107">The SWIFT FRR CorrelationSet Resolver pipeline component in the Party Resolution stage</span></span>  
  
  <span data-ttu-id="251fc-108">受信ポートを持つメッセージを処理する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed False = = と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND True = =。</span><span class="sxs-lookup"><span data-stu-id="251fc-108">The receive port handles messages that have [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed==False and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND==True.</span></span> <span data-ttu-id="251fc-109">トランスポート メカニズムでは、バックエンド アプリケーションによって決まります。</span><span class="sxs-lookup"><span data-stu-id="251fc-109">The transport mechanism is whatever the back-end application dictates.</span></span>  
  
  <span data-ttu-id="251fc-110">この受信ポートは、SWIFT からのメッセージを受信場所で使用されている同じカスタム受信パイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="251fc-110">This receive port uses the same custom receive pipeline that is used by the receive location for messages from SWIFT.</span></span> <span data-ttu-id="251fc-111">ただし、パイプラインは、2 つの受信場所に対して、さまざまな機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="251fc-111">However, the pipeline performs different functions for the two receive locations.</span></span> <span data-ttu-id="251fc-112">バックエンド アプリケーションからのメッセージの受信場所では、SWIFT FRR CorrelationSet 競合回避モジュールのパイプライン コンポーネントは、関連付けトークンを初期化します。</span><span class="sxs-lookup"><span data-stu-id="251fc-112">In the receive location for messages from the back-end application, the SWIFT FRR CorrelationSet Resolver pipeline component initializes the correlation token.</span></span>