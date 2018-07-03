---
title: '手順 4: 取引先、Partner1 のパーティとビジネス プロファイルの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db50d0f6-e838-4e92-8548-a63a2c445d55
caps.latest.revision: 40
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa53034af1a07ca55574e2e37eecb7c0875f8a2e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989683"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="2e713-102">手順 4: 取引先のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="2e713-102">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>
<span data-ttu-id="2e713-103">![手順 9 の 4](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span><span class="sxs-lookup"><span data-stu-id="2e713-103">![Step 4 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span></span>  
  
 <span data-ttu-id="2e713-104">このステップでは、取引先が 850 メッセージを自組織に送信し、それに対する 997 受信確認メッセージを受信するように、取引先 Fabrikam のパーティおよびビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="2e713-104">In this step, you configure a party and business profile for your trading partner Fabrikam to send an 850 message to your organization and receive a 997 acknowledgment message in return.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2e713-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="2e713-105">Prerequisites</span></span>  
 <span data-ttu-id="2e713-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e713-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="2e713-107">取引先のパーティとビジネス プロファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="2e713-107">To configure a party and business profile for your trading partner</span></span>  
  
1. <span data-ttu-id="2e713-108">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 **Microsoft BizTalk Server**をクリックし、**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="2e713-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to **Microsoft BizTalk Server**, and then clicking **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="2e713-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="2e713-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="2e713-110">右クリック**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="2e713-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3. <span data-ttu-id="2e713-111">**パーティ プロパティ** ダイアログ ボックスに、入力**Fabrikam**で、**名前**フィールド。</span><span class="sxs-lookup"><span data-stu-id="2e713-111">In the **Party Properties** dialog box, enter **Fabrikam** in the **Name** field.</span></span>  
  
4. <span data-ttu-id="2e713-112">クリア、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="2e713-112">Clear the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="2e713-113">指定する チェック ボックスをオフにすると、パーティ (この場合、 **Fabrikam**) BizTalk Server をホストしていません。</span><span class="sxs-lookup"><span data-stu-id="2e713-113">By clearing the check box you specify that the party (in this case, **Fabrikam**) does not host BizTalk Server.</span></span>  
  
5. <span data-ttu-id="2e713-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e713-114">Click **OK**.</span></span>  
  
6. <span data-ttu-id="2e713-115">パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="2e713-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7. <span data-ttu-id="2e713-116">**プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力`Fabrikam_Profile`で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="2e713-116">In the **Profile Properties** dialog box, on the **General** page, enter `Fabrikam_Profile` in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2e713-117">プロファイルがという名前のパーティを作成するときに*PartyName*(_p) が自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="2e713-117">When you create a party, a profile named *PartyName*_Profile is automatically created.</span></span> <span data-ttu-id="2e713-118">新しいプロファイルを作成する代わりに、このプロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2e713-118">You can use this profile instead of creating a new one.</span></span> <span data-ttu-id="2e713-119">プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="2e713-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="2e713-120">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e713-120">In the **General** page, specify a name for the profile.</span></span>  
  
8. <span data-ttu-id="2e713-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e713-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2e713-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="2e713-122">Next Steps</span></span>  
 <span data-ttu-id="2e713-123">受信場所を構成する (**fromTHEM_4010_850**)」の説明に従って、Fabrikam から 850 メッセージを受信する[手順 5: 受信ポートと受信場所構成](../core/step-5-configure-a-receive-port-and-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="2e713-123">You configure the receive location (**fromTHEM_4010_850**) to receive the 850 message from Fabrikam, as described in [Step 5: Configure a Receive Port and Receive Location](../core/step-5-configure-a-receive-port-and-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e713-124">参照</span><span class="sxs-lookup"><span data-stu-id="2e713-124">See Also</span></span>  
 [<span data-ttu-id="2e713-125">EDI のプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="2e713-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)