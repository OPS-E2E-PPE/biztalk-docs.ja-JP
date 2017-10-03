---
title: "SWIFT メッセージの送信ポートを FRR |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- send ports, FRR
ms.assetid: 905c69a3-dff3-4a60-803d-dd617ffb6896
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a442b45f57009b839b4e184ef9662b253ba32b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="frr-send-port-for-messages-to-swift"></a><span data-ttu-id="c9950-102">SWIFT メッセージの送信ポートを FRR</span><span class="sxs-lookup"><span data-stu-id="c9950-102">FRR Send Port for Messages to SWIFT</span></span>
<span data-ttu-id="c9950-103">FIN 対応調整 (FRR) を有効にするには、MQSeries の SAA BizTalk アダプターを経由するメッセージを送信する FRR 送信ポートを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9950-103">To enable FIN response reconciliation (FRR), you must set up an FRR send port that sends a message to SAA through the BizTalk Adapter for MQSeries.</span></span> <span data-ttu-id="c9950-104">この送信ポート ルート カスタム FRR 経由でメッセージの送信パイプライン コンポーネントを次のパイプライン コンポーネントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9950-104">This send port routes a message through a custom FRR send pipeline component that you must create with the following pipeline components:</span></span>  
  
-   <span data-ttu-id="c9950-105">アセンブル ステージに SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="c9950-105">The SWIFT assembler in the Assemble stage</span></span>  
  
-   <span data-ttu-id="c9950-106">エンコード ステージに SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c9950-106">The SWIFTAsmFrrMQSeriesHelper pipeline component in the Encode stage</span></span>  
  
 <span data-ttu-id="c9950-107">SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネントでは、FRRCorrelationToken プロパティの値を送信メッセージの MQMD_MsgID プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c9950-107">The SWIFTAsmFrrMQSeriesHelper pipeline component sets the MQMD_MsgID property of the outgoing message to the value of the FRRCorrelationToken property.</span></span> <span data-ttu-id="c9950-108">また、によって割り当てられ、値がパイプラインのデザイン時に設定された以降"MQ"で必要なコンテキスト プロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="c9950-108">It also assigns and promotes any other required context properties starting with "MQ" with values set at the pipeline design time.</span></span> <span data-ttu-id="c9950-109">送信パイプラインには、構成可能なプロパティとして MQSeries に対して定義されている各プロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9950-109">The send pipeline includes each property defined for MQSeries as a configurable property.</span></span> <span data-ttu-id="c9950-110">各値は、「不使用」既定値です。</span><span class="sxs-lookup"><span data-stu-id="c9950-110">Each value defaults to "Not Used".</span></span>  
  
 <span data-ttu-id="c9950-111">送信ポートがメッセージを処理する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed = = False と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND = = True です。</span><span class="sxs-lookup"><span data-stu-id="c9950-111">The send port handles messages that have [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed==False and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND==True.</span></span> <span data-ttu-id="c9950-112">トランスポート機構では、BizTalk Adapter for MQSeries がします。</span><span class="sxs-lookup"><span data-stu-id="c9950-112">The transport mechanism is the BizTalk Adapter for MQSeries.</span></span> <span data-ttu-id="c9950-113">フラグメント化サイズなどのトランスポートのプロパティに関する情報は、MQSeries のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c9950-113">For information about the transport properties, such as the fragmentation size, see the MQSeries documentation.</span></span>