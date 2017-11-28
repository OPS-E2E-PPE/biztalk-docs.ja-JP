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
# <a name="frr-receive-location-for-messages-from-swift"></a><span data-ttu-id="d8d80-102">FRR は、SWIFT からのメッセージの場所を受信します。</span><span class="sxs-lookup"><span data-stu-id="d8d80-102">FRR Receive Location for Messages from SWIFT</span></span>
<span data-ttu-id="d8d80-103">FIN 対応調整 (FRR) を有効にするのには、FRR を設定する必要があります SAA からメッセージを受信し、による処理の準備を行うのためのパイプライン コンポーネントを受信[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d8d80-103">To enable FIN response reconciliation (FRR), you must set up an FRR receive pipeline component to receive a message from SAA and prepare it for processing by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="d8d80-104">受信パイプラインには、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8d80-104">The receive pipeline contains the following components:</span></span>  
  
-   <span data-ttu-id="d8d80-105">逆アセンブル ステージに SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="d8d80-105">The SWIFT disassembler in the Disassemble stage</span></span>  
  
-   <span data-ttu-id="d8d80-106">デコーダーの段階で SWIFT FRR デコーダー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d8d80-106">The SWIFT FRR Decoder pipeline component in the Decoder stage</span></span>  
  
-   <span data-ttu-id="d8d80-107">パーティの解決ステージに SWIFT FRR 相互関係セット競合回避モジュールのパイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d8d80-107">The SWIFT FRR CorrelationSet Resolver pipeline component in the Party Resolution stage</span></span>  
  
 <span data-ttu-id="d8d80-108">ときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]パン/NAN を受け取る SWIFT FRR デコーダーは、応答が PAN または NAN がかどうかを判断する MQ フィードバック コンテキスト プロパティを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="d8d80-108">When [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives a PAN/NAN, SWIFT FRR Decoder reads the MQ Feedback context property to determine whether the response is a PAN or a NAN.</span></span> <span data-ttu-id="d8d80-109">トランスポートに依存しないを設定して[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck ブール値を true にパンまたは NAN では false。</span><span class="sxs-lookup"><span data-stu-id="d8d80-109">It sets the transport-agnostic [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck Boolean values to true for a PAN or false for a NAN.</span></span>  
  
 <span data-ttu-id="d8d80-110">SWIFT FRR 相互関係セット競合回避モジュールのパイプライン コンポーネントでは、MQMD で値を持つ、FRR オーケストレーションを使用する応答メッセージの FRRCorrelationToken プロパティが上書きされます。CorrelId プロパティです。</span><span class="sxs-lookup"><span data-stu-id="d8d80-110">The SWIFT FRR CorrelationSet Resolver pipeline component overwrites the response message's FRRCorrelationToken property, which the FRR orchestration uses, with the value in the MQMD.CorrelId property.</span></span>