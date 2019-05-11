---
title: AS2 BizTalk Server での処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0027d3db-24a5-459d-9f4e-a75f49d31d82
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea65fea589d0d5bdd69de1e9fcd762c27e6b28c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358885"
---
# <a name="as2-processing-in-biztalk-server"></a><span data-ttu-id="e5857-102">BizTalk Server での AS2 処理</span><span class="sxs-lookup"><span data-stu-id="e5857-102">AS2 Processing in BizTalk Server</span></span>
<span data-ttu-id="e5857-103">このトピックでは、AS2 メッセージの受信側と送信側の処理、および取引先アグリーメントが AS2 メッセージングにどのように役立つかの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5857-103">This topic provides an overview of receive-side and send-side processing of AS2 messages, and how trading partner agreements can help achieve AS2 messaging.</span></span>  
  
## <a name="trading-partner-agreements-for-as2-processing"></a><span data-ttu-id="e5857-104">AS2 処理用の取引先アグリーメント</span><span class="sxs-lookup"><span data-stu-id="e5857-104">Trading Partner Agreements for AS2 Processing</span></span>  
 <span data-ttu-id="e5857-105">取引先アグリーメントは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] における AS2 のサポートで重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="e5857-105">Trading partner agreements play a key role in AS2 support in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="e5857-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] における AS2 処理に関連したほとんどの構成機能および管理機能は、ビジネス プロファイル間の取引先アグリーメントを構成することによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-106">Most configuration and administrative functions related to AS2 processing in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are performed by configuring the trading partner agreements between business profiles.</span></span> <span data-ttu-id="e5857-107">アグリーメントには、両方の取引先の特定のビジネス プロファイルから、共通する双方向のメッセージ処理プロパティがまとめられます。</span><span class="sxs-lookup"><span data-stu-id="e5857-107">Agreements bring together common bi-directional message processing properties from specific business profiles of both partners.</span></span> <span data-ttu-id="e5857-108">アグリーメントは、各ビジネス プロファイルに対して定義されたプロトコル設定に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-108">Agreements are built upon the protocol settings defined for each business profile.</span></span> <span data-ttu-id="e5857-109">2 つのビジネス プロファイル間に取引先アグリーメントを実装するには、メッセージを交換する各ビジネス プロファイルのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e5857-109">You implement a trading partner agreement between two business profiles by defining properties for each business profile that will be exchanging messages.</span></span> <span data-ttu-id="e5857-110">取引先管理 (TPM) ユーザー インターフェイスで、AS2 メッセージ受信者と AS2 メッセージ送信者として各ビジネス プロファイルのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e5857-110">You set properties for each business profile as an AS2 message receiver and an AS2 message sender in the Trading Partner Management (TPM) user interface.</span></span> <span data-ttu-id="e5857-111">TPM の画面はでは、**パーティ**のノード、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="e5857-111">The TPM screens are in the **Parties** node of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="e5857-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、開発者でなくても AS2 処理を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e5857-112">You do not have to be a developer to configure AS2 processing in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="e5857-113">AS2 プロパティは、ビジネス プロファイルの「トランスポート プロトコル設定」の一部として、または取引先アグリーメントに AS2 設定を直接指定することによって、指定できます。</span><span class="sxs-lookup"><span data-stu-id="e5857-113">You can specify the AS2 properties as part of the “transport protocol settings” for a business profile or by directly specifying the AS2 settings in the trading partner agreement.</span></span> <span data-ttu-id="e5857-114">プロトコル設定の詳細については、次を参照してください。[プロトコル設定](../core/protocol-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5857-114">For more information about the protocol settings, see [Protocol Settings](../core/protocol-settings.md).</span></span> <span data-ttu-id="e5857-115">契約の詳細については、次を参照してください。[取引先アグリーメント](../core/trading-partner-agreement.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5857-115">For more information about agreements, see [Trading Partner Agreement](../core/trading-partner-agreement.md).</span></span>  <span data-ttu-id="e5857-116">次の AS2 機能を構成するには、AS2 固有のプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="e5857-116">You configure the following AS2 functionality by setting the AS2-specific properties:</span></span>  
  
- <span data-ttu-id="e5857-117">否認不可ストレージ オプションの選択</span><span class="sxs-lookup"><span data-stu-id="e5857-117">Select non-repudiation storage options</span></span>  
  
- <span data-ttu-id="e5857-118">送信メッセージの署名、圧縮、または暗号化の各プロパティの指定</span><span class="sxs-lookup"><span data-stu-id="e5857-118">Specify signing, compression, or encryption properties for outgoing messages</span></span>  
  
- <span data-ttu-id="e5857-119">送信メッセージの MDN の要求</span><span class="sxs-lookup"><span data-stu-id="e5857-119">Request MDNs for outgoing messages</span></span>  
  
- <span data-ttu-id="e5857-120">AS2 メッセージのヘッダーで署名、圧縮、暗号化、および MDN の各プロパティをオーバーライドすることによる着信 MDN のプロパティの設定</span><span class="sxs-lookup"><span data-stu-id="e5857-120">Set properties for incoming MDNs by overriding the signing, compression, encryption, and MDN properties in the header of the AS2 message.</span></span>  
  
  <span data-ttu-id="e5857-121">詳細については、どの取引先のパートナー アグリーメント AS2 処理に役立つ、次を参照してください。 [AS2 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-as2-processing.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5857-121">For more information about how trading partner agreements help in AS2 processing, see [The Role of Agreements in AS2 Processing](../core/the-role-of-agreements-in-as2-processing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5857-122">EDI 処理と異なり、AS2 処理にはグローバル プロパティはありません。</span><span class="sxs-lookup"><span data-stu-id="e5857-122">There are no global properties for AS2 processing, as there are for EDI processing.</span></span>  
  
## <a name="as2-receive-side-processing"></a><span data-ttu-id="e5857-123">受信側の AS2 処理</span><span class="sxs-lookup"><span data-stu-id="e5857-123">AS2 Receive-Side Processing</span></span>  
 <span data-ttu-id="e5857-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で AS2 メッセージを受信すると、AS2 受信パイプラインでメッセージが処理されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-124">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an AS2 message, it processes the message in an AS2 receive pipeline.</span></span> <span data-ttu-id="e5857-125">AS2 (AS2EdiReceive) 経由で EDI メッセージを受信するパイプラインがあり、AS2 処理と EDI 処理の両方が実行されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-125">There is a pipeline for receiving an EDI message over AS2 (AS2EdiReceive), which performs both AS2 and EDI processing.</span></span> <span data-ttu-id="e5857-126">もう 1 つのパイプライン (AS2Receive) は、AS2 経由で受信した非 EDI メッセージの AS2 処理のみを行います。</span><span class="sxs-lookup"><span data-stu-id="e5857-126">Another pipeline (AS2Receive) performs only AS2 processing for non-EDI messages received over AS2.</span></span>  
  
 <span data-ttu-id="e5857-127">受信側の AS2 処理には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5857-127">AS2 receive-side processing includes the following:</span></span>  
  
- <span data-ttu-id="e5857-128">取引先アグリーメント参照</span><span class="sxs-lookup"><span data-stu-id="e5857-128">Trading partner agreement lookup</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="e5857-129">以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パーティの定義にアグリーメントの定義も含まれていました。</span><span class="sxs-lookup"><span data-stu-id="e5857-129">In the previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a party definition also included the agreement definition.</span></span> <span data-ttu-id="e5857-130">そのため、受信パイプラインがパーティのプロパティを検索する場合は、パーティの定義内でアグリーメント定義を内部的に検索してから、必要に応じてメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="e5857-130">So, when the receive pipeline looked up the party properties, it would internally look for the agreement definition within the party definition and then process the messages accordingly.</span></span> <span data-ttu-id="e5857-131">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パーティ (取引先) は取引先アグリーメントとは異なるため、取引先アグリーメントだけが検索されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-131">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], because the party (or trading partner) is distinct from the trading partner agreement, the receive pipeline looks for the trading partner agreement specifically.</span></span>  
  > 
  > [!NOTE]
  >  <span data-ttu-id="e5857-132">メッセージが解決されるすべてのアグリーメントが無効になっている場合、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-132">If all the agreements that a message resolves to are disabled, the message will be suspended.</span></span>  <span data-ttu-id="e5857-133">また、イベント ログに警告が記録されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-133">A warning is also logged in the Event log.</span></span>  
  
- <span data-ttu-id="e5857-134">否認不可データベースへのメッセージのコピーの保存</span><span class="sxs-lookup"><span data-stu-id="e5857-134">Saving copies of the message in the non-repudiation database</span></span>  
  
- <span data-ttu-id="e5857-135">重複メッセージの確認</span><span class="sxs-lookup"><span data-stu-id="e5857-135">Check for duplicate messages</span></span>  
  
- <span data-ttu-id="e5857-136">複数のドキュメントを含むメッセージの処理</span><span class="sxs-lookup"><span data-stu-id="e5857-136">Processing messages containing multiple documents</span></span>  
  
- <span data-ttu-id="e5857-137">MIME エンベロープからのドキュメント ファイル名の取得</span><span class="sxs-lookup"><span data-stu-id="e5857-137">Retrieving a documents file name from the MIME envelope</span></span>  
  
- <span data-ttu-id="e5857-138">メッセージの解読</span><span class="sxs-lookup"><span data-stu-id="e5857-138">Decrypting the message</span></span>  
  
- <span data-ttu-id="e5857-139">メッセージの圧縮解除</span><span class="sxs-lookup"><span data-stu-id="e5857-139">Decompressing the message</span></span>  
  
- <span data-ttu-id="e5857-140">メッセージのデジタル署名の検証</span><span class="sxs-lookup"><span data-stu-id="e5857-140">Verifying the digital signature of the message</span></span>  
  
- <span data-ttu-id="e5857-141">HTTP 応答の生成</span><span class="sxs-lookup"><span data-stu-id="e5857-141">Generating an HTTP response</span></span>  
  
- <span data-ttu-id="e5857-142">MDN 応答の生成</span><span class="sxs-lookup"><span data-stu-id="e5857-142">Generating an MDN response</span></span>  
  
  <span data-ttu-id="e5857-143">受信側の AS2 処理を使用する場合は、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5857-143">Following are some considerations that you must make while using AS2 receive-side processing:</span></span>  
  
- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e5857-144">は、同期モードまたは非同期モードで MDN を返します。</span><span class="sxs-lookup"><span data-stu-id="e5857-144">returns an MDN in either synchronous or asynchronous mode.</span></span> <span data-ttu-id="e5857-145">MDN が非同期に返される場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は別の送信ポートを経由して MDN を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5857-145">If the MDN will be returned asynchronously, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must send it over a separate send port.</span></span>  
  
- <span data-ttu-id="e5857-146">非 EDI ファイル (XML 以外) を AS2 経由で受信し、非 EDI ペイロードの逆アセンブリを実行する必要がある場合、2 番目の受信パイプラインでループバック メカニズムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5857-146">When you receive a non-EDI file (not XML) over AS2, and you need to perform disassembly of the non-EDI payload, you will need to use requires a loopback mechanism with a second receive pipeline.</span></span> <span data-ttu-id="e5857-147">詳細については、次を参照してください。 [AS2 経由で受信した非 EDI メッセージの受信側の処理](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5857-147">For more information, see [Receive-Side Processing of an Incoming Non-EDI Message over AS2](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md).</span></span>  
  
- <span data-ttu-id="e5857-148">受信場所は HTTP アダプターのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5857-148">The receive location can only use the HTTP adapter.</span></span>  
  
- <span data-ttu-id="e5857-149">受信側の AS2 処理の詳細については、次を参照してください。[どのように BizTalk Server 受信 AS2 メッセージ](../core/how-biztalk-server-receives-as2-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5857-149">For more information about AS2 receive-side processing, see [How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md).</span></span>  
  
- <span data-ttu-id="e5857-150">受信パイプラインで AS2 逆アセンブラーによって実行される特定の処理の詳細については、次を参照してください。[受信 AS2 メッセージの処理](../core/processing-an-incoming-as2-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5857-150">For more information about the specific processing performed by the AS2 Disassembler in the receive pipeline, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="as2-send-side-processing"></a><span data-ttu-id="e5857-151">送信側の AS2 処理</span><span class="sxs-lookup"><span data-stu-id="e5857-151">AS2 Send-Side Processing</span></span>  
 <span data-ttu-id="e5857-152">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で送信 AS2 メッセージを生成および送信すると、AS2 送信パイプラインでメッセージが処理されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-152">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates and sends an outgoing AS2 message, it processes the message in an AS2 send pipeline.</span></span> <span data-ttu-id="e5857-153">AS2 (AS2EdiSend) 経由で EDI メッセージを送信するパイプラインがあり、AS2 処理と EDI 処理の両方が実行されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-153">There is a pipeline for sending an EDI message over AS2 (AS2EdiSend), which performs both AS2 and EDI processing.</span></span> <span data-ttu-id="e5857-154">もう 1 つのパイプライン (AS2Send) は、AS2 経由で送信された非 EDI メッセージの AS2 処理のみを行います。</span><span class="sxs-lookup"><span data-stu-id="e5857-154">Another pipeline (AS2Send) performs only AS2 processing for non-EDI messages sent over AS2.</span></span>  
  
 <span data-ttu-id="e5857-155">送信側の AS2 処理には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5857-155">AS2 send-side processing includes the following:</span></span>  
  
- <span data-ttu-id="e5857-156">取引先アグリーメント参照</span><span class="sxs-lookup"><span data-stu-id="e5857-156">Trading partner agreement lookup</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="e5857-157">以前のバージョンの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、パーティの定義にアグリーメントの定義も含まれていました。</span><span class="sxs-lookup"><span data-stu-id="e5857-157">In the previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a party definition also included the agreement definition.</span></span> <span data-ttu-id="e5857-158">そのため、送信パイプラインがパーティのプロパティを検索する場合は、パーティの定義内でアグリーメント定義を内部的に検索してから、必要に応じてメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="e5857-158">So, when the send pipeline looked up the party properties, it would internally look for the agreement definition within the party definition and then process the messages accordingly.</span></span> <span data-ttu-id="e5857-159">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パーティ (または取引先パートナー) は具体的には、次のように取引先パートナー アグリーメントの取引先アグリーメントの送信パイプラインは異なりますがあるため、します。</span><span class="sxs-lookup"><span data-stu-id="e5857-159">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], because the party (or trading partner) is distinct from the trading partner agreement, the send pipeline looks for the trading partner agreement specifically.</span></span>  
  > 
  > [!NOTE]
  >  <span data-ttu-id="e5857-160">メッセージが解決されるすべてのアグリーメントが無効になっている場合、メッセージは中断されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-160">If all the agreements that a message resolves to are disabled, the message will be suspended.</span></span>  <span data-ttu-id="e5857-161">また、イベント ログに警告が記録されます。</span><span class="sxs-lookup"><span data-stu-id="e5857-161">A warning is also logged in the Event log.</span></span>  
  
- <span data-ttu-id="e5857-162">否認不可データベースへのメッセージのコピーの保存</span><span class="sxs-lookup"><span data-stu-id="e5857-162">Saving copies of the message in the non-repudiation database</span></span>  
  
- <span data-ttu-id="e5857-163">AS2 エンベロープの適用</span><span class="sxs-lookup"><span data-stu-id="e5857-163">Applying an AS2 envelope</span></span>  
  
- <span data-ttu-id="e5857-164">複数のドキュメントの送信</span><span class="sxs-lookup"><span data-stu-id="e5857-164">Sending multiple documents</span></span>  
  
- <span data-ttu-id="e5857-165">MIME エンベロープの一部としての各ドキュメント ファイル名のソート</span><span class="sxs-lookup"><span data-stu-id="e5857-165">Storing each documents filename as part of the MIME envelope</span></span>  
  
- <span data-ttu-id="e5857-166">メッセージへの署名</span><span class="sxs-lookup"><span data-stu-id="e5857-166">Signing the message</span></span>  
  
  > [!NOTE]
  >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e5857-167">では、既定の署名証明書をオーバーライドし、アグリーメントで合意した証明書を代わりに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e5857-167">enables you to override the default signing certificate and instead use a certificate agreed upon in the agreement.</span></span> <span data-ttu-id="e5857-168">既定の送信メッセージの署名証明書をオーバーライドする方法の詳細については、次を参照してください。 [AS2 プロパティを設定する](../core/configuring-as2-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5857-168">For instructions on overriding default certificate for signing outgoing messages, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
- <span data-ttu-id="e5857-169">メッセージの圧縮</span><span class="sxs-lookup"><span data-stu-id="e5857-169">Compressing the message</span></span>  
  
- <span data-ttu-id="e5857-170">メッセージの暗号化</span><span class="sxs-lookup"><span data-stu-id="e5857-170">Encrypting the message</span></span>  
  
- <span data-ttu-id="e5857-171">MDN の MIC 値の計算</span><span class="sxs-lookup"><span data-stu-id="e5857-171">Computing an MIC value for the MDN</span></span>  
  
- <span data-ttu-id="e5857-172">着信 MDN の処理 (同期 MDN の場合)</span><span class="sxs-lookup"><span data-stu-id="e5857-172">Processing an incoming MDN (in the case of a synchronous MDN)</span></span>  
  
- <span data-ttu-id="e5857-173">メッセージの再送信 (MDN が受信されない場合)</span><span class="sxs-lookup"><span data-stu-id="e5857-173">Resending the message if no MDN is received</span></span>  
  
  <span data-ttu-id="e5857-174">受信側の AS2 処理を使用する場合は、次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5857-174">Following are some considerations that you must make while using AS2 receive-side processing:</span></span>  
  
- <span data-ttu-id="e5857-175">送信ポートは HTTP アダプターのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5857-175">The send port can only use the HTTP adapter.</span></span>  
  
- <span data-ttu-id="e5857-176">送信側の AS2 処理の詳細については、次を参照してください。[どのように BizTalk Server 送信 AS2 メッセージ](../core/how-biztalk-server-sends-as2-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5857-176">For more information about AS2 send-side processing, see [How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md).</span></span>  
  
- <span data-ttu-id="e5857-177">送信パイプラインで実行される特定の処理の詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5857-177">For more information about the specific processing performed in the send pipeline, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5857-178">参照</span><span class="sxs-lookup"><span data-stu-id="e5857-178">See Also</span></span>  
 <span data-ttu-id="e5857-179">[AS2 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-as2-processing.md) </span><span class="sxs-lookup"><span data-stu-id="e5857-179">[The Role of Agreements in AS2 Processing](../core/the-role-of-agreements-in-as2-processing.md) </span></span>  
 <span data-ttu-id="e5857-180">[BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="e5857-180">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="e5857-181">BizTalk Server が AS2 メッセージを送信する方法</span><span class="sxs-lookup"><span data-stu-id="e5857-181">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)