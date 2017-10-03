---
title: "手順 3: Organization1 用のパーティとビジネス プロファイルの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 849e5146-a82a-41f2-bb96-089841b2444d
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eff579959840f760449422ebbe7af35792e7cc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="eee40-102">手順 3: 組織のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="eee40-102">Step 3: Configure a Party and Business Profile for Your Organization</span></span>
<span data-ttu-id="eee40-103">![手順 9 3](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span><span class="sxs-lookup"><span data-stu-id="eee40-103">![Step 3 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-3of9.gif "Step_3of9")</span></span>  
  
 <span data-ttu-id="eee40-104">このステップでは、取引先から 850 メッセージを受信し、997 受信確認メッセージを返すように、組織のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="eee40-104">In this step, you configure a party and a business profile for your organization to receive an 850 message from your trading partner and return a 997 acknowledgment message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eee40-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="eee40-105">Prerequisites</span></span>  
 <span data-ttu-id="eee40-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eee40-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-organization"></a><span data-ttu-id="eee40-107">組織のパーティおよびビジネス プロファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="eee40-107">To configure a party and business profile for your organization</span></span>  
  
1.  <span data-ttu-id="eee40-108">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール をクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 **Microsoft BizTalk Server**をクリックし、**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="eee40-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to **Microsoft BizTalk Server**, and then clicking **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="eee40-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]の順に展開および**BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="eee40-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="eee40-110">右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="eee40-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3.  <span data-ttu-id="eee40-111">**パーティ プロパティ** ダイアログ ボックスで、入力**OrderSystem**で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="eee40-111">In the **Party Properties** dialog box, enter **OrderSystem** in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="eee40-112">選択、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="eee40-112">Select the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="eee40-113">チェック ボックスをオンにすることを指定、パーティ (この場合、 **OrderSystem**) も BizTalk Server をホストします。</span><span class="sxs-lookup"><span data-stu-id="eee40-113">By selecting the check box you specify that the party (in this case, **OrderSystem**) also hosts BizTalk Server.</span></span>  
  
5.  <span data-ttu-id="eee40-114">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eee40-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="eee40-115">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="eee40-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7.  <span data-ttu-id="eee40-116">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力`OrderSystem_Profile`で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="eee40-116">In the **Profile Properties** dialog box, on the **General** page, enter `OrderSystem_Profile` in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eee40-117">パーティを作成するときに、という名前のプロファイル*PartyName*_Profile が自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="eee40-117">When you create a party, a profile named *PartyName*_Profile is automatically created.</span></span> <span data-ttu-id="eee40-118">新しいプロファイルを作成する代わりに、このプロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eee40-118">You can use this profile instead of creating a new one.</span></span> <span data-ttu-id="eee40-119">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="eee40-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="eee40-120">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="eee40-120">In the **General** page, specify a name for the profile.</span></span>  
  
8.  <span data-ttu-id="eee40-121">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eee40-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eee40-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="eee40-122">Next Steps</span></span>  
 <span data-ttu-id="eee40-123">パートナー組織のパーティとビジネス プロファイルを構成する (**Fabrikam**)」の説明に従って、[手順 4:、取引先のパーティとビジネス プロファイルを構成する](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)です。</span><span class="sxs-lookup"><span data-stu-id="eee40-123">You configure a party and business profile for your partner organization (**Fabrikam**), as described in [Step 4: Configure a Party and Business Profile for Your Trading Partner](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee40-124">参照</span><span class="sxs-lookup"><span data-stu-id="eee40-124">See Also</span></span>  
 [<span data-ttu-id="eee40-125">EDI のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="eee40-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)