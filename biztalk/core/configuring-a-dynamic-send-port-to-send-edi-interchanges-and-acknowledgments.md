---
title: EDI インターチェンジと確認を送信する動的送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a124059c-c29c-4a7f-a8a3-13dffc09ae5c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4883eb78a24eb7ad7254e319c901602dfcb97a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391398"
---
# <a name="configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments"></a><span data-ttu-id="1212c-102">EDI インターチェンジと確認を送信するための動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="1212c-102">Configuring a Dynamic Send Port to Send EDI Interchanges and Acknowledgments</span></span>
<span data-ttu-id="1212c-103">を、EDI 受信確認またはインターチェンジを送信するには、静的な送信ポートまたは動的送信ポートのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1212c-103">To send an EDI acknowledgment or interchange, you can use either a static send port or a dynamic send port.</span></span> <span data-ttu-id="1212c-104">動的送信ポートでは、アグリーメントを解決し、DestinationPartyName コンテキスト プロパティの値に基づいて送信先アドレスを決定するために複数の送信先のいずれかにインターチェンジを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="1212c-104">A dynamic send port enables you to send an interchange to any one of multiple destinations, because it resolves the agreement and determines the destination address based upon the value in the DestinationPartyName context property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1212c-105">受信されると、XML メッセージに基づく EDI インターチェンジを送信して、パススルーを使用している場合は、そのアプリケーションを受信するためのパイプラインの受信、DestinationPartyName コンテキスト プロパティを昇格させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1212c-105">If you are sending an EDI interchange that is based upon an XML message received, and you are using a passthrough receive pipeline to receive that application, you will have to promote the DestinationPartyName context property.</span></span> <span data-ttu-id="1212c-106">詳細については、次を参照してください。[アグリーメントの解決と送信 EDI メッセージのスキーマ決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="1212c-106">For more information, see [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1212c-107">インターチェンジを受信したポートで EDI 逆アセンブラーの DestinationPartyName プロパティが設定するため、動的送信ポートが受信確認を送信する場合は、DestinationPartyName コンテキスト プロパティが昇格する既に、受信確認。</span><span class="sxs-lookup"><span data-stu-id="1212c-107">If the dynamic send port will be sending an acknowledgment, the DestinationPartyName context property will already be promoted because the EDI Disassembler in the port that received the interchange populates the DestinationPartyName property on the acknowledgment.</span></span>  
  
 <span data-ttu-id="1212c-108">動的な一方向の送信ポートを作成するには、次の構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="1212c-108">To create a one-way dynamic send port, use the following configuration:</span></span>  
  
|<span data-ttu-id="1212c-109">場所</span><span class="sxs-lookup"><span data-stu-id="1212c-109">Location</span></span>|<span data-ttu-id="1212c-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1212c-110">Property</span></span>|<span data-ttu-id="1212c-111">設定</span><span class="sxs-lookup"><span data-stu-id="1212c-111">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="1212c-112">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="1212c-112">**Send Port Properties: General**</span></span>|<span data-ttu-id="1212c-113">[ポートの種類]</span><span class="sxs-lookup"><span data-stu-id="1212c-113">Port type</span></span>|<span data-ttu-id="1212c-114">動的な一方向</span><span class="sxs-lookup"><span data-stu-id="1212c-114">Dynamic One-Way</span></span>|  
|<span data-ttu-id="1212c-115">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="1212c-115">**Send Port Properties: General**</span></span>|<span data-ttu-id="1212c-116">送信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="1212c-116">Send handler</span></span>|<span data-ttu-id="1212c-117">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="1212c-117">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="1212c-118">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="1212c-118">**Send Port Properties: General**</span></span>|<span data-ttu-id="1212c-119">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="1212c-119">Send pipeline</span></span>|<span data-ttu-id="1212c-120">EdiSend</span><span class="sxs-lookup"><span data-stu-id="1212c-120">EdiSend</span></span>|  
|<span data-ttu-id="1212c-121">**ファイル トランスポートのプロパティ:認証**</span><span class="sxs-lookup"><span data-stu-id="1212c-121">**FILE Transport Properties: Authentication**</span></span>|<span data-ttu-id="1212c-122">ホストに (ユーザー名とパスワード) を持つネットワーク共有へのアクセスがあるない場合に、これらの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="1212c-122">Use these credentials when host does not have access to network share (with User name and Password)</span></span>|<span data-ttu-id="1212c-123">認証が必要な場合に設定します。</span><span class="sxs-lookup"><span data-stu-id="1212c-123">Set if authentication is required.</span></span>|  
|<span data-ttu-id="1212c-124">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="1212c-124">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="1212c-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1212c-125">Property</span></span>|<span data-ttu-id="1212c-126">BTS.MessageType</span><span class="sxs-lookup"><span data-stu-id="1212c-126">BTS.MessageType</span></span>|  
|<span data-ttu-id="1212c-127">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="1212c-127">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="1212c-128">演算子</span><span class="sxs-lookup"><span data-stu-id="1212c-128">Operator</span></span>|==|  
|<span data-ttu-id="1212c-129">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="1212c-129">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="1212c-130">値</span><span class="sxs-lookup"><span data-stu-id="1212c-130">Value</span></span>|<span data-ttu-id="1212c-131">**インターチェンジの**:</span><span class="sxs-lookup"><span data-stu-id="1212c-131">**For interchanges**:</span></span><br /><br /> <span data-ttu-id="1212c-132">- `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`、または</span><span class="sxs-lookup"><span data-stu-id="1212c-132">- `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`, or</span></span><br /><br /> <span data-ttu-id="1212c-133">-                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`、または</span><span class="sxs-lookup"><span data-stu-id="1212c-133">-                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`,or</span></span><br /><br /> <span data-ttu-id="1212c-134">**Ack の**:</span><span class="sxs-lookup"><span data-stu-id="1212c-134">**For ACKs**:</span></span><br /><br /> <span data-ttu-id="1212c-135">-                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`、または</span><span class="sxs-lookup"><span data-stu-id="1212c-135">-                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`, or</span></span><br /><br /> <span data-ttu-id="1212c-136">-                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`、または</span><span class="sxs-lookup"><span data-stu-id="1212c-136">-                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`, or</span></span><br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a><span data-ttu-id="1212c-137">アグリーメント プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="1212c-137">Setting Agreement Properties</span></span>  
 <span data-ttu-id="1212c-138">送信ポートを作成した後は、関数への送信パイプラインに必要なアグリーメントのプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1212c-138">After creating the send port, you need to set the agreement properties required for the send pipeline to function.</span></span> <span data-ttu-id="1212c-139">これらのプロパティのさまざまなページの設定、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1212c-139">These properties are set in various pages of the **Agreement Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1212c-140">参照</span><span class="sxs-lookup"><span data-stu-id="1212c-140">See Also</span></span>  
 [<span data-ttu-id="1212c-141">EDI ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="1212c-141">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)