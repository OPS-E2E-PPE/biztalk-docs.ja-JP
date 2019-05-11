---
title: 分散アクティビティの間のナビゲーションを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f8faf0a-eb06-4383-932d-4106306d6cf3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd43576f9571cd34aa69f6f666fca6777434cf4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341284"
---
# <a name="how-to-configure-navigation-between-distributed-activities"></a><span data-ttu-id="bab10-102">分散アクティビティ間のナビゲーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="bab10-102">How to Configure Navigation Between Distributed Activities</span></span>
<span data-ttu-id="bab10-103">分散ナビゲーションでは、リモートの BAM の展開に存在するアクティビティを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="bab10-103">Distributed navigation allows users to view activities that exist in remote BAM deployments.</span></span> <span data-ttu-id="bab10-104">1 台のコンピューターで BAM ポータルのユーザーが、BAM ポータルの別の配置でのアクティビティを表示できる分散ナビゲーションを有効にすると[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="bab10-104">When you enable distributed navigation, users of the BAM portal on one computer will be able to view activities in the BAM portal on another deployment of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="bab10-105">このトピックの手順では、次のシナリオでの分散ナビゲーションを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bab10-105">The procedure in this topic describes how to enable distributed navigation in the following scenario:</span></span>  
  
- <span data-ttu-id="bab10-106">営業部門は、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 1 のコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="bab10-106">A sales department with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployed on computer 1.</span></span>  
  
- <span data-ttu-id="bab10-107">出荷部門は、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2 のコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="bab10-107">A shipping department with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployed on computer 2.</span></span>  
  
- <span data-ttu-id="bab10-108">ビューには、1 コンピューターに展開された売上データというアクティビティと myBusinessView が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bab10-108">A view called myBusinessView with an activity called Sales Data deployed on computer 1.</span></span>  
  
- <span data-ttu-id="bab10-109">ビューには、コンピューター 2 にインストールされている、出荷データというアクティビティと myBusinessView が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="bab10-109">A view called myBusinessView with an activity called Shipping Data installed on computer 2.</span></span>  
  
- <span data-ttu-id="bab10-110">ビジネスの販売部門のビジネス ユーザーは、両方のコンピューターでアクティビティを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bab10-110">A business user in the sales department with a business need to see the activities on both computers.</span></span>  
  
### <a name="how-to-set-up-distributed-navigation-for-remote-activities"></a><span data-ttu-id="bab10-111">リモート アクティビティの分散ナビゲーションを設定する方法</span><span class="sxs-lookup"><span data-stu-id="bab10-111">How to set up distributed navigation for remote activities</span></span>  
  
1.  <span data-ttu-id="bab10-112">コンピューター 1 の管理者では、ビジネス ユーザーのコンピューター 1 の myBusinessView ビューへのアクセスを付与します。</span><span class="sxs-lookup"><span data-stu-id="bab10-112">The administrator of computer 1 grants the business user access to the myBusinessView view on computer 1.</span></span> <span data-ttu-id="bab10-113">次のように、bm.exe コマンドを使用する:**アカウントの追加-accountname:\<アカウント名\>-ビュー:** myBusinessView</span><span class="sxs-lookup"><span data-stu-id="bab10-113">You use the bm.exe command, as follows: **add-account -AccountName:\<account name\> -View:** myBusinessView</span></span>  
  
2.  <span data-ttu-id="bab10-114">コンピューター 1 の管理者では、次のように、有効にする の 参照 を実行して分散ナビゲーションを有効: **bm.exe 参照を有効にする TargetServer:** computer2 **- TargetDatabase:\<ターゲットデータベース\>**</span><span class="sxs-lookup"><span data-stu-id="bab10-114">The administrator on computer 1 enables distributed navigation by running the enable reference command, as follows: **bm.exe enable-reference -TargetServer:** computer2 **-TargetDatabase:\<target database\>**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bab10-115">通常 BAM Web サービスにアクセスするために部門間で使用されるアカウントは、別のコンピューター別になります。</span><span class="sxs-lookup"><span data-stu-id="bab10-115">Typically the account used between departments for BAM Web services access will be different on different computers.</span></span> <span data-ttu-id="bab10-116">そのため、このシナリオではコンピューター 1 の管理者必要があります追加コンピューター 1 の Web サービスの権限借用アカウント コンピューター 2 の BAM プライマリ インポート データベースの BAM_ManagementWS ロールにします。</span><span class="sxs-lookup"><span data-stu-id="bab10-116">Therefore, in this scenario the administrator of computer 1 must add the Web services Impersonation account of computer 1 to the BAM_ManagementWS role of the BAM Primary Import database for computer 2.</span></span> <span data-ttu-id="bab10-117">詳細についてを参照してください「の表示および変更するロールのメンバーシップ」 [ http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990)します。</span><span class="sxs-lookup"><span data-stu-id="bab10-117">For more information, see "Viewing and Modifying Role Memberships" at [http://go.microsoft.com/fwlink/?LinkId=66990](http://go.microsoft.com/fwlink/?LinkId=66990).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bab10-118">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="bab10-118">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
3.  <span data-ttu-id="bab10-119">コンピューター 2 の管理者では、ビジネス ユーザーのコンピューター 1 の手順で説明したように、BM.exe コマンドを使用して 2 の myBusinessView ビューへのアクセスを付与します。</span><span class="sxs-lookup"><span data-stu-id="bab10-119">The administrator of computer 2 grants the business user access to the myBusinessView view on computer 2 using the BM.exe command as noted in step 1.</span></span>  
  
## <a name="results-of-setting-up-distributed-navigation"></a><span data-ttu-id="bab10-120">分散ナビゲーションの設定の結果</span><span class="sxs-lookup"><span data-stu-id="bab10-120">Results of Setting Up Distributed Navigation</span></span>  
 <span data-ttu-id="bab10-121">分散ナビゲーションを有効にすると両方のコンピューターで、ビューに追加されたユーザーには、ホーム ポータルの [マイ ビュー] ペインで、両方のコンピューターに展開したビューのアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bab10-121">When distributed navigation is enabled the users added to the views on both computers will see the activities for the views deployed on both computers in the My Views pane of their home portal.</span></span> <span data-ttu-id="bab10-122">これらのユーザーは、リモートの展開でホストされているアクティビティをクリックしてと、シームレスに誘導されますポータルにアクティビティがホストされていること、および、既定のポータルにした場合と同じアクティビティを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="bab10-122">When these users click an activity that is hosted on a remote deployment, they are seamlessly directed to the portal on which that activity is hosted and they are able to view the activity as if it were on their default portal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bab10-123">双方向では、分散ナビゲーションを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bab10-123">Distributed navigation can be enabled in both directions.</span></span> <span data-ttu-id="bab10-124">リモート アクティビティを共有している両方のコンピューターで上記の手順を次には、分散ナビゲーションを使用するいずれかのコンピューター上のポータルのビジネス ユーザーができるようにします。</span><span class="sxs-lookup"><span data-stu-id="bab10-124">Following the procedure above on both computers that are sharing remote activities enables business users of the portals on either computer to use distributed navigation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab10-125">参照</span><span class="sxs-lookup"><span data-stu-id="bab10-125">See Also</span></span>  
 <span data-ttu-id="bab10-126">[リモート アクティビティの分散ナビゲーションを管理します。](../core/managing-distributed-navigation-of-remote-activities.md) </span><span class="sxs-lookup"><span data-stu-id="bab10-126">[Managing Distributed Navigation of Remote Activities](../core/managing-distributed-navigation-of-remote-activities.md) </span></span>  
 [<span data-ttu-id="bab10-127">BAM ポータル</span><span class="sxs-lookup"><span data-stu-id="bab10-127">BAM Portal</span></span>](../core/bam-portal.md)