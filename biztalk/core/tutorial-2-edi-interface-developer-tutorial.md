---
title: チュートリアル 2:EDI インターフェイス開発チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10fb650-cbb9-41e5-a80d-06afd0513814
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1af388c62be4e23ba13d29f93567cdab76fdfb7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401724"
---
# <a name="tutorial-2-edi-interface-developer-tutorial"></a><span data-ttu-id="6a5d8-102">チュートリアル 2:EDI インターフェイス開発チュートリアル</span><span class="sxs-lookup"><span data-stu-id="6a5d8-102">Tutorial 2: EDI Interface Developer Tutorial</span></span>
<span data-ttu-id="6a5d8-103">このチュートリアルは、EDI 機能を使用する方法を示します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インターフェイス開発シナ リオでします。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-103">This tutorial demonstrates how to use the EDI functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in an Interface Developer scenario.</span></span>  
  
 <span data-ttu-id="6a5d8-104">**チュートリアルのシナリオ**</span><span class="sxs-lookup"><span data-stu-id="6a5d8-104">**Tutorial Scenario**</span></span>  
  
 <span data-ttu-id="6a5d8-105">このシナリオで、取引先は ANSI X12 を使用して、会社に注文書を送信 Version 4010 850 トランザクション セット (850 メッセージ)。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-105">In this scenario, your trading partner sends Purchase Orders to your company using the ANSI X12 Version 4010 850 Transaction Set (an 850 message).</span></span> <span data-ttu-id="6a5d8-106">会社が、注文システムの内部アプリケーションを使用して、発注書を処理します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-106">Your company uses an internal application, the Order System, to process purchase orders.</span></span>  
  
 <span data-ttu-id="6a5d8-107">取引先から受信する 850 メッセージと、会社の内部の注文システム間のインターフェイスの設計を担当するインターフェイス開発者としています。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-107">You are an interface developer responsible for designing the interface between the 850 message you receive from your trading partner and your company’s internal Order System.</span></span> <span data-ttu-id="6a5d8-108">取引先には、送信 850 メッセージごとの機能確認 (997) が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-108">Your trading partner requires a Functional Acknowledgement (997) for each 850 message it sends.</span></span>  
  
 <span data-ttu-id="6a5d8-109">参照しやすいように、次の識別子が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-109">For ease of reference, the following identifiers are used:</span></span>  
  
|<span data-ttu-id="6a5d8-110">Entity</span><span class="sxs-lookup"><span data-stu-id="6a5d8-110">Entity</span></span>|<span data-ttu-id="6a5d8-111">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="6a5d8-111">Identifier</span></span>|  
|------------|----------------|  
|<span data-ttu-id="6a5d8-112">会社</span><span class="sxs-lookup"><span data-stu-id="6a5d8-112">Your company</span></span>|<span data-ttu-id="6a5d8-113">OrderSystem</span><span class="sxs-lookup"><span data-stu-id="6a5d8-113">OrderSystem</span></span>|  
|<span data-ttu-id="6a5d8-114">取引先パートナー</span><span class="sxs-lookup"><span data-stu-id="6a5d8-114">Your trading partner</span></span>|<span data-ttu-id="6a5d8-115">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="6a5d8-115">Fabrikam</span></span>|  
  
 <span data-ttu-id="6a5d8-116">完成したソリューションにおけるメッセージ フローは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-116">The message flow in the completed solution will be as follows:</span></span>  
  
 <span data-ttu-id="6a5d8-117">![EDI インターフェイス開発チュートリアル メッセージ フロー](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")</span><span class="sxs-lookup"><span data-stu-id="6a5d8-117">![EDI Interface Developer Tutorial message flow](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")</span></span>  
  
 <span data-ttu-id="6a5d8-118">**メッセージ フロー**</span><span class="sxs-lookup"><span data-stu-id="6a5d8-118">**Message Flow**</span></span>  
  
 <span data-ttu-id="6a5d8-119">このチュートリアルでは、ソリューションは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-119">The solution in this tutorial will do the following:</span></span>  
  
1. <span data-ttu-id="6a5d8-120">Fabrikam 取引先からフラット ファイル インターチェンジを受信します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-120">Receive a flat-file interchange from the trading partner Fabrikam.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6a5d8-121">この一覧のイベントは、示されている順序で発生するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-121">The events in this list may not occur in the order shown.</span></span>  
  
2. <span data-ttu-id="6a5d8-122">EDI インターチェンジをそのスキーマに対して検証し、メッセージを XML に逆アセンブルして、メッセージ XML を MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-122">Validate the EDI interchange against its schema, disassemble the message into XML, and drop the message XML into the MessageBox.</span></span>  
  
3. <span data-ttu-id="6a5d8-123">受信した EDI インターチェンジに対する 997 受信確認を生成して、MessageBox にドロップします。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-123">Generate a 997 acknowledgment to the received EDI interchange, and drop it in the MessageBox.</span></span>  
  
4. <span data-ttu-id="6a5d8-124">一方向の送信ポートで 997 XML を取得し、997 EDI インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-124">Pick up the 997 XML by a one-way send port, and assemble the 997 EDI interchange.</span></span>  
  
5. <span data-ttu-id="6a5d8-125">997 インターチェンジを Fabrikam に送信します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-125">Send the 997 interchange to Fabrikam.</span></span>  
  
6. <span data-ttu-id="6a5d8-126">一方向の送信ポートで Msg XML を選択し、メッセージ EDI インターチェンジをアセンブルします。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-126">Pick up the Msg XML by a one-way send port, and assemble the message EDI interchange.</span></span>  
  
7. <span data-ttu-id="6a5d8-127">EDI インターチェンジを OrderSystem に送信します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-127">Send the EDI interchange to OrderSystem.</span></span>  
  
   <span data-ttu-id="6a5d8-128">**Configuration**</span><span class="sxs-lookup"><span data-stu-id="6a5d8-128">**Configuration**</span></span>  
  
   <span data-ttu-id="6a5d8-129">このチュートリアルでは、次の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-129">In this tutorial, you will do the following:</span></span>  
  
- <span data-ttu-id="6a5d8-130">BizTalk 取引先から 850 メッセージを期待し、997 受信確認を返信するを構成します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-130">Configure BizTalk to expect the 850 message from your trading partner and to send back a 997 acknowledgment</span></span>  
  
- <span data-ttu-id="6a5d8-131">BizTalk マップを使用して、850 メッセージ データを注文システムで必要な形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-131">Use a BizTalk map to convert the 850 message data into the format required by the Order System.</span></span> <span data-ttu-id="6a5d8-132">このマップは、チュートリアル ファイルで提供される、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-132">This map is provided in the tutorial files in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK.</span></span>  
  
- <span data-ttu-id="6a5d8-133">850 メッセージを受信するための受信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-133">Configure a receive port for receiving the 850 message.</span></span>  
  
- <span data-ttu-id="6a5d8-134">OrderSystem に正しい形式で 850 メッセージを送信する送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-134">Configure a send port to send the 850 message to OrderSystem in the correct format.</span></span>  
  
- <span data-ttu-id="6a5d8-135">BizTalk で生成された 997 受信確認を取引先 Fabrikam にルーティングをサブスクライブする送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-135">Configure a send port to subscribe to the BizTalk-generated 997 acknowledgment for routing back to the trading partner, Fabrikam.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a5d8-136">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="6a5d8-136">In This Section</span></span>  
  
-   [<span data-ttu-id="6a5d8-137">ステップ 1: EDI インターフェイス開発チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-137">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)  
  
-   [<span data-ttu-id="6a5d8-138">手順 2:更新し、チュートリアルのソリューションの展開</span><span class="sxs-lookup"><span data-stu-id="6a5d8-138">Step 2: Update and Deploy the Tutorial Solution</span></span>](../core/step-2-update-and-deploy-the-tutorial-solution.md)  
  
-   [<span data-ttu-id="6a5d8-139">ステップ 3:組織のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-139">Step 3: Configure a Party and Business Profile for Your Organization</span></span>](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
-   [<span data-ttu-id="6a5d8-140">手順 4:取引先のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-140">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)  
  
-   [<span data-ttu-id="6a5d8-141">手順 5:構成を受信ポートと受信場所</span><span class="sxs-lookup"><span data-stu-id="6a5d8-141">Step 5: Configure a Receive Port and Receive Location</span></span>](../core/step-5-configure-a-receive-port-and-receive-location.md)  
  
-   [<span data-ttu-id="6a5d8-142">手順 6:組織にデータを送信する送信ポートの構成します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-142">Step 6: Configure a Send Port to Send Data to Your Organization</span></span>](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)  
  
-   [<span data-ttu-id="6a5d8-143">手順 7:取引先に、受信確認を送信する送信ポートの構成します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-143">Step 7: Configure a Send Port to Send the Acknowledgment to Your Trading Partner</span></span>](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)  
  
-   [<span data-ttu-id="6a5d8-144">手順 8:当事者間で取引先アグリーメントを構成します。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-144">Step 8: Configure the Trading Partner Agreement between the Parties</span></span>](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)  
  
-   [<span data-ttu-id="6a5d8-145">手順 9:EDI ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="6a5d8-145">Step 9: Test the EDI Solution</span></span>](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="6a5d8-146">参照</span><span class="sxs-lookup"><span data-stu-id="6a5d8-146">See Also</span></span>  
 [<span data-ttu-id="6a5d8-147">BizTalk Server チュートリアル</span><span class="sxs-lookup"><span data-stu-id="6a5d8-147">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)