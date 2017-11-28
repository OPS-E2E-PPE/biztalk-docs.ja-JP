---
title: "チュートリアル 2: EDI インターフェイス開発チュートリアル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d10fb650-cbb9-41e5-a80d-06afd0513814
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cb84454d2570ae6833847b598b55af6cf7777e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-2-edi-interface-developer-tutorial"></a><span data-ttu-id="18b17-102">チュートリアル 2: EDI インターフェイス開発チュートリアル</span><span class="sxs-lookup"><span data-stu-id="18b17-102">Tutorial 2: EDI Interface Developer Tutorial</span></span>
<span data-ttu-id="18b17-103">このチュートリアルでは、インターフェイス開発シナリオで [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の EDI 機能を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="18b17-103">This tutorial demonstrates how to use the EDI functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in an Interface Developer scenario.</span></span>  
  
 <span data-ttu-id="18b17-104">**チュートリアルのシナリオ**</span><span class="sxs-lookup"><span data-stu-id="18b17-104">**Tutorial Scenario**</span></span>  
  
 <span data-ttu-id="18b17-105">このシナリオでは、取引先は ANSI X12 Version 4010 850 トランザクション セット (850 メッセージ) を使用して注文書を送信します。</span><span class="sxs-lookup"><span data-stu-id="18b17-105">In this scenario, your trading partner sends Purchase Orders to your company using the ANSI X12 Version 4010 850 Transaction Set (an 850 message).</span></span> <span data-ttu-id="18b17-106">社内では、内部アプリケーション、注文システムを使用して、発注書を処理します。</span><span class="sxs-lookup"><span data-stu-id="18b17-106">Your company uses an internal application, the Order System, to process purchase orders.</span></span>  
  
 <span data-ttu-id="18b17-107">インターフェイス開発者として、取引先から受信した 850 のメッセージと社内の注文システムとの間のインターフェイスを設計するとします。</span><span class="sxs-lookup"><span data-stu-id="18b17-107">You are an interface developer responsible for designing the interface between the 850 message you receive from your trading partner and your company’s internal Order System.</span></span> <span data-ttu-id="18b17-108">取引先は、送信する 850 メッセージごとに機能確認 (997) を要求します。</span><span class="sxs-lookup"><span data-stu-id="18b17-108">Your trading partner requires a Functional Acknowledgement (997) for each 850 message it sends.</span></span>  
  
 <span data-ttu-id="18b17-109">参照しやすいように、次の識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="18b17-109">For ease of reference, the following identifiers are used:</span></span>  
  
|<span data-ttu-id="18b17-110">Entity</span><span class="sxs-lookup"><span data-stu-id="18b17-110">Entity</span></span>|<span data-ttu-id="18b17-111">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="18b17-111">Identifier</span></span>|  
|------------|----------------|  
|<span data-ttu-id="18b17-112">自社</span><span class="sxs-lookup"><span data-stu-id="18b17-112">Your company</span></span>|<span data-ttu-id="18b17-113">OrderSystem</span><span class="sxs-lookup"><span data-stu-id="18b17-113">OrderSystem</span></span>|  
|<span data-ttu-id="18b17-114">取引先</span><span class="sxs-lookup"><span data-stu-id="18b17-114">Your trading partner</span></span>|<span data-ttu-id="18b17-115">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="18b17-115">Fabrikam</span></span>|  
  
 <span data-ttu-id="18b17-116">完成したソリューションにおけるメッセージ フローは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="18b17-116">The message flow in the completed solution will be as follows:</span></span>  
  
 <span data-ttu-id="18b17-117">![EDI インターフェイス開発チュートリアル メッセージ フロー](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")</span><span class="sxs-lookup"><span data-stu-id="18b17-117">![EDI Interface Developer Tutorial message flow](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")</span></span>  
  
 <span data-ttu-id="18b17-118">**メッセージ フロー**</span><span class="sxs-lookup"><span data-stu-id="18b17-118">**Message Flow**</span></span>  
  
 <span data-ttu-id="18b17-119">このチュートリアルのソリューションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="18b17-119">The solution in this tutorial will do the following:</span></span>  
  
1.  <span data-ttu-id="18b17-120">Fabrikam という取引先からフラット ファイル インターチェンジを受信します。</span><span class="sxs-lookup"><span data-stu-id="18b17-120">Receive a flat-file interchange from the trading partner Fabrikam.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="18b17-121">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="18b17-121">The events in this list may not occur in the order shown.</span></span>  
  
2.  <span data-ttu-id="18b17-122">EDI インターチェンジをそのスキーマに対して検証し、メッセージを XML に逆アセンブルして、メッセージ XML を MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="18b17-122">Validate the EDI interchange against its schema, disassemble the message into XML, and drop the message XML into the MessageBox.</span></span>  
  
3.  <span data-ttu-id="18b17-123">受信した EDI インターチェンジに対する 997 受信確認を生成して、MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="18b17-123">Generate a 997 acknowledgment to the received EDI interchange, and drop it in the MessageBox.</span></span>  
  
4.  <span data-ttu-id="18b17-124">一方向の送信ポートで 997 XML を取得し、997 EDI インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="18b17-124">Pick up the 997 XML by a one-way send port, and assemble the 997 EDI interchange.</span></span>  
  
5.  <span data-ttu-id="18b17-125">997 インターチェンジを Fabrikam に送信します。</span><span class="sxs-lookup"><span data-stu-id="18b17-125">Send the 997 interchange to Fabrikam.</span></span>  
  
6.  <span data-ttu-id="18b17-126">一方向の送信ポートで Msg XML を取得し、メッセージ EDI インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="18b17-126">Pick up the Msg XML by a one-way send port, and assemble the message EDI interchange.</span></span>  
  
7.  <span data-ttu-id="18b17-127">EDI インターチェンジを OrderSystem に送信します。</span><span class="sxs-lookup"><span data-stu-id="18b17-127">Send the EDI interchange to OrderSystem.</span></span>  
  
 <span data-ttu-id="18b17-128">**Configuration**</span><span class="sxs-lookup"><span data-stu-id="18b17-128">**Configuration**</span></span>  
  
 <span data-ttu-id="18b17-129">このチュートリアルでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="18b17-129">In this tutorial, you will do the following:</span></span>  
  
-   <span data-ttu-id="18b17-130">取引先から送信される 850 メッセージを予想して BizTalk を構築し、997 受信確認を送り返します。</span><span class="sxs-lookup"><span data-stu-id="18b17-130">Configure BizTalk to expect the 850 message from your trading partner and to send back a 997 acknowledgment</span></span>  
  
-   <span data-ttu-id="18b17-131">BizTalk マップを使用して、850 メッセージのデータを注文システムで必要な形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="18b17-131">Use a BizTalk map to convert the 850 message data into the format required by the Order System.</span></span> <span data-ttu-id="18b17-132">このマップは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK のチュートリアル ファイルに収録されています。</span><span class="sxs-lookup"><span data-stu-id="18b17-132">This map is provided in the tutorial files in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK.</span></span>  
  
-   <span data-ttu-id="18b17-133">850 メッセージの受信に使用する受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="18b17-133">Configure a receive port for receiving the 850 message.</span></span>  
  
-   <span data-ttu-id="18b17-134">OrderSystem に正しい形式で 850 メッセージを送信するように送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="18b17-134">Configure a send port to send the 850 message to OrderSystem in the correct format.</span></span>  
  
-   <span data-ttu-id="18b17-135">BizTalk で生成された 997 受信確認をルーティングして取引先の Fabrikam に返すため、これをサブスクライブするように送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="18b17-135">Configure a send port to subscribe to the BizTalk-generated 997 acknowledgment for routing back to the trading partner, Fabrikam.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18b17-136">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="18b17-136">In This Section</span></span>  
  
-   [<span data-ttu-id="18b17-137">手順 1: EDI インターフェイス開発チュートリアルの準備します。</span><span class="sxs-lookup"><span data-stu-id="18b17-137">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)  
  
-   [<span data-ttu-id="18b17-138">手順 2: 更新し、チュートリアルのソリューションを展開</span><span class="sxs-lookup"><span data-stu-id="18b17-138">Step 2: Update and Deploy the Tutorial Solution</span></span>](../core/step-2-update-and-deploy-the-tutorial-solution.md)  
  
-   [<span data-ttu-id="18b17-139">手順 3: 組織のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="18b17-139">Step 3: Configure a Party and Business Profile for Your Organization</span></span>](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
-   [<span data-ttu-id="18b17-140">手順 4: 取引先のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="18b17-140">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)  
  
-   [<span data-ttu-id="18b17-141">手順 5: 構成する受信ポートと受信場所</span><span class="sxs-lookup"><span data-stu-id="18b17-141">Step 5: Configure a Receive Port and Receive Location</span></span>](../core/step-5-configure-a-receive-port-and-receive-location.md)  
  
-   [<span data-ttu-id="18b17-142">手順 6: 組織にデータを送信する送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="18b17-142">Step 6: Configure a Send Port to Send Data to Your Organization</span></span>](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)  
  
-   [<span data-ttu-id="18b17-143">手順 7: 取引先に、受信確認を送信する送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="18b17-143">Step 7: Configure a Send Port to Send the Acknowledgment to Your Trading Partner</span></span>](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)  
  
-   [<span data-ttu-id="18b17-144">手順 8: 当事者間の取引先アグリーメントを構成します。</span><span class="sxs-lookup"><span data-stu-id="18b17-144">Step 8: Configure the Trading Partner Agreement between the Parties</span></span>](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)  
  
-   [<span data-ttu-id="18b17-145">手順 9: EDI ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="18b17-145">Step 9: Test the EDI Solution</span></span>](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="18b17-146">参照</span><span class="sxs-lookup"><span data-stu-id="18b17-146">See Also</span></span>  
 [<span data-ttu-id="18b17-147">BizTalk Server チュートリアル</span><span class="sxs-lookup"><span data-stu-id="18b17-147">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)