---
title: "BizTalk Server 管理者グループを管理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fe92c9c43ccef242d8c14b5f1aa48e0b1a8d852
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-the-biztalk-server-administrators-group"></a><span data-ttu-id="8abce-102">BizTalk Server 管理者グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="8abce-102">How to Manage the BizTalk Server Administrators Group</span></span>
<span data-ttu-id="8abce-103">BizTalk Server 管理者グループには、管理タスクの実行に最低限必要な権限が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="8abce-103">The BizTalk Server Administrators group has the fewest privileges necessary to perform administrative tasks.</span></span> <span data-ttu-id="8abce-104">BizTalk Server 管理コンソールまたは WMI プロバイダを使用して管理タスクを実行できるようにするには、ユーザーを BizTalk Server 管理者グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="8abce-104">You add users to the BizTalk Server Administrators group so that they can perform administrative tasks by using the BizTalk Server Administration Console or the WMI provider.</span></span> <span data-ttu-id="8abce-105">また、BizTalk Server 管理コンソールまたは WMI プロバイダを使用して管理タスクを実行する必要がなくなった場合は、ユーザーを BizTalk Server 管理者グループから削除します。</span><span class="sxs-lookup"><span data-stu-id="8abce-105">You also remove users from the BizTalk Server Administrators group when they no longer need to perform administrative tasks by using the BizTalk Server Administration Console or the WMI provider.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8abce-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="8abce-106">Prerequisites</span></span>  
 <span data-ttu-id="8abce-107">ここで示す手順を実行するには、管理者グループまたはドメイン管理者グループのメンバである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8abce-107">You must be a member of the Administrators or Domain Admins group to perform this procedure.</span></span>  
  
### <a name="to-add-users-to-the-local-biztalk-server-administrators-group"></a><span data-ttu-id="8abce-108">ユーザーをローカルの BizTalk Server 管理者グループに追加するには</span><span class="sxs-lookup"><span data-stu-id="8abce-108">To add users to the local BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="8abce-109">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**コンピューターの管理**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-109">Click **Start**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="8abce-110">展開**システム ツール**、展開**ローカル ユーザーとグループ**、をクリックし、**グループ**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="8abce-110">Expand **System Tools**, expand **Local Users and Groups**, and then click the **Groups** folder.</span></span> <span data-ttu-id="8abce-111">フォルダの内容が詳細ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8abce-111">The folder contents appear in the details pane.</span></span>  
  
3.  <span data-ttu-id="8abce-112">詳細ペインでクリックして**BizTalk Server 管理者**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-112">In the details pane, click **BizTalk Server Administrators**.</span></span>  
  
4.  <span data-ttu-id="8abce-113">**アクション** メニューのをポイント**すべてのタスク**、クリックして**グループに追加**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-113">On the **Action** menu, point to **All Tasks**, and then click **Add to Group**.</span></span>  
  
5.  <span data-ttu-id="8abce-114">**BizTalk Server 管理者のプロパティ**ダイアログ ボックスで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-114">In the **BizTalk Server Administrators Properties** dialog box, click **Add**.</span></span>  
  
6.  <span data-ttu-id="8abce-115">**ファイルの場所**一覧で、ドメインまたはコンピューター名を選択します。</span><span class="sxs-lookup"><span data-stu-id="8abce-115">In the **Look in** list, select your domain or computer name.</span></span>  
  
7.  <span data-ttu-id="8abce-116">一覧で、ユーザーとコンピューターのドメインまたは手順 6 で選択したコンピューターに関連付けられているを含む、選択は、追加するユーザー アカウント**追加**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-116">In the list that contains the users and computers associated with the domain or computer you selected in step 6, select the user account to add, click **Add**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="8abce-117">をクリックして**OK**を閉じる、 **BizTalk Server 管理者のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8abce-117">Click **OK** to close the **BizTalk Server Administrators Properties** dialog box.</span></span>  
  
### <a name="to-remove-users-from-local-the-biztalk-server-administrators-group"></a><span data-ttu-id="8abce-118">ユーザーをローカルの BizTalk Server 管理者グループから削除するには</span><span class="sxs-lookup"><span data-stu-id="8abce-118">To remove users from local the BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="8abce-119">をクリックして**開始**、 をポイント**管理ツール**、順にクリック**コンピューターの管理**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-119">Click **Start**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="8abce-120">展開**システム ツール**、展開**ローカル ユーザーとグループ**、をクリックし、**グループ**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="8abce-120">Expand **System Tools**, expand **Local Users and Groups**, and then click the **Groups** folder.</span></span> <span data-ttu-id="8abce-121">フォルダの内容が詳細ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8abce-121">The folder contents appear in the details pane.</span></span>  
  
3.  <span data-ttu-id="8abce-122">詳細ペインでクリックして**BizTalk Server 管理者**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-122">In the details pane, click **BizTalk Server Administrators**.</span></span>  
  
4.  <span data-ttu-id="8abce-123">**アクション** メニューのをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-123">On the **Action** menu, click **Properties**.</span></span>  
  
5.  <span data-ttu-id="8abce-124">**BizTalk Server 管理者のプロパティ** ダイアログ ボックスで、ユーザー アカウントをクリックして、削除する**削除**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-124">In the **BizTalk Server Administrators Properties** dialog box, select the user account you want to remove, and then click **Remove**.</span></span>  
  
6.  <span data-ttu-id="8abce-125">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8abce-125">Click **OK**.</span></span>  
  
### <a name="to-add-users-to-the-domain-biztalk-server-administrators-group"></a><span data-ttu-id="8abce-126">ユーザーをドメインの BizTalk Server 管理者グループに追加するには</span><span class="sxs-lookup"><span data-stu-id="8abce-126">To add users to the domain BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="8abce-127">ドメイン管理者アカウントを使用して SQL Server データベースが参加しているドメイン コントローラにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8abce-127">Log on to the domain controller where the SQL Server databases are joined by using the Domain Admins account.</span></span>  
  
2.  <span data-ttu-id="8abce-128">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**Active Directory ユーザーとコンピューター**に開始、 **Active Directory ユーザーとコンピューター**コンソールです。</span><span class="sxs-lookup"><span data-stu-id="8abce-128">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
    1.  <span data-ttu-id="8abce-129">コンソール ツリーで、メンバを追加するフォルダとして、BizTalk Server 管理者グループを含むフォルダを展開します。</span><span class="sxs-lookup"><span data-stu-id="8abce-129">In the console tree, click the folder that contains the BizTalk Server Administrators group to which you want to add a member.</span></span>  
  
    2.  <span data-ttu-id="8abce-130">詳細ウィンドウで、BizTalk Server 管理者グループを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-130">In the details pane, right-click the BizTalk Server Administrators group, and then click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="8abce-131">**メンバー**  タブで、をクリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-131">On the **Members** tab, click **Add**.</span></span>  
  
    4.  <span data-ttu-id="8abce-132">**を選択するオブジェクト名の入力**、ユーザーの名前を入力して、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-132">In **Enter the object names to select**, type the name of the user, and then click **OK**.</span></span>  
  
### <a name="to-remove-users-from-the-domain-biztalk-server-administrators-group"></a><span data-ttu-id="8abce-133">ユーザー ドメインの BizTalk Server 管理者グループから削除するには</span><span class="sxs-lookup"><span data-stu-id="8abce-133">To remove users from the domain BizTalk Server Administrators group</span></span>  
  
1.  <span data-ttu-id="8abce-134">ドメイン管理者アカウントを使用して SQL データベースが参加しているドメイン コントローラにログオンします。</span><span class="sxs-lookup"><span data-stu-id="8abce-134">Log on to the domain controller where SQL databases are joined using the Domain Admins account.</span></span>  
  
2.  <span data-ttu-id="8abce-135">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**Active Directory ユーザーとコンピューター**に開始、 **Active Directory ユーザーとコンピューター**コンソールです。</span><span class="sxs-lookup"><span data-stu-id="8abce-135">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Active Directory Users and Computers** to start the **Active Directory Users and Computers** console.</span></span>  
  
    1.  <span data-ttu-id="8abce-136">コンソール ツリーで、メンバを追加するフォルダとして、BizTalk Server 管理者グループを含むフォルダを展開します。</span><span class="sxs-lookup"><span data-stu-id="8abce-136">In the console tree, click the folder that contains the BizTalk Server Administrators group to which you want to add a member.</span></span>  
  
    2.  <span data-ttu-id="8abce-137">詳細ウィンドウで、BizTalk Server 管理者グループを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-137">In the details pane, right-click the BizTalk Server Administrators group, and then click **Properties**.</span></span>  
  
    3.  <span data-ttu-id="8abce-138">**メンバー**  タブで、削除、およびをクリックするメンバーをクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="8abce-138">On the **Members** tab, click the member you want to remove, and then click **Remove**.</span></span>  
  
    4.  <span data-ttu-id="8abce-139">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8abce-139">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8abce-140">参照</span><span class="sxs-lookup"><span data-stu-id="8abce-140">See Also</span></span>  
 <span data-ttu-id="8abce-141">[BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="8abce-141">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 <span data-ttu-id="8abce-142">[管理ホストおよびサービス アカウント](../core/managing-hosts-and-service-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="8abce-142">[Managing Hosts and Service Accounts](../core/managing-hosts-and-service-accounts.md) </span></span>  
 <span data-ttu-id="8abce-143">[Windows グループとユーザー アカウントを管理するためのベスト プラクティス](../core/best-practices-for-managing-windows-groups-and-user-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="8abce-143">[Best Practices for Managing Windows Groups and User Accounts](../core/best-practices-for-managing-windows-groups-and-user-accounts.md) </span></span>  
 <span data-ttu-id="8abce-144">[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="8abce-144">[Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md) </span></span>  
 [<span data-ttu-id="8abce-145">Windows グループおよびユーザー アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="8abce-145">Managing Windows Groups and User Accounts</span></span>](../core/managing-windows-groups-and-user-accounts.md)