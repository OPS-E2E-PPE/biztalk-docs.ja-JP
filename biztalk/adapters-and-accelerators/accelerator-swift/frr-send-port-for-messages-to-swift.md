---
title: SWIFT へのメッセージの FRR 送信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, send ports
- send ports, FRR
ms.assetid: 905c69a3-dff3-4a60-803d-dd617ffb6896
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa0de25c96ec7d685fa68b1d2bd675d95dea0cda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378077"
---
# <a name="frr-send-port-for-messages-to-swift"></a><span data-ttu-id="cfc02-102">SWIFT へのメッセージの FRR 送信ポート</span><span class="sxs-lookup"><span data-stu-id="cfc02-102">FRR Send Port for Messages to SWIFT</span></span>
<span data-ttu-id="cfc02-103">FIN 応答 reconciliation (FRR) を有効にするには、MQSeries の SAA BizTalk アダプターを経由するメッセージを送信する FRR 送信ポートを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfc02-103">To enable FIN response reconciliation (FRR), you must set up an FRR send port that sends a message to SAA through the BizTalk Adapter for MQSeries.</span></span> <span data-ttu-id="cfc02-104">この送信ポートのルート カスタム FRR 経由でメッセージの送信パイプライン コンポーネント、次のパイプライン コンポーネントを使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfc02-104">This send port routes a message through a custom FRR send pipeline component that you must create with the following pipeline components:</span></span>  
  
- <span data-ttu-id="cfc02-105">アセンブル ステージで SWIFT アセンブラー</span><span class="sxs-lookup"><span data-stu-id="cfc02-105">The SWIFT assembler in the Assemble stage</span></span>  
  
- <span data-ttu-id="cfc02-106">エンコード段階で SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cfc02-106">The SWIFTAsmFrrMQSeriesHelper pipeline component in the Encode stage</span></span>  
  
  <span data-ttu-id="cfc02-107">SWIFTAsmFrrMQSeriesHelper パイプライン コンポーネントは、FRRCorrelationToken プロパティの値を送信メッセージの MQMD_MsgID プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="cfc02-107">The SWIFTAsmFrrMQSeriesHelper pipeline component sets the MQMD_MsgID property of the outgoing message to the value of the FRRCorrelationToken property.</span></span> <span data-ttu-id="cfc02-108">また、割り当てし、パイプラインのデザイン時に設定されている値"MQ"で始まるその他の必要なコンテキスト プロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="cfc02-108">It also assigns and promotes any other required context properties starting with "MQ" with values set at the pipeline design time.</span></span> <span data-ttu-id="cfc02-109">送信パイプラインには、構成可能なプロパティとして MQSeries に対して定義されている各プロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfc02-109">The send pipeline includes each property defined for MQSeries as a configurable property.</span></span> <span data-ttu-id="cfc02-110">各値は「使われない」既定値です。</span><span class="sxs-lookup"><span data-stu-id="cfc02-110">Each value defaults to "Not Used".</span></span>  
  
  <span data-ttu-id="cfc02-111">送信ポートを持つメッセージを処理する[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed False = = と[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND True = =。</span><span class="sxs-lookup"><span data-stu-id="cfc02-111">The send port handles messages that have [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed==False and [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_SWIFTBOUND==True.</span></span> <span data-ttu-id="cfc02-112">トランスポート メカニズムでは、BizTalk Adapter for MQSeries です。</span><span class="sxs-lookup"><span data-stu-id="cfc02-112">The transport mechanism is the BizTalk Adapter for MQSeries.</span></span> <span data-ttu-id="cfc02-113">断片化のサイズなどのトランスポートのプロパティについては、MQSeries のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfc02-113">For information about the transport properties, such as the fragmentation size, see the MQSeries documentation.</span></span>