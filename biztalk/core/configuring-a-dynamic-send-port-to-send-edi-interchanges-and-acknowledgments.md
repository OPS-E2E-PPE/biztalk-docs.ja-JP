---
title: EDI インターチェンジと確認を送信する動的送信ポートの構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 9a793fc22394c2b4d294bcd48fae1f9403ae9278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232818"
---
# <a name="configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments"></a><span data-ttu-id="1db80-102">EDI インターチェンジと確認を送信するための動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="1db80-102">Configuring a Dynamic Send Port to Send EDI Interchanges and Acknowledgments</span></span>
<span data-ttu-id="1db80-103">EDI 確認またはインターチェンジを送信するには、静的送信ポートまたは動的送信ポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1db80-103">To send an EDI acknowledgment or interchange, you can use either a static send port or a dynamic send port.</span></span> <span data-ttu-id="1db80-104">動的送信ポートは、アグリーメントを解決して、DestinationPartyName コンテキスト プロパティ内の値に基づいて送信先アドレスを特定します。そのため、動的送信ポートを使用すると、複数の送信先のいずれにもインターチェンジを送信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1db80-104">A dynamic send port enables you to send an interchange to any one of multiple destinations, because it resolves the agreement and determines the destination address based upon the value in the DestinationPartyName context property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1db80-105">受信した XML メッセージに基づく EDI インターチェンジを送信し、そのアプリケーションを受信するためにパススルー受信パイプラインを使用する場合は、DestinationPartyName コンテキスト プロパティを昇格させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1db80-105">If you are sending an EDI interchange that is based upon an XML message received, and you are using a passthrough receive pipeline to receive that application, you will have to promote the DestinationPartyName context property.</span></span> <span data-ttu-id="1db80-106">詳細については、次を参照してください。[アグリーメントの解決と送信 EDI メッセージのスキーマの決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="1db80-106">For more information, see [Agreement Resolution and Schema Determination for Outgoing EDI Messages](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1db80-107">動的送信ポートが確認を送信する場合は、インターチェンジを受信したポートの EDI 逆アセンブラーによって確認の DestinationPartyName プロパティが設定されるため、DestinationPartyName コンテキスト プロパティが既に昇格されています。</span><span class="sxs-lookup"><span data-stu-id="1db80-107">If the dynamic send port will be sending an acknowledgment, the DestinationPartyName context property will already be promoted because the EDI Disassembler in the port that received the interchange populates the DestinationPartyName property on the acknowledgment.</span></span>  
  
 <span data-ttu-id="1db80-108">一方向の動的送信ポートを作成するには、次の構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="1db80-108">To create a one-way dynamic send port, use the following configuration:</span></span>  
  
|<span data-ttu-id="1db80-109">場所</span><span class="sxs-lookup"><span data-stu-id="1db80-109">Location</span></span>|<span data-ttu-id="1db80-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1db80-110">Property</span></span>|<span data-ttu-id="1db80-111">設定</span><span class="sxs-lookup"><span data-stu-id="1db80-111">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="1db80-112">**送信ポートのプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="1db80-112">**Send Port Properties: General**</span></span>|<span data-ttu-id="1db80-113">[ポートの種類]</span><span class="sxs-lookup"><span data-stu-id="1db80-113">Port type</span></span>|<span data-ttu-id="1db80-114">動的な一方向</span><span class="sxs-lookup"><span data-stu-id="1db80-114">Dynamic One-Way</span></span>|  
|<span data-ttu-id="1db80-115">**送信ポートのプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="1db80-115">**Send Port Properties: General**</span></span>|<span data-ttu-id="1db80-116">送信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="1db80-116">Send handler</span></span>|<span data-ttu-id="1db80-117">BizTalkServerApplication</span><span class="sxs-lookup"><span data-stu-id="1db80-117">BizTalkServerApplication</span></span>|  
|<span data-ttu-id="1db80-118">**送信ポートのプロパティ: 全般**</span><span class="sxs-lookup"><span data-stu-id="1db80-118">**Send Port Properties: General**</span></span>|<span data-ttu-id="1db80-119">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="1db80-119">Send pipeline</span></span>|<span data-ttu-id="1db80-120">EdiSend</span><span class="sxs-lookup"><span data-stu-id="1db80-120">EdiSend</span></span>|  
|<span data-ttu-id="1db80-121">**ファイル トランスポートのプロパティ: 認証**</span><span class="sxs-lookup"><span data-stu-id="1db80-121">**FILE Transport Properties: Authentication**</span></span>|<span data-ttu-id="1db80-122">ホストにネットワーク共有へのアクセス権がない場合に、これらの資格情報を (ユーザー名およびパスワードと共に) 使用します。</span><span class="sxs-lookup"><span data-stu-id="1db80-122">Use these credentials when host does not have access to network share (with User name and Password)</span></span>|<span data-ttu-id="1db80-123">認証が必要な場合に設定します。</span><span class="sxs-lookup"><span data-stu-id="1db80-123">Set if authentication is required.</span></span>|  
|<span data-ttu-id="1db80-124">**送信ポートのプロパティ: フィルター**</span><span class="sxs-lookup"><span data-stu-id="1db80-124">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="1db80-125">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1db80-125">Property</span></span>|<span data-ttu-id="1db80-126">BTS.MessageType</span><span class="sxs-lookup"><span data-stu-id="1db80-126">BTS.MessageType</span></span>|  
|<span data-ttu-id="1db80-127">**送信ポートのプロパティ: フィルター**</span><span class="sxs-lookup"><span data-stu-id="1db80-127">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="1db80-128">演算子</span><span class="sxs-lookup"><span data-stu-id="1db80-128">Operator</span></span>|==|  
|<span data-ttu-id="1db80-129">**送信ポートのプロパティ: フィルター**</span><span class="sxs-lookup"><span data-stu-id="1db80-129">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="1db80-130">値</span><span class="sxs-lookup"><span data-stu-id="1db80-130">Value</span></span>|<span data-ttu-id="1db80-131">**インターチェンジの**:</span><span class="sxs-lookup"><span data-stu-id="1db80-131">**For interchanges**:</span></span><br /><br /> <span data-ttu-id="1db80-132">- `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`、または</span><span class="sxs-lookup"><span data-stu-id="1db80-132">- `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`, or</span></span><br /><br /> <span data-ttu-id="1db80-133">-                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`、または</span><span class="sxs-lookup"><span data-stu-id="1db80-133">-                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`,or</span></span><br /><br /> <span data-ttu-id="1db80-134">**Ack の**:</span><span class="sxs-lookup"><span data-stu-id="1db80-134">**For ACKs**:</span></span><br /><br /> <span data-ttu-id="1db80-135">-                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`、または</span><span class="sxs-lookup"><span data-stu-id="1db80-135">-                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`, or</span></span><br /><br /> <span data-ttu-id="1db80-136">-                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`、または</span><span class="sxs-lookup"><span data-stu-id="1db80-136">-                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`, or</span></span><br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a><span data-ttu-id="1db80-137">アグリーメント プロパティの設定</span><span class="sxs-lookup"><span data-stu-id="1db80-137">Setting Agreement Properties</span></span>  
 <span data-ttu-id="1db80-138">送信ポートを作成したら、送信パイプラインを正しく機能させるために必要となるアグリーメント プロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1db80-138">After creating the send port, you need to set the agreement properties required for the send pipeline to function.</span></span> <span data-ttu-id="1db80-139">さまざまなページでこれらのプロパティが設定されて、**アグリーメントのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="1db80-139">These properties are set in various pages of the **Agreement Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db80-140">参照</span><span class="sxs-lookup"><span data-stu-id="1db80-140">See Also</span></span>  
 [<span data-ttu-id="1db80-141">EDI ソリューションのポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="1db80-141">Configuring Ports for an EDI Solution</span></span>](../core/configuring-ports-for-an-edi-solution.md)