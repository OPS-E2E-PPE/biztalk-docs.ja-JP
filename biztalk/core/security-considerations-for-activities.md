---
title: 活動のセキュリティに関する考慮事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fc49afd-a1c3-4ac7-8b89-11be667221e2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26ea453b24ac3e8df25e7a4da98f27731f3828be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270058"
---
# <a name="security-considerations-for-activities"></a><span data-ttu-id="a4f77-102">アクティビティのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a4f77-102">Security Considerations for Activities</span></span>
<span data-ttu-id="a4f77-103">WCF アダプタの通信データを受信するときに使用するセキュリティ ロールは、他の BAM ソリューションで使用するものと同じです。</span><span class="sxs-lookup"><span data-stu-id="a4f77-103">The security roles you use when intercepting the WCF adapter are the same as those used for other BAM solutions.</span></span> <span data-ttu-id="a4f77-104">このため、WCF アダプタの通信データを受信するときは、使用するユーザーとライタ ロールの適切な選択にも注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4f77-104">The additional considerations for intercepting the WCF adapter involve selecting the correct user and event writer role to use.</span></span>  
  
 <span data-ttu-id="a4f77-105">WCF サービスおよび WCF アダプタの使用時には、すべての BAM 関連データが、選択したロールによって BAM プライマリ インポート データベースに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a4f77-105">When using WCF services and the WCF adapter, all BAM-related data is written to the BAM Primary Import database by the selected role.</span></span>  
  
 <span data-ttu-id="a4f77-106">適切なユーザー ロール構成の選択基準は、ソリューションのシナリオによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a4f77-106">You can select the proper user role configuration by assessing your solution scenario:</span></span>  
  
-   <span data-ttu-id="a4f77-107">多くの新しいサービスをさまざまなアクティビティによって追跡し、すべてのサービスを同じユーザー アカウントで実行する必要がある場合は、BAM_EVENT_WRITER スーパー ロールを使用して受信したイベントの書き込みを行うと便利です。</span><span class="sxs-lookup"><span data-stu-id="a4f77-107">If your solution requires many new services that are tracked by many different activities, and are all run under the same user account, it is advantageous to use the BAM_EVENT_WRITER super role to write the intercepted events.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4f77-108">この場合、ユーザーを BAM イベント ライタ スーパー ロールに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4f77-108">Users must be added to the BAM event writer super role.</span></span> <span data-ttu-id="a4f77-109">ユーザーをスーパー ロールに追加すると、そのユーザーがシステム内のすべてのアクティビティに書き込みを行うことができるようになるため、注意が必要です。</span><span class="sxs-lookup"><span data-stu-id="a4f77-109">When adding a user to the super role it is important to remember that the user will then be able to write to all the activities in the system.</span></span>  
  
-   <span data-ttu-id="a4f77-110">書き込み対象のイベントをより厳密に管理する必要がある場合は、アクティビティ固有のロールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4f77-110">If your solution requires greater control of the events written, then you should use activity-specific roles.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a4f77-111">この場合、ユーザーを各アクティビティに固有のイベント ライタ ロールに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4f77-111">Users must be added to the activity specific event writer role for each activity.</span></span>  
  
 <span data-ttu-id="a4f77-112">BAM イベント ライター ロールを構成する方法の詳細については、次を参照してください。[かを確認し、アクティビティ イベント ライター ロールを設定する方法](../core/how-to-determine-and-set-event-writer-roles-for-activities.md)です。</span><span class="sxs-lookup"><span data-stu-id="a4f77-112">For more information about configuring the BAM event writer roles, see [How to Determine and Set Event Writer Roles for Activities](../core/how-to-determine-and-set-event-writer-roles-for-activities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a4f77-113">BizTalk Application Users グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4f77-113">You must be a member of the BizTalk Application Users group.</span></span>  
  
 <span data-ttu-id="a4f77-114">IIS 使用時の偽装対策のために BAM WCF インターセプタを構成する場合に使用するユーザー アカウントを選択するときは、次のシナリオに基づいて判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4f77-114">When selecting the user account to use when configuring the BAM WCF interceptor for impersonation security under IIS you should consider the following scenarios:</span></span>  
  
-   <span data-ttu-id="a4f77-115">自己ホスト型: 実行可能ファイルで実行されているコンピューターを保持する WCF サービス開きます。</span><span class="sxs-lookup"><span data-stu-id="a4f77-115">Self-Hosted: An executable running on your computer that holds the WCF service open.</span></span>  
  
-   <span data-ttu-id="a4f77-116">WCF アダプター: を使用して作成したソリューション、 **Biztalk WCF サービス公開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="a4f77-116">WCF adapter: Solutions created using the **Biztalk WCF Service Publishing Wizard**.</span></span>  
  
-   <span data-ttu-id="a4f77-117">IIS でホストされる: WCF サービスを使用してアプリケーションを IIS でホストされているソリューションです。</span><span class="sxs-lookup"><span data-stu-id="a4f77-117">IIS hosted: A solution hosted in an IIS application using a WCF Service.</span></span>  
  
 <span data-ttu-id="a4f77-118">次の表を基準に、使用するアカウントを決定してください。</span><span class="sxs-lookup"><span data-stu-id="a4f77-118">Use the following table to help identify the account to use:</span></span>  
  
|<span data-ttu-id="a4f77-119">ソリューションの種類</span><span class="sxs-lookup"><span data-stu-id="a4f77-119">Solution type</span></span>|<span data-ttu-id="a4f77-120">使用するアカウント</span><span class="sxs-lookup"><span data-stu-id="a4f77-120">Account to use</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="a4f77-121">自己ホスト型</span><span class="sxs-lookup"><span data-stu-id="a4f77-121">Self-hosted</span></span>|<span data-ttu-id="a4f77-122">サービスをオープンな状態で格納する実行可能ファイルの実行に使用するアカウント。</span><span class="sxs-lookup"><span data-stu-id="a4f77-122">The account that is used to run the executable that will hold the service open.</span></span>|  
|<span data-ttu-id="a4f77-123">WCF アダプター</span><span class="sxs-lookup"><span data-stu-id="a4f77-123">WCF adapter</span></span>|<span data-ttu-id="a4f77-124">AppPool id を使用して: これは、受信場所が存在する Vroot に関連付けられた AppPool です。</span><span class="sxs-lookup"><span data-stu-id="a4f77-124">Use the AppPool identity: This is the AppPool associated with the Vroot that houses the receive location.</span></span> <span data-ttu-id="a4f77-125">使用すると、この id が自動的に作成、 **BizTalk WCF サービス公開ウィザード**サイトを公開します。</span><span class="sxs-lookup"><span data-stu-id="a4f77-125">This identity is created automatically when you use the **BizTalk WCF Service Publishing Wizard** to publish the site.</span></span> <span data-ttu-id="a4f77-126">これは、IIS ホスト型ソリューションの特殊なケースと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="a4f77-126">You can consider this a special case of the IIS-hosted solution.</span></span>|  
|<span data-ttu-id="a4f77-127">IIS ホスト型</span><span class="sxs-lookup"><span data-stu-id="a4f77-127">IIS-hosted</span></span>|<span data-ttu-id="a4f77-128">WCF サービスの VRoot/Application を実行する AppPool ユーザーの ID。</span><span class="sxs-lookup"><span data-stu-id="a4f77-128">The identity of the AppPool user running the WCF service VRoot/Application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4f77-129">参照</span><span class="sxs-lookup"><span data-stu-id="a4f77-129">See Also</span></span>  
 [<span data-ttu-id="a4f77-130">BAM インターセプタのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a4f77-130">Security Considerations for BAM Interceptors</span></span>](../core/security-considerations-for-bam-interceptors.md)