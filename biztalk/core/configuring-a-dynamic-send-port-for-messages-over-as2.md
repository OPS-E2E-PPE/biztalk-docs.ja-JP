---
title: AS2 経由でメッセージを動的送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 246d64e8-70ca-48f4-8b72-d43b0964dbb4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af1952947120a6f90310244f7ef17ee6fc5810d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356397"
---
# <a name="configuring-a-dynamic-send-port-for-messages-over-as2"></a><span data-ttu-id="e37cb-102">AS2 経由でのメッセージの動的送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="e37cb-102">Configuring a Dynamic Send Port for Messages over AS2</span></span>
<span data-ttu-id="e37cb-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成し、動的送信ポートを経由して AS2 メッセージを送信する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send AS2 messages over a dynamic send port.</span></span> <span data-ttu-id="e37cb-104">この構成作業では、動的送信ポートを作成し、バックエンド アプリケーションを構成して該当するコンテキスト プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-104">This configuration includes creating the dynamic send port and configuring a backend application to set the appropriate context properties.</span></span> <span data-ttu-id="e37cb-105">動的送信ポートを作成して AS2 メッセージを送信する場合、送信ポートが動作するように特定のプロパティを昇格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e37cb-105">When you create a dynamic send port to send an AS2 message, you must promote certain properties for the send port to work.</span></span> <span data-ttu-id="e37cb-106">詳細については、次を参照してください。[送信ポートを動的にメッセージを BizTalk Server AS2 の送信を構成](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md#BKMK_Proc)以下。</span><span class="sxs-lookup"><span data-stu-id="e37cb-106">For more information, see [To configure BizTalk Server to send AS2 messages over a dynamic send port](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md#BKMK_Proc) below.</span></span>  
  
 <span data-ttu-id="e37cb-107">動的送信ポートを使用すると、パーティの構成をハードコーディングせずに、複数のパーティにメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="e37cb-107">A dynamic send port enables you to send messages to multiple parties without hard-coding the party configuration.</span></span> <span data-ttu-id="e37cb-108">メッセージの送信に使用するアグリーメントおよび送信先は、コンテキスト プロパティを使用して動的に決定されます。</span><span class="sxs-lookup"><span data-stu-id="e37cb-108">The agreement and destination to be used in sending the message are determined dynamically through context properties.</span></span> <span data-ttu-id="e37cb-109">個々の顧客用に静的送信ポートを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e37cb-109">You do not have to create a static send port for each individual customer.</span></span>  
  
 <span data-ttu-id="e37cb-110">EDI メッセージまたは非 EDI メッセージを持つ AS2 メッセージや EDI 受信確認を送信するには、次のように構成された動的 HTTP 応答送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-110">To send an AS2 message with an EDI or non-EDI message or an EDI acknowledgment, create a dynamic response HTTP send port with the following configuration:</span></span>  
  
|<span data-ttu-id="e37cb-111">場所</span><span class="sxs-lookup"><span data-stu-id="e37cb-111">Location</span></span>|<span data-ttu-id="e37cb-112">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e37cb-112">Property</span></span>|<span data-ttu-id="e37cb-113">設定</span><span class="sxs-lookup"><span data-stu-id="e37cb-113">Setting</span></span>|  
|--------------|--------------|-------------|  
|<span data-ttu-id="e37cb-114">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="e37cb-114">**Send Port Properties: General**</span></span>|<span data-ttu-id="e37cb-115">ポートの種類</span><span class="sxs-lookup"><span data-stu-id="e37cb-115">Port Type</span></span>|<span data-ttu-id="e37cb-116">-動的な送信請求-応答 (場合に mdn を要求する**受信確認 (Mdn)** 一方向アグリーメント タブでページが選択されている)</span><span class="sxs-lookup"><span data-stu-id="e37cb-116">- Dynamic Solicit Response (if Request MDN in **Acknowledgements (MDNs)** page in the one-way agreement tab is selected)</span></span><br /><br /> <span data-ttu-id="e37cb-117">-動的な一方向送信ポート (場合に mdn を要求する**受信確認 (Mdn)** 一方向アグリーメント タブでページがクリアされます)</span><span class="sxs-lookup"><span data-stu-id="e37cb-117">- Dynamic One-way Send Port (if Request MDN in **Acknowledgements (MDNs)** page in the one-way agreement tab is cleared)</span></span>|  
|<span data-ttu-id="e37cb-118">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="e37cb-118">**Send Port Properties: General**</span></span>|<span data-ttu-id="e37cb-119">[送信パイプライン]</span><span class="sxs-lookup"><span data-stu-id="e37cb-119">Send pipeline</span></span>|<span data-ttu-id="e37cb-120">-AS2EdiSend (EDI エンコード メッセージの場合)</span><span class="sxs-lookup"><span data-stu-id="e37cb-120">- AS2EdiSend (for EDI-encoded messages)</span></span><br /><br /> <span data-ttu-id="e37cb-121">-AS2Send (非 EDI メッセージの場合)</span><span class="sxs-lookup"><span data-stu-id="e37cb-121">- AS2Send (for non-EDI messages)</span></span>|  
|<span data-ttu-id="e37cb-122">**送信ポートのプロパティ:[全般]**</span><span class="sxs-lookup"><span data-stu-id="e37cb-122">**Send Port Properties: General**</span></span>|<span data-ttu-id="e37cb-123">受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="e37cb-123">Receive pipeline</span></span><br /><br /> <span data-ttu-id="e37cb-124">(場合に mdn を要求する**受信確認 (Mdn)** 一方向アグリーメント タブでページが選択されている)</span><span class="sxs-lookup"><span data-stu-id="e37cb-124">(if Request MDN in **Acknowledgements (MDNs)** page in the one-way agreement tab is selected)</span></span>|<span data-ttu-id="e37cb-125">AS2Receive (動的な送信請求応答の送信ポートの場合)</span><span class="sxs-lookup"><span data-stu-id="e37cb-125">AS2Receive (for dynamic solicit response send port)</span></span>|  
|<span data-ttu-id="e37cb-126">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="e37cb-126">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="e37cb-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e37cb-127">Property</span></span>|<span data-ttu-id="e37cb-128">BTS.MessageType</span><span class="sxs-lookup"><span data-stu-id="e37cb-128">BTS.MessageType</span></span>|  
|<span data-ttu-id="e37cb-129">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="e37cb-129">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="e37cb-130">演算子</span><span class="sxs-lookup"><span data-stu-id="e37cb-130">Operator</span></span>|==|  
|<span data-ttu-id="e37cb-131">**送信ポートのプロパティ:フィルター**</span><span class="sxs-lookup"><span data-stu-id="e37cb-131">**Send Port Properties: Filters**</span></span>|<span data-ttu-id="e37cb-132">値</span><span class="sxs-lookup"><span data-stu-id="e37cb-132">Value</span></span>|<span data-ttu-id="e37cb-133">- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>` (の EDI メッセージの場合)</span><span class="sxs-lookup"><span data-stu-id="e37cb-133">- `http://schemas.microsoft.com/BizTalk/EDI/X12/2006#<schema name>` (for an EDI message)</span></span><br /><br /> <span data-ttu-id="e37cb-134">- `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root` (x12 受信確認)</span><span class="sxs-lookup"><span data-stu-id="e37cb-134">- `http://schemas.microsoft.com/Edi/X12#X12_<997 or TA1>_Root` (for an X12 acknowledgment)</span></span><br /><br /> <span data-ttu-id="e37cb-135">- `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root` (EDIFACT 受信確認) を</span><span class="sxs-lookup"><span data-stu-id="e37cb-135">- `http://schemas.microsoft.com/Edi/Efact#Efact_Contrl_Root` (for an EDIFACT acknowledgment)</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="e37cb-136">前提条件</span><span class="sxs-lookup"><span data-stu-id="e37cb-136">Prerequisites</span></span>  
 <span data-ttu-id="e37cb-137">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e37cb-137">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
##  <a name="BKMK_Proc"></a> <span data-ttu-id="e37cb-138">送信ポートを動的にメッセージを BizTalk Server AS2 の送信を構成</span><span class="sxs-lookup"><span data-stu-id="e37cb-138">To configure BizTalk Server to send AS2 messages over a dynamic send port</span></span>  
  
1. <span data-ttu-id="e37cb-139">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、前のように構成された、動的な一方向の送信ポート (MDN が要求されていない場合) または動的な送信請求応答の送信ポート (MDN が要求されている場合) を作成します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-139">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a dynamic one-way send port (if an MDN is not requested) or a dynamic solicit response send port (if an MDN is requested) with the above configuration.</span></span>  
  
2. <span data-ttu-id="e37cb-140">このメッセージに該当するアグリーメントに対して、AS2 プロパティおよび EDI プロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e37cb-140">For the agreement that applies to this message, set the AS2 and EDI properties required.</span></span>  
  
3. <span data-ttu-id="e37cb-141">次のプロパティをメッセージ コンテキストに昇格します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-141">Promote the following properties to the message context:</span></span>  
  
   -   `BTS.MessageType`  
  
   -   `EdiIntAS.MessageID`  
  
4. <span data-ttu-id="e37cb-142">次のプロパティをメッセージ コンテキストに書き込む機能をバックエンド アプリケーションに追加し、プロパティに適切な値を設定します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-142">Add functionality to a backend application to write the following properties to the message context, setting them to the appropriate values:</span></span>  
  
   -   `EdiIntAS.AS2To`  
  
   -   `BTS.OutboundTransportLocation`  
  
   -   `HTTP.EnableChunkedEncoding`  
  
   -   `BTS.EncryptionCert`  
  
   > [!NOTE]
   >  <span data-ttu-id="e37cb-143">動的送信ポートが正しく機能するように、`AS2To` および `OutboundTransportLocation` の各コンテキスト プロパティをメッセージ コンテキストに書き込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="e37cb-143">The `AS2To` context property and the `OutboundTransportLocation` context property must be written to the message context for the dynamic send port to function properly.</span></span> <span data-ttu-id="e37cb-144">`AS2To` プロパティは、送信メッセージの処理に使用するアグリーメントをポートで決定するために必要です。`OutboundTransportLocation` プロパティは、メッセージの送信先を送信ポートで決定するために必要です。</span><span class="sxs-lookup"><span data-stu-id="e37cb-144">The `AS2To` property is required for the port to determine the agreement to use in processing the outgoing message and the `OutboundTransportLocation` property is required for the send port to determine the destination of the message.</span></span> <span data-ttu-id="e37cb-145">詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-145">For more information, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
## <a name="functionality"></a><span data-ttu-id="e37cb-146">機能</span><span class="sxs-lookup"><span data-stu-id="e37cb-146">Functionality</span></span>  
 <span data-ttu-id="e37cb-147">動的送信ポートとパイプラインは次の操作を実行して、AS2 経由で同期 EDI メッセージ、非 EDI メッセージ、または受信確認を送信し、返された MDN を処理します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-147">The dynamic send port and pipeline does the following to send a synchronous EDI or non-EDI message or acknowledgment over AS2 and process the returned MDN:</span></span>  
  
- <span data-ttu-id="e37cb-148">EDI メッセージを送信する場合は、`BTS.MessageType` プロパティのフィルター処理を `http://schemas.microsoft.com/BizTalk/EDI/X12/2006 namespace` のメッセージ スキーマに設定して (たとえば、864 メッセージの場合は X12_00401_864)、EDI メッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-148">If sending an EDI message, picks up the EDI message by filtering on the property `BTS.MessageType` set to the message schema in the `http://schemas.microsoft.com/BizTalk/EDI/X12/2006 namespace` (for example, X12_00401_864 for an 864 message).</span></span>  
  
- <span data-ttu-id="e37cb-149">EDI 受信確認を送信する場合は、`BTS.MessageType` プロパティのフィルター処理を次の管理スキーマのいずれかに設定して、受信確認を取得します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-149">If sending an EDI acknowledgment, picks up the acknowledgment by filtering on the property `BTS.MessageType` set to one of the following control schema:</span></span>  
  
  -   <span data-ttu-id="e37cb-150">`http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root` (997 受信確認の場合)</span><span class="sxs-lookup"><span data-stu-id="e37cb-150">`http://schemas.microsoft.com/BizTalk/EDI/X12#X12_997_Root` for a 997 acknowledgment</span></span>  
  
  -   <span data-ttu-id="e37cb-151">`http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root` (TA1 受信確認の場合)</span><span class="sxs-lookup"><span data-stu-id="e37cb-151">`http://schemas.microsoft.com/BizTalk/EDI/X12#X12_TA1_Root` for a TA1 acknowledgment</span></span>  
  
  -   <span data-ttu-id="e37cb-152">`http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root` (CONTRL 受信確認の場合)</span><span class="sxs-lookup"><span data-stu-id="e37cb-152">`http://schemas.microsoft.com/BizTalk/EDI/Efact#Efact_Contrl_Root` for a CONTRL acknowledgment</span></span>  
  
- <span data-ttu-id="e37cb-153">非 EDI メッセージを送信する場合は、適切なフィルタを使用してメッセージを取得します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-153">If sending a non-EDI message, picks up the message using an appropriate filter.</span></span>  
  
- <span data-ttu-id="e37cb-154">AS2 メッセージを構築します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-154">Builds an AS2 message.</span></span> <span data-ttu-id="e37cb-155">このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-155">For more information about this process, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
  > [!NOTE]
  >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e37cb-156">は、http、smtp、ftp などの URL の形式から、動的送信ポートで使用するトランスポートの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-156">determines the transport type to be used by the dynamic send port from the format of the URL, i.e., http, smtp, ftp, etc.</span></span>  
  
- <span data-ttu-id="e37cb-157">メッセージや受信確認を送信ポートの送信先 URL にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="e37cb-157">Routes the message or acknowledgment to the destination URL for the send port.</span></span>  
  
- <span data-ttu-id="e37cb-158">メッセージや受信確認に対する MDN 応答を受信します (この処理が有効になっている送信請求応答の送信ポートの場合)。</span><span class="sxs-lookup"><span data-stu-id="e37cb-158">Receives the MDN response to the message or acknowledgment, if enabled and if a solicit-response send port.</span></span> <span data-ttu-id="e37cb-159">このプロセスの詳細については、次を参照してください。[受信 MDN の処理](../core/processing-an-incoming-mdn.md)します。</span><span class="sxs-lookup"><span data-stu-id="e37cb-159">For more information about this process, see [Processing an Incoming MDN](../core/processing-an-incoming-mdn.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e37cb-160">参照</span><span class="sxs-lookup"><span data-stu-id="e37cb-160">See Also</span></span>  
 [<span data-ttu-id="e37cb-161">AS2 ソリューションのポートの構成</span><span class="sxs-lookup"><span data-stu-id="e37cb-161">Configuring Ports for an AS2 Solution</span></span>](../core/configuring-ports-for-an-as2-solution.md)