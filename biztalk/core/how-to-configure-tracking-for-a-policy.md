---
title: ポリシーの追跡を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, tracking
- HAT, policies
- managing [policies], tracking
- tracking, policies
- managing [policies], configuring
- policies, configuring
- configuring [HAT tracking], policies
- tracking, configuring
ms.assetid: f126e541-c183-4544-8b9d-ca07d2af303e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f92e8555c0d644411c165284dd734eb94e6569e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980411"
---
# <a name="how-to-configure-tracking-for-a-policy"></a><span data-ttu-id="68801-102">ポリシーの追跡を構成する方法</span><span class="sxs-lookup"><span data-stu-id="68801-102">How to Configure Tracking for a Policy</span></span>
<span data-ttu-id="68801-103">このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して、ポリシーの追跡を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="68801-103">This topic describes how to use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administration console to configure tracking for a policy.</span></span> <span data-ttu-id="68801-104">管理コンソールの [グループ ハブ] ページのクエリ ビューでインスタンス データ、条件の結果、アクション、および議題の更新を表示するオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="68801-104">You can select options to view instance data, results of conditions, actions, and agenda updates in the query views of the administration console Group Hub page.</span></span>  
  
 <span data-ttu-id="68801-105">作成とクエリの使用に関する詳細については、[、BizTalk Server 管理コンソールを使用して](../core/using-the-biztalk-server-administration-console.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68801-105">For more information about creating and using queries, see [Using the BizTalk Server Administration Console](../core/using-the-biztalk-server-administration-console.md).</span></span> <span data-ttu-id="68801-106">メッセージとサービスのインスタンスの追跡の機能の詳細については[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を参照してください[追跡メッセージを表示し、インスタンス データ](../core/viewing-tracked-message-and-instance-data.md)します。</span><span class="sxs-lookup"><span data-stu-id="68801-106">For more information about the message and service instance  tracking features of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Viewing Tracked Message and Instance Data](../core/viewing-tracked-message-and-instance-data.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="68801-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="68801-107">Prerequisites</span></span>  
 <span data-ttu-id="68801-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68801-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="68801-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="68801-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-configure-tracking-for-a-policy"></a><span data-ttu-id="68801-110">ポリシーの追跡を構成するには</span><span class="sxs-lookup"><span data-stu-id="68801-110">To configure tracking for a policy</span></span>  
  
1. <span data-ttu-id="68801-111">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="68801-111">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="68801-112">コンソール ツリーで、BizTalk グループを展開し、ポリシーの追跡を構成する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="68801-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to configure tracking for a policy.</span></span>  
  
3. <span data-ttu-id="68801-113">クリックして**ポリシー**は、ポリシーを右クリックし、**プロパティ**、順にクリックします**追跡**します。</span><span class="sxs-lookup"><span data-stu-id="68801-113">Click **Policies**, right-click the policy, click **Properties**, and then click **Tracking**.</span></span>  
  
4. <span data-ttu-id="68801-114">次の表に示すように、必要な追跡オプションを選択し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="68801-114">Select the tracking options you want, as described in the following table, and then click **OK**.</span></span>  
  
   |<span data-ttu-id="68801-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="68801-115">Use this</span></span>|<span data-ttu-id="68801-116">目的</span><span class="sxs-lookup"><span data-stu-id="68801-116">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="68801-117">**ファクト アクティビティ**</span><span class="sxs-lookup"><span data-stu-id="68801-117">**Fast activity**</span></span>|<span data-ttu-id="68801-118">ポリシーが適用されるインスタンス データを追跡するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="68801-118">Select this check box to track the instance data on which the policy operates.</span></span>|  
   |<span data-ttu-id="68801-119">**条件の評価**</span><span class="sxs-lookup"><span data-stu-id="68801-119">**Condition evaluation**</span></span>|<span data-ttu-id="68801-120">選択したポリシーの条件の結果 (True または False) を追跡するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="68801-120">Select this check box to track the true/false results of conditions in the selected policy.</span></span>|  
   |<span data-ttu-id="68801-121">**ルールの実行**</span><span class="sxs-lookup"><span data-stu-id="68801-121">**Rule firings**</span></span>|<span data-ttu-id="68801-122">ポリシーの結果として開始されたアクションを追跡するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="68801-122">Select this check box to track the actions started as a result of the policy.</span></span>|  
   |<span data-ttu-id="68801-123">**議題の更新**</span><span class="sxs-lookup"><span data-stu-id="68801-123">**Agenda updates**</span></span>|<span data-ttu-id="68801-124">議題に加えられた変更を追跡するには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="68801-124">Select this check box to track updates to the agenda.</span></span> <span data-ttu-id="68801-125">議題とは、"True" が設定されており実行が必要なアクションの一覧です。</span><span class="sxs-lookup"><span data-stu-id="68801-125">The agenda contains a list of actions that are "true" and need to fire.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68801-126">参照</span><span class="sxs-lookup"><span data-stu-id="68801-126">See Also</span></span>  
 [<span data-ttu-id="68801-127">ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="68801-127">Managing Policies</span></span>](../core/managing-policies.md)