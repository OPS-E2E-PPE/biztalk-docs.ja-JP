---
title: BizTalk Server 管理者グループを管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Administrators group, user accounts
- BizTalk Administrators group
- user accounts, BizTalk Administrators group
- Windows Management Instrumentation (WMI), administering
- BizTalk Administrators group, privileges
- security, BizTalk Administrators group
- Administration Console [BizTalk Server], security
- Administration Console [BizTalk Server], administering
- BizTalk Administrators group, about BizTalk Administrators group
ms.assetid: 60ea689b-0b93-4fcc-b49c-6436e7be473f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7b22fff1ff8216021ba11038d5ee275f4dd0bb4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336712"
---
# <a name="how-to-manage-the-biztalk-server-administrators-group"></a><span data-ttu-id="e6f20-102">BizTalk Server 管理者グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="e6f20-102">How to Manage the BizTalk Server Administrators Group</span></span>
<span data-ttu-id="e6f20-103">BizTalk Server 管理者グループは、管理タスクを実行するために必要最小限の特権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="e6f20-103">The BizTalk Server Administrators group has the fewest privileges necessary to perform administrative tasks.</span></span> <span data-ttu-id="e6f20-104">BizTalk Server 管理コンソールまたは WMI プロバイダーを使用して管理タスクを実行できるように、BizTalk Server 管理者グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-104">You add users to the BizTalk Server Administrators group so that they can perform administrative tasks by using the BizTalk Server Administration Console or the WMI provider.</span></span> <span data-ttu-id="e6f20-105">削除することもユーザー、BizTalk Server 管理者グループから、BizTalk Server 管理コンソールまたは WMI プロバイダーを使用して管理タスクを実行するが不要になったときにします。</span><span class="sxs-lookup"><span data-stu-id="e6f20-105">You also remove users from the BizTalk Server Administrators group when they no longer need to perform administrative tasks by using the BizTalk Server Administration Console or the WMI provider.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e6f20-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="e6f20-106">Prerequisites</span></span>  
 <span data-ttu-id="e6f20-107">この手順を実行する管理者または Domain Admins グループのメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="e6f20-107">You must be a member of the Administrators or Domain Admins group to perform this procedure.</span></span>  
  
### <a name="to-add-users-to-the-local-biztalk-server-administrators-group"></a><span data-ttu-id="e6f20-108">ローカルの BizTalk Server 管理者グループにユーザーを追加するには</span><span class="sxs-lookup"><span data-stu-id="e6f20-108">To add users to the local BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="e6f20-109">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**コンピュータの管理**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-109">Click **Start**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="e6f20-110">展開**システム ツール**、展開**ローカル ユーザーとグループ**、 をクリックし、**グループ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e6f20-110">Expand **System Tools**, expand **Local Users and Groups**, and then click the **Groups** folder.</span></span> <span data-ttu-id="e6f20-111">詳細ウィンドウで、フォルダーの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6f20-111">The folder contents appear in the details pane.</span></span>  
  
3.  <span data-ttu-id="e6f20-112">詳細ウィンドウで次のようにクリックします。 **BizTalk Server 管理者**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-112">In the details pane, click **BizTalk Server Administrators**.</span></span>  
  
4.  <span data-ttu-id="e6f20-113">**アクション**メニューで、**すべてのタスク**、 をクリックし、**をグループに追加**。</span><span class="sxs-lookup"><span data-stu-id="e6f20-113">On the **Action** menu, point to **All Tasks**, and then click **Add to Group**.</span></span>  
  
5.  <span data-ttu-id="e6f20-114">**BizTalk Server 管理者のプロパティ**ダイアログ ボックスで、をクリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-114">In the **BizTalk Server Administrators Properties** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="e6f20-115">**検索**一覧で、ドメインまたはコンピューター名を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-115">In the **Look in** list, select your domain or computer name.</span></span>  
  
7.  <span data-ttu-id="e6f20-116">ユーザーおよびドメインまたは手順 6 で選択したコンピュータに関連付けられているコンピューターの一覧で、追加のユーザー アカウントを選択します。**追加**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="e6f20-116">In the list that contains the users and computers associated with the domain or computer you selected in step 6, select the user account to add, click **Add**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="e6f20-117">クリックして**OK**を閉じる、 **BizTalk Server 管理者のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e6f20-117">Click **OK** to close the **BizTalk Server Administrators Properties** dialog box.</span></span>  
  
### <a name="to-remove-users-from-local-the-biztalk-server-administrators-group"></a><span data-ttu-id="e6f20-118">ローカルの BizTalk Server 管理者グループからユーザーを削除するには</span><span class="sxs-lookup"><span data-stu-id="e6f20-118">To remove users from local the BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="e6f20-119">クリックして**開始**、 をポイント**管理ツール**、順にクリックします**コンピュータの管理**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-119">Click **Start**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="e6f20-120">展開**システム ツール**、展開**ローカル ユーザーとグループ**、 をクリックし、**グループ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="e6f20-120">Expand **System Tools**, expand **Local Users and Groups**, and then click the **Groups** folder.</span></span> <span data-ttu-id="e6f20-121">詳細ウィンドウで、フォルダーの内容が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e6f20-121">The folder contents appear in the details pane.</span></span>  
  
3.  <span data-ttu-id="e6f20-122">詳細ウィンドウで次のようにクリックします。 **BizTalk Server 管理者**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-122">In the details pane, click **BizTalk Server Administrators**.</span></span>  
  
4.  <span data-ttu-id="e6f20-123">**アクション** メニューのをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-123">On the **Action** menu, click **Properties**.</span></span>  
  
5.  <span data-ttu-id="e6f20-124">**BizTalk Server 管理者のプロパティ** ダイアログ ボックスで、ユーザー アカウントをクリックして、削除する場合、select**削除**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-124">In the **BizTalk Server Administrators Properties** dialog box, select the user account you want to remove, and then click **Remove**.</span></span>  
  
6.  <span data-ttu-id="e6f20-125">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f20-125">Click **OK**.</span></span>  
  
### <a name="to-add-users-to-the-domain-biztalk-server-administrators-group"></a><span data-ttu-id="e6f20-126">ドメインの BizTalk Server 管理者グループにユーザーを追加するには</span><span class="sxs-lookup"><span data-stu-id="e6f20-126">To add users to the domain BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="e6f20-127">Domain Admins アカウントを使用して、SQL Server データベースが参加しているドメイン コント ローラーにログオンします。</span><span class="sxs-lookup"><span data-stu-id="e6f20-127">Log on to the domain controller where the SQL Server databases are joined by using the Domain Admins account.</span></span>  
  
2.  <span data-ttu-id="e6f20-128">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**Active Directory ユーザーとコンピューター**に開始、 **Active Directory ユーザーとコンピューター**コンソール。</span><span class="sxs-lookup"><span data-stu-id="e6f20-128">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
    1.  <span data-ttu-id="e6f20-129">コンソール ツリーで、メンバーを追加する BizTalk Server 管理者グループを含むフォルダーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f20-129">In the console tree, click the folder that contains the BizTalk Server Administrators group to which you want to add a member.</span></span>  
  
    2.  <span data-ttu-id="e6f20-130">詳細ペインで、BizTalk Server 管理者グループを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-130">In the details pane, right-click the BizTalk Server Administrators group, and then click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="e6f20-131">**メンバー** ] タブで [**追加**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-131">On the **Members** tab, click **Add**.</span></span>  
  
    4.  <span data-ttu-id="e6f20-132">**を選択するオブジェクト名の入力**、ユーザーの名前を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-132">In **Enter the object names to select**, type the name of the user, and then click **OK**.</span></span>  
  
### <a name="to-remove-users-from-the-domain-biztalk-server-administrators-group"></a><span data-ttu-id="e6f20-133">ユーザー ドメインの BizTalk Server 管理者グループから削除するには</span><span class="sxs-lookup"><span data-stu-id="e6f20-133">To remove users from the domain BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="e6f20-134">ドメイン コント ローラーにログオンが SQL データベースは、Domain Admins アカウントを使用して結合されます。</span><span class="sxs-lookup"><span data-stu-id="e6f20-134">Log on to the domain controller where SQL databases are joined using the Domain Admins account.</span></span>  
  
2.  <span data-ttu-id="e6f20-135">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**Active Directory ユーザーとコンピューター**に開始、 **Active Directory ユーザーとコンピューター**コンソール。</span><span class="sxs-lookup"><span data-stu-id="e6f20-135">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
    1.  <span data-ttu-id="e6f20-136">コンソール ツリーで、メンバーを追加する BizTalk Server 管理者グループを含むフォルダーをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f20-136">In the console tree, click the folder that contains the BizTalk Server Administrators group to which you want to add a member.</span></span>  
  
    2.  <span data-ttu-id="e6f20-137">詳細ペインで、BizTalk Server 管理者グループを右クリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-137">In the details pane, right-click the BizTalk Server Administrators group, and then click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="e6f20-138">**メンバー**  タブをクリックしてをクリックし、削除、削除するメンバー**削除**します。</span><span class="sxs-lookup"><span data-stu-id="e6f20-138">On the **Members** tab, click the member you want to remove, and then click **Remove**.</span></span>  
  
    4.  <span data-ttu-id="e6f20-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6f20-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f20-140">参照</span><span class="sxs-lookup"><span data-stu-id="e6f20-140">See Also</span></span>  
 <span data-ttu-id="e6f20-141">[BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="e6f20-141">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="e6f20-142">[ホストの管理とサービス アカウント](../core/managing-hosts-and-service-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="e6f20-142">[Managing Hosts and Service Accounts](../core/managing-hosts-and-service-accounts.md) </span></span>  
 <span data-ttu-id="e6f20-143">[Windows グループとユーザー アカウントを管理するためのベスト プラクティス](../core/best-practices-for-managing-windows-groups-and-user-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="e6f20-143">[Best Practices for Managing Windows Groups and User Accounts](../core/best-practices-for-managing-windows-groups-and-user-accounts.md) </span></span>  
 <span data-ttu-id="e6f20-144">[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="e6f20-144">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="e6f20-145">Windows ループおよびユーザー アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="e6f20-145">Managing Windows Groups and User Accounts</span></span>](../core/managing-windows-groups-and-user-accounts.md)