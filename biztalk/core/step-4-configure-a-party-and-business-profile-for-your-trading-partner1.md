---
title: '手順 4: 取引、Partner1 のパーティとビジネス プロファイルの構成 |Microsoft ドキュメント'
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
ms.openlocfilehash: a7b8be8215b790e74a3c1a8ecd8324d62454c2ac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277418"
---
# <a name="step-4-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="db278-102">手順 4: 取引先のパーティとビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="db278-102">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>
<span data-ttu-id="db278-103">![手順 4. 9 の](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span><span class="sxs-lookup"><span data-stu-id="db278-103">![Step 4 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-4of9.gif "Step_4of9")</span></span>  
  
 <span data-ttu-id="db278-104">このステップでは、取引先が 850 メッセージを自組織に送信し、それに対する 997 受信確認メッセージを受信するように、取引先 Fabrikam のパーティおよびビジネス プロファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="db278-104">In this step, you configure a party and business profile for your trading partner Fabrikam to send an 850 message to your organization and receive a 997 acknowledgment message in return.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="db278-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="db278-105">Prerequisites</span></span>  
 <span data-ttu-id="db278-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="db278-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-a-party-and-business-profile-for-your-trading-partner"></a><span data-ttu-id="db278-107">取引先のパーティとビジネス プロファイルを構成するには</span><span class="sxs-lookup"><span data-stu-id="db278-107">To configure a party and business profile for your trading partner</span></span>  
  
1.  <span data-ttu-id="db278-108">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール をクリックして**開始**をポイントして、**すべてのプログラム**をポイントして、 **Microsoft BizTalk Server**をクリックし、**BizTalk Server 管理**です。</span><span class="sxs-lookup"><span data-stu-id="db278-108">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console by clicking **Start**, pointing to **All Programs**, pointing to **Microsoft BizTalk Server**, and then clicking **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="db278-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]の順に展開および**BizTalk グループ**です。</span><span class="sxs-lookup"><span data-stu-id="db278-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then expand **BizTalk Group**.</span></span> <span data-ttu-id="db278-110">右クリック**パーティ**、 をポイント**新規**、クリックして**パーティ**です。</span><span class="sxs-lookup"><span data-stu-id="db278-110">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
3.  <span data-ttu-id="db278-111">**パーティ プロパティ** ダイアログ ボックスで、入力**Fabrikam**で、**名前**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="db278-111">In the **Party Properties** dialog box, enter **Fabrikam** in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="db278-112">クリア、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="db278-112">Clear the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box.</span></span> <span data-ttu-id="db278-113">チェック ボックスをオフにすることを指定、パーティ (この場合、 **Fabrikam**) BizTalk Server をホストしていません。</span><span class="sxs-lookup"><span data-stu-id="db278-113">By clearing the check box you specify that the party (in this case, **Fabrikam**) does not host BizTalk Server.</span></span>  
  
5.  <span data-ttu-id="db278-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db278-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="db278-115">パーティ名を右クリックし、**新規**、クリックして**ビジネス プロファイル**です。</span><span class="sxs-lookup"><span data-stu-id="db278-115">Right-click the party name, point to **New**, and then click **Business Profile**.</span></span>  
  
7.  <span data-ttu-id="db278-116">**プロファイル プロパティ**ダイアログ ボックスの**全般** ページで、入力`Fabrikam_Profile`で、**名前**テキスト ボックス。</span><span class="sxs-lookup"><span data-stu-id="db278-116">In the **Profile Properties** dialog box, on the **General** page, enter `Fabrikam_Profile` in the **Name** text box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="db278-117">パーティを作成するときに、という名前のプロファイル*PartyName*_Profile が自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="db278-117">When you create a party, a profile named *PartyName*_Profile is automatically created.</span></span> <span data-ttu-id="db278-118">新しいプロファイルを作成する代わりに、このプロファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="db278-118">You can use this profile instead of creating a new one.</span></span> <span data-ttu-id="db278-119">プロファイルの名前を変更するプロファイルを右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="db278-119">To rename a profile, right-click the profile and select **Properties**.</span></span> <span data-ttu-id="db278-120">**全般** ページで、プロファイルの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="db278-120">In the **General** page, specify a name for the profile.</span></span>  
  
8.  <span data-ttu-id="db278-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db278-121">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="db278-122">次の手順</span><span class="sxs-lookup"><span data-stu-id="db278-122">Next Steps</span></span>  
 <span data-ttu-id="db278-123">受信場所を構成する (**fromTHEM_4010_850**)」の説明に従って、Fabrikam から 850 メッセージを受信する[手順 5: 受信ポートと受信場所を構成する](../core/step-5-configure-a-receive-port-and-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="db278-123">You configure the receive location (**fromTHEM_4010_850**) to receive the 850 message from Fabrikam, as described in [Step 5: Configure a Receive Port and Receive Location](../core/step-5-configure-a-receive-port-and-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db278-124">参照</span><span class="sxs-lookup"><span data-stu-id="db278-124">See Also</span></span>  
 [<span data-ttu-id="db278-125">EDI のプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="db278-125">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)