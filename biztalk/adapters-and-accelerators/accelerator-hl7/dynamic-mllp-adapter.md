---
title: "動的 MLLP アダプター |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e22fabb-0edf-4931-b8b2-74a5daccee4a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7d1d7046135de1dc1837d1fb8961ef440b5009
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="dynamic-mllp-adapter"></a><span data-ttu-id="23581-102">動的 MLLP アダプター</span><span class="sxs-lookup"><span data-stu-id="23581-102">Dynamic MLLP Adapter</span></span>
<span data-ttu-id="23581-103">以降で[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]、一方向または双方向 (要求-応答) の送信ポートを使用して実行時に MLLP アダプターのプロパティを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="23581-103">Starting with [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)], the MLLP adapter properties can be configured at Runtime using a One-Way or Two-Way (Request-Response) send port.</span></span>  
  
## <a name="dynamic-properties"></a><span data-ttu-id="23581-104">動的プロパティ</span><span class="sxs-lookup"><span data-stu-id="23581-104">Dynamic Properties</span></span>  
 <span data-ttu-id="23581-105">次のプロパティが、 **GlobalPropertySchemas**名前空間。</span><span class="sxs-lookup"><span data-stu-id="23581-105">The following properties are in the **GlobalPropertySchemas** namespace:</span></span>  
  
|<span data-ttu-id="23581-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="23581-106">Property</span></span>|<span data-ttu-id="23581-107">Description</span><span class="sxs-lookup"><span data-stu-id="23581-107">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="23581-108">メッセージ (MLLP.acceptableACKCodes) =「すべての確認コード」です。</span><span class="sxs-lookup"><span data-stu-id="23581-108">Message(MLLP.acceptableACKCodes)=”All ACK Codes”;</span></span>|<span data-ttu-id="23581-109">値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23581-109">Values include:</span></span><br /><br /> <span data-ttu-id="23581-110">-すべての確認コード</span><span class="sxs-lookup"><span data-stu-id="23581-110">-   All ACK Codes</span></span><br /><span data-ttu-id="23581-111">-AA と CA</span><span class="sxs-lookup"><span data-stu-id="23581-111">-   AA and CA</span></span><br /><span data-ttu-id="23581-112">-AA、カナダ、AE および CE</span><span class="sxs-lookup"><span data-stu-id="23581-112">-   AA, CA, AE and CE</span></span><br /><span data-ttu-id="23581-113">-AA、カナダ、AR、CR</span><span class="sxs-lookup"><span data-stu-id="23581-113">-   AA, CA, AR and CR</span></span><br /><br /> <span data-ttu-id="23581-114">似ています、**受容 ACK コード**静的 MLLP 送信ポートのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="23581-114">This is similar to the **Acceptable ACK Codes** property in a Static MLLP Send Port.</span></span>|  
|<span data-ttu-id="23581-115">メッセージ (MLLP です。キャリッジ リターン) ="0 d"です。</span><span class="sxs-lookup"><span data-stu-id="23581-115">Message(MLLP.CarriageReturn)=”0d”;</span></span>|<span data-ttu-id="23581-116">ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="23581-116">ASCII Carriage Return Character</span></span>|  
|<span data-ttu-id="23581-117">メッセージ (MLLP.endBlockDelimiter) ="1 c"です。</span><span class="sxs-lookup"><span data-stu-id="23581-117">Message(MLLP.endBlockDelimiter)=”1c”;</span></span>|<span data-ttu-id="23581-118">終了ブロックの ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="23581-118">ASCII End Block Character</span></span>|  
|<span data-ttu-id="23581-119">メッセージ (MLLP.startBlockDelimiter) ="0b"です。</span><span class="sxs-lookup"><span data-stu-id="23581-119">Message(MLLP.startBlockDelimiter)=”0b”;</span></span>|<span data-ttu-id="23581-120">開始ブロック文字の ASCII</span><span class="sxs-lookup"><span data-stu-id="23581-120">ASCII Start Block Character</span></span>|  
|<span data-ttu-id="23581-121">メッセージ (MLLP.timeout) =「60000」です。</span><span class="sxs-lookup"><span data-stu-id="23581-121">Message(MLLP.timeout)=”60000”;</span></span>|<span data-ttu-id="23581-122">BTAHL7 サーバーがタイムアウトに非アクティブなどの送信ソケットの後にピリオド (0 はタイムアウトなし)</span><span class="sxs-lookup"><span data-stu-id="23581-122">Period after which inactive sending socket on BTAHL7 server will timeout(0 is no timeout)</span></span>|  
|<span data-ttu-id="23581-123">SendPortName(Microsoft.XLANGs.BaseTypes.Address) =「127.0.0.1:11000」です。</span><span class="sxs-lookup"><span data-stu-id="23581-123">SendPortName(Microsoft.XLANGs.BaseTypes.Address) = “127.0.0.1:11000”;</span></span>|<span data-ttu-id="23581-124">メッセージのルーティングのアドレスとポート</span><span class="sxs-lookup"><span data-stu-id="23581-124">Address and Port for routing the message</span></span>|  
|<span data-ttu-id="23581-125">SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) ="MLLP"です。</span><span class="sxs-lookup"><span data-stu-id="23581-125">SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) = “MLLP”;</span></span>|<span data-ttu-id="23581-126">アダプター (MLLP) の種類</span><span class="sxs-lookup"><span data-stu-id="23581-126">Type of Adapter (MLLP)</span></span>|  
  
## <a name="additional"></a><span data-ttu-id="23581-127">追加情報</span><span class="sxs-lookup"><span data-stu-id="23581-127">Additional</span></span>  
  
-   <span data-ttu-id="23581-128">HL7 のオーケストレーションでマルチパート メッセージを作成する、ときにメッセージ部分で作成この順序に従うとします。</span><span class="sxs-lookup"><span data-stu-id="23581-128">When creating a multipart message in an orchestration for HL7, create the message parts in this following order:</span></span>  
  
    1.  <span data-ttu-id="23581-129">MSH セグメント</span><span class="sxs-lookup"><span data-stu-id="23581-129">MSH Segment</span></span>  
  
    2.  <span data-ttu-id="23581-130">BodySegments</span><span class="sxs-lookup"><span data-stu-id="23581-130">BodySegments</span></span>  
  
    3.  <span data-ttu-id="23581-131">ZSegments</span><span class="sxs-lookup"><span data-stu-id="23581-131">ZSegments</span></span>  
  
     <span data-ttu-id="23581-132">異なる順序でメッセージ部分を指定する場合は、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="23581-132">If you specify the message parts in a different order, the following error occurs:</span></span>  
  
     <span data-ttu-id="23581-133">WrongBodyPartException</span><span class="sxs-lookup"><span data-stu-id="23581-133">WrongBodyPartException</span></span>  
  
-   <span data-ttu-id="23581-134">動的ルーティングをサポートするために、オーケストレーションでは、アダプターのルートのプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="23581-134">The adapter route properties can be specified on the orchestration to support dynamic routing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23581-135">参照</span><span class="sxs-lookup"><span data-stu-id="23581-135">See Also</span></span>  
 <span data-ttu-id="23581-136">[構成パラメーターを送信および受信アダプター](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="23581-136">[Configuration Parameters for Send and Receive Adapters](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md) </span></span>  
 <span data-ttu-id="23581-137">[MLLP の受信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md) </span><span class="sxs-lookup"><span data-stu-id="23581-137">[MLLP Receive Adapter Processing](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md) </span></span>  
 <span data-ttu-id="23581-138">[MLLP 送信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md) </span><span class="sxs-lookup"><span data-stu-id="23581-138">[MLLP Send Adapter Processing](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md) </span></span>  
 [<span data-ttu-id="23581-139">MLLP でエンコードされたメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="23581-139">Processing MLLP-encoded Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)