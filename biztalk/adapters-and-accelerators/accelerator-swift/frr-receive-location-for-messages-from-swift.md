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
# <a name="frr-receive-location-for-messages-from-swift"></a><span data-ttu-id="1485c-102">SWIFT から FRR 受信メッセージの場所</span><span class="sxs-lookup"><span data-stu-id="1485c-102">FRR Receive Location for Messages from SWIFT</span></span>
<span data-ttu-id="1485c-103">FIN 応答 reconciliation (FRR) を有効にするのには、FRR を設定する必要があります SAA からメッセージを受信して、による処理の準備を行うのためのパイプライン コンポーネントを受信[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="1485c-103">To enable FIN response reconciliation (FRR), you must set up an FRR receive pipeline component to receive a message from SAA and prepare it for processing by [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="1485c-104">受信パイプラインには、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1485c-104">The receive pipeline contains the following components:</span></span>  
  
- <span data-ttu-id="1485c-105">逆アセンブル ステージで SWIFT 逆アセンブラー</span><span class="sxs-lookup"><span data-stu-id="1485c-105">The SWIFT disassembler in the Disassemble stage</span></span>  
  
- <span data-ttu-id="1485c-106">デコーダーの段階で SWIFT FRR デコーダー パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1485c-106">The SWIFT FRR Decoder pipeline component in the Decoder stage</span></span>  
  
- <span data-ttu-id="1485c-107">パーティの解決ステージでは、SWIFT FRR CorrelationSet 競合回避モジュールのパイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1485c-107">The SWIFT FRR CorrelationSet Resolver pipeline component in the Party Resolution stage</span></span>  
  
  <span data-ttu-id="1485c-108">ときに[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]パン/NAN を受け取る SWIFT FRR デコーダーは、応答が、パン、または NAN がかどうかを判断する MQ フィードバック コンテキスト プロパティを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="1485c-108">When [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] receives a PAN/NAN, SWIFT FRR Decoder reads the MQ Feedback context property to determine whether the response is a PAN or a NAN.</span></span> <span data-ttu-id="1485c-109">トランスポートに依存しない設定[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck ブール値がパンまたは NAN に対して false の値を true にします。</span><span class="sxs-lookup"><span data-stu-id="1485c-109">It sets the transport-agnostic [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRTransportLevelAck Boolean values to true for a PAN or false for a NAN.</span></span>  
  
  <span data-ttu-id="1485c-110">SWIFT FRR CorrelationSet 競合回避モジュールのパイプライン コンポーネントでは、MQMD の値と、FRR オーケストレーションを使用する応答メッセージの FRRCorrelationToken プロパティが上書きされます。CorrelId プロパティです。</span><span class="sxs-lookup"><span data-stu-id="1485c-110">The SWIFT FRR CorrelationSet Resolver pipeline component overwrites the response message's FRRCorrelationToken property, which the FRR orchestration uses, with the value in the MQMD.CorrelId property.</span></span>