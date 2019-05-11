---
title: 動的 MLLP アダプター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2e22fabb-0edf-4931-b8b2-74a5daccee4a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d603af67031c0e0429a362c6a3681f94f812b503
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258963"
---
# <a name="dynamic-mllp-adapter"></a><span data-ttu-id="27b4f-102">動的 MLLP アダプター</span><span class="sxs-lookup"><span data-stu-id="27b4f-102">Dynamic MLLP Adapter</span></span>
<span data-ttu-id="27b4f-103">以降で[!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)]、一方向または双方向 (要求-応答) の送信ポートを使用して実行時に MLLP アダプターのプロパティを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="27b4f-103">Starting with [!INCLUDE[bts2013r2](../../includes/bts2013r2-md.md)], the MLLP adapter properties can be configured at Runtime using a One-Way or Two-Way (Request-Response) send port.</span></span>  
  
## <a name="dynamic-properties"></a><span data-ttu-id="27b4f-104">動的プロパティ</span><span class="sxs-lookup"><span data-stu-id="27b4f-104">Dynamic Properties</span></span>  
 <span data-ttu-id="27b4f-105">次のプロパティは、 **GlobalPropertySchemas**名前空間。</span><span class="sxs-lookup"><span data-stu-id="27b4f-105">The following properties are in the **GlobalPropertySchemas** namespace:</span></span>  
  
|<span data-ttu-id="27b4f-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="27b4f-106">Property</span></span>|<span data-ttu-id="27b4f-107">説明</span><span class="sxs-lookup"><span data-stu-id="27b4f-107">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="27b4f-108">Message(MLLP.acceptableACKCodes)=”All ACK Codes”;</span><span class="sxs-lookup"><span data-stu-id="27b4f-108">Message(MLLP.acceptableACKCodes)=”All ACK Codes”;</span></span>|<span data-ttu-id="27b4f-109">値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="27b4f-109">Values include:</span></span><br /><br /> <span data-ttu-id="27b4f-110">-すべての確認コード</span><span class="sxs-lookup"><span data-stu-id="27b4f-110">-   All ACK Codes</span></span><br /><span data-ttu-id="27b4f-111">-AA と CA</span><span class="sxs-lookup"><span data-stu-id="27b4f-111">-   AA and CA</span></span><br /><span data-ttu-id="27b4f-112">-AA、CA、AE、CE</span><span class="sxs-lookup"><span data-stu-id="27b4f-112">-   AA, CA, AE and CE</span></span><br /><span data-ttu-id="27b4f-113">-AA、CA、AR、CR</span><span class="sxs-lookup"><span data-stu-id="27b4f-113">-   AA, CA, AR and CR</span></span><br /><br /> <span data-ttu-id="27b4f-114">似ています、**許容される確認コード**MLLP の静的送信ポートのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="27b4f-114">This is similar to the **Acceptable ACK Codes** property in a Static MLLP Send Port.</span></span>|  
|<span data-ttu-id="27b4f-115">Message(MLLP.CarriageReturn)=”0d”;</span><span class="sxs-lookup"><span data-stu-id="27b4f-115">Message(MLLP.CarriageReturn)=”0d”;</span></span>|<span data-ttu-id="27b4f-116">ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="27b4f-116">ASCII Carriage Return Character</span></span>|  
|<span data-ttu-id="27b4f-117">Message(MLLP.endBlockDelimiter)=”1c”;</span><span class="sxs-lookup"><span data-stu-id="27b4f-117">Message(MLLP.endBlockDelimiter)=”1c”;</span></span>|<span data-ttu-id="27b4f-118">終了ブロックの ASCII 文字</span><span class="sxs-lookup"><span data-stu-id="27b4f-118">ASCII End Block Character</span></span>|  
|<span data-ttu-id="27b4f-119">Message(MLLP.startBlockDelimiter)=”0b”;</span><span class="sxs-lookup"><span data-stu-id="27b4f-119">Message(MLLP.startBlockDelimiter)=”0b”;</span></span>|<span data-ttu-id="27b4f-120">開始ブロック文字の ASCII</span><span class="sxs-lookup"><span data-stu-id="27b4f-120">ASCII Start Block Character</span></span>|  
|<span data-ttu-id="27b4f-121">Message(MLLP.timeout)=”60000”;</span><span class="sxs-lookup"><span data-stu-id="27b4f-121">Message(MLLP.timeout)=”60000”;</span></span>|<span data-ttu-id="27b4f-122">非アクティブな送信ソケット BTAHL7 サーバーはタイムアウトの後にピリオド (0 はタイムアウトなし)</span><span class="sxs-lookup"><span data-stu-id="27b4f-122">Period after which inactive sending socket on BTAHL7 server will timeout(0 is no timeout)</span></span>|  
|<span data-ttu-id="27b4f-123">SendPortName(Microsoft.XLANGs.BaseTypes.Address) = “127.0.0.1:11000”;</span><span class="sxs-lookup"><span data-stu-id="27b4f-123">SendPortName(Microsoft.XLANGs.BaseTypes.Address) = “127.0.0.1:11000”;</span></span>|<span data-ttu-id="27b4f-124">メッセージのルーティングのアドレスとポート</span><span class="sxs-lookup"><span data-stu-id="27b4f-124">Address and Port for routing the message</span></span>|  
|<span data-ttu-id="27b4f-125">SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) = “MLLP”;</span><span class="sxs-lookup"><span data-stu-id="27b4f-125">SendPortName(Microsoft.XLANGs.BaseTypes.TransportType) = “MLLP”;</span></span>|<span data-ttu-id="27b4f-126">(MLLP) アダプターの種類</span><span class="sxs-lookup"><span data-stu-id="27b4f-126">Type of Adapter (MLLP)</span></span>|  
  
## <a name="additional"></a><span data-ttu-id="27b4f-127">その他</span><span class="sxs-lookup"><span data-stu-id="27b4f-127">Additional</span></span>  
  
- <span data-ttu-id="27b4f-128">For HL7 をオーケストレーションでマルチパート メッセージを作成する場合、メッセージでパーツを作成この次の順序。</span><span class="sxs-lookup"><span data-stu-id="27b4f-128">When creating a multipart message in an orchestration for HL7, create the message parts in this following order:</span></span>  
  
  1. <span data-ttu-id="27b4f-129">MSH セグメント</span><span class="sxs-lookup"><span data-stu-id="27b4f-129">MSH Segment</span></span>  
  
  2. <span data-ttu-id="27b4f-130">BodySegments</span><span class="sxs-lookup"><span data-stu-id="27b4f-130">BodySegments</span></span>  
  
  3. <span data-ttu-id="27b4f-131">ZSegments</span><span class="sxs-lookup"><span data-stu-id="27b4f-131">ZSegments</span></span>  
  
     <span data-ttu-id="27b4f-132">別の順序でメッセージ部分を指定する場合は、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="27b4f-132">If you specify the message parts in a different order, the following error occurs:</span></span>  
  
     <span data-ttu-id="27b4f-133">WrongBodyPartException</span><span class="sxs-lookup"><span data-stu-id="27b4f-133">WrongBodyPartException</span></span>  
  
- <span data-ttu-id="27b4f-134">動的ルーティングをサポートするために、オーケストレーションでは、アダプターのルートのプロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="27b4f-134">The adapter route properties can be specified on the orchestration to support dynamic routing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b4f-135">参照</span><span class="sxs-lookup"><span data-stu-id="27b4f-135">See Also</span></span>  
 <span data-ttu-id="27b4f-136">[構成パラメーターを送信および受信アダプター](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="27b4f-136">[Configuration Parameters for Send and Receive Adapters](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md) </span></span>  
 <span data-ttu-id="27b4f-137">[MLLP 受信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md) </span><span class="sxs-lookup"><span data-stu-id="27b4f-137">[MLLP Receive Adapter Processing](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md) </span></span>  
 <span data-ttu-id="27b4f-138">[MLLP 送信アダプターの処理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md) </span><span class="sxs-lookup"><span data-stu-id="27b4f-138">[MLLP Send Adapter Processing](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md) </span></span>  
 [<span data-ttu-id="27b4f-139">MLLP でエンコードされたメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="27b4f-139">Processing MLLP-encoded Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)