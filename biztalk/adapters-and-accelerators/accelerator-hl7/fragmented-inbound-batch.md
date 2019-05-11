---
title: 受信バッチを断片化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, fragmenting messages
- messages, fragmenting
- fragmenting messages
ms.assetid: 5844710e-f662-48a3-bf1a-bc1ba91e678a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac8e0d99bfa9ea8696a7cd9f6eeed8a6be16006d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267817"
---
# <a name="fragmented-inbound-batch"></a><span data-ttu-id="c8892-102">断片化した受信バッチ</span><span class="sxs-lookup"><span data-stu-id="c8892-102">Fragmented Inbound Batch</span></span>
<span data-ttu-id="c8892-103">構成できる[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]メッセージ バッチを受信する、バッチからのメッセージを抽出し、送信先システムに、個々 のメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="c8892-103">You can configure [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to receive a message batch, extract the messages from the batch, and then route the individual messages to the destination system.</span></span> <span data-ttu-id="c8892-104">受信のバッチが個別のメッセージにフラグメントの断片化を有効にした場合それ以外の場合、バッチが処理され、1 つのバッチまたはインターチェンジとしてルーティングします。</span><span class="sxs-lookup"><span data-stu-id="c8892-104">If you enable fragmentation, the inbound batch fragments into individual messages; otherwise, the batch is processed and routed as a single 'batch' or interchange.</span></span> <span data-ttu-id="c8892-105">バッチ処理を有効にするのにには、BTAHL7 構成エクスプ ローラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c8892-105">You use BTAHL7 Configuration Explorer to enable batching.</span></span> <span data-ttu-id="c8892-106">バッチ処理を有効にする方法の詳細については、次を参照してください。[バッチ処理構成](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)します。</span><span class="sxs-lookup"><span data-stu-id="c8892-106">For more information about enabling batching, see [Configuring Batching](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md).</span></span>  
  
 <span data-ttu-id="c8892-107">一般的な断片化した受信バッチのシナリオを次に示します。</span><span class="sxs-lookup"><span data-stu-id="c8892-107">The following describes a typical fragmented inbound batch scenario:</span></span>  
  
1.  <span data-ttu-id="c8892-108">システム A で実行されている、基幹業務アプリケーションでは、BTAHL7 をメッセージのバッチを送信します。</span><span class="sxs-lookup"><span data-stu-id="c8892-108">A line-of-business application, running on System A, sends a message batch to BTAHL7.</span></span>  
  
     <span data-ttu-id="c8892-109">バッチのメッセージは、2 つの異なる形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="c8892-109">Batch messages can be in two different formats.</span></span> <span data-ttu-id="c8892-110">BTAHL7 では、次の形式を処理できます。</span><span class="sxs-lookup"><span data-stu-id="c8892-110">BTAHL7 can process the following formats:</span></span>  
  
    -   <span data-ttu-id="c8892-111">形式 1:1 つのファイルのヘッダーとトレーラー (FHS/FTS) の組み合わせと 1 つまたは複数バッチ ヘッダーとトレーラー (BHS/BTS) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8892-111">Format 1: Includes one file header and trailer (FHS/FTS) pair and one or more batch header and trailers (BHS/BTS).</span></span>  
  
        ```  
        FHS  
        BHS  
        MSH  
        .............  
        MSH  
        ...........  
        BTS  
        BHS  
        MSH  
        ..............  
        MSH  
        ...............  
        BTS  
        FTS  
        ```  
  
    -   <span data-ttu-id="c8892-112">形式 2:HL7 の定義ファイルとバッチのラッパーが含まれていないと、一連の中断がストリーム内のメッセージ。</span><span class="sxs-lookup"><span data-stu-id="c8892-112">Format 2: Does not contain HL7 defined file and batch wrappers, and suspends a series are messages in a stream.</span></span>  
  
        ```  
        MSH  
        .......  
        MSH  
        ........  
        MSH  
        .........  
        ```  
  
2.  <span data-ttu-id="c8892-113">BTAHL7 では、バッチから個々 のメッセージを作成し、適切なスキーマに対して、個々 のメッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="c8892-113">BTAHL7 creates individual messages from the batch and then verifies the individual messages against the appropriate schemas.</span></span>  
  
3.  <span data-ttu-id="c8892-114">BTAHL7 では、バッチから抽出された各メッセージをシステム A に、個別の受信確認メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c8892-114">BTAHL7 sends a separate acknowledgment message to System A for each message extracted from the batch.</span></span>  
  
4.  <span data-ttu-id="c8892-115">BTAHL7 では、メッセージ バッチのヘッダーではなく、個々 のメッセージのルーティング情報に基づいて、送信先システムに、個々 のメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="c8892-115">BTAHL7 routes the individual messages to the destination system based on the routing information in the individual messages, rather than the message batch header.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c8892-116">BTAHL7 がバッチとファイルのヘッダー/トレーラーを検証していないときに、 **FHS3**フィールド (送信元パーティ) を持つ断片化が有効になっている取引先が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8892-116">BTAHL7 does not validate batch and file headers/trailers when the **FHS3** field (sending party) contains a trading partner that has fragmentation enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8892-117">参照</span><span class="sxs-lookup"><span data-stu-id="c8892-117">See Also</span></span>  
 [<span data-ttu-id="c8892-118">バッチ処理の構成</span><span class="sxs-lookup"><span data-stu-id="c8892-118">Configuring Batching</span></span>](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)