---
title: '手順 3: Organization2 のパーティとビジネス プロファイルの構成 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 024d1ec7-237a-43cb-8159-90f9c71a670e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 809c8bd4080a7d2ddf14d9c84e98c050e198e6cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000363"
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="ef77b-102">手順 3: 組織のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="ef77b-102">Step 3: Configure a Party and Business Profile for Your Organization</span></span>
<span data-ttu-id="ef77b-103">![手順 3/11](../core/media/tut-step3-of-11.gif "Tut_Step3_of_11")</span><span class="sxs-lookup"><span data-stu-id="ef77b-103">![Step 3 of 11](../core/media/tut-step3-of-11.gif "Tut_Step3_of_11")</span></span>  
  
 <span data-ttu-id="ef77b-104">このステップでは、取引先から 864 メッセージを受信し、997 受信確認メッセージと非同期 MDN を返すように、組織のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="ef77b-104">In this step, you configure a party and a business profile for your organization to receive an 864 message from your trading partner and return a 997 acknowledgment message and an asynchronous MDN.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ef77b-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="ef77b-105">Prerequisites</span></span>  
 <span data-ttu-id="ef77b-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef77b-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="ef77b-107">組織のパーティおよびビジネス プロファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="ef77b-107">To configure a party and business profile for your organization</span></span>  
  
1. <span data-ttu-id="ef77b-108">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールをクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリックし、 **BizTalk Server 管理コンソール**.</span><span class="sxs-lookup"><span data-stu-id="ef77b-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then clicking **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="ef77b-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、順に展開**BizTalk グループ**します。</span><span class="sxs-lookup"><span data-stu-id="ef77b-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="ef77b-110">右クリック**パーティ**、 をポイント**新規**、 をクリックし、**パーティ**します。</span><span class="sxs-lookup"><span data-stu-id="ef77b-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3. <span data-ttu-id="ef77b-111">**パーティ プロパティ** ダイアログ ボックスに、入力**Contoso**で、**名前**フィールド。</span><span class="sxs-lookup"><span data-stu-id="ef77b-111">In the **Party Properties** dialog box, enter **Contoso** in the **Name** field.</span></span>  
  
4. <span data-ttu-id="ef77b-112">選択、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="ef77b-112">Select the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="ef77b-113">指定するチェック ボックスをオン、パーティ (この場合、 **Contoso**) も BizTalk Server をホストします。</span><span class="sxs-lookup"><span data-stu-id="ef77b-113">By selecting the check box you specify that the party (in this case, **Contoso**) also hosts BizTalk Server.</span></span>  
  
5. <span data-ttu-id="ef77b-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef77b-114">Click **OK**.</span></span>  
  
6. <span data-ttu-id="ef77b-115">パーティ名を右クリックし、[**新規**、] をクリックし、**ビジネス プロファイル**します。</span><span class="sxs-lookup"><span data-stu-id="ef77b-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7. <span data-ttu-id="ef77b-116">**プロファイル プロパティ**] ダイアログ ボックスの [、**全般**ページで、入力`Contoso_Profile`で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="ef77b-116">In the **Profile Properties** dialog box, on the **General** page, enter `Contoso_Profile` in the **Name** text box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ef77b-117">パーティを作成すると、プロファイルも作成されます。</span><span class="sxs-lookup"><span data-stu-id="ef77b-117">When you create a party, a profile is also created.</span></span> <span data-ttu-id="ef77b-118">新しいプロファイルを作成する代わりに、そのプロファイルの名前を変更して使用できます。</span><span class="sxs-lookup"><span data-stu-id="ef77b-118">You can rename and use that profile instead of creating a new one.</span></span> <span data-ttu-id="ef77b-119">プロファイルの名前を変更するには、プロファイルを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="ef77b-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="ef77b-120">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ef77b-120">In the **General** page, specify a name for the profile.</span></span>  
  
8. <span data-ttu-id="ef77b-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ef77b-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="ef77b-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="ef77b-122">Next Steps</span></span>  
 <span data-ttu-id="ef77b-123">パートナー組織のパーティとビジネス プロファイルを構成する (**Fabrikam**)」の説明に従って、[手順 4: パーティとビジネス プロファイル、取引先パートナーを構成](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)します。</span><span class="sxs-lookup"><span data-stu-id="ef77b-123">You configure a party and business profile for your partner organization (**Fabrikam**), as described in [Step 4: Configure a Party and Business Profile for Your Trading Partner](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef77b-124">参照</span><span class="sxs-lookup"><span data-stu-id="ef77b-124">See Also</span></span>  
 [<span data-ttu-id="ef77b-125">EDI のプロパティの構成</span><span class="sxs-lookup"><span data-stu-id="ef77b-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)