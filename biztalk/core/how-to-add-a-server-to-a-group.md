---
title: "サーバー グループを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- groups, servers
- adding, servers
- managing [groups], adding servers
- servers, groups
- managing [servers], adding to groups
ms.assetid: 6eca1eeb-1a56-4470-b3bc-c64865cf6270
caps.latest.revision: "26"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db5c7b760167f3e17d3ea82bf1023884b65e725
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-server-to-a-group"></a><span data-ttu-id="43954-102">グループにサーバーを追加する方法</span><span class="sxs-lookup"><span data-stu-id="43954-102">How to Add a Server to a Group</span></span>
<span data-ttu-id="43954-103">BizTalk Server 構成ウィザードを使用して、BizTalk グループにサーバーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="43954-103">You can use BizTalk Server Configuration to add a server to a BizTalk group.</span></span> <span data-ttu-id="43954-104">BizTalk グループにサーバーを追加して、BizTalk Server 環境をスケール アウトします。</span><span class="sxs-lookup"><span data-stu-id="43954-104">You add additional servers to a BizTalk group to scale out your BizTalk Server environment.</span></span>  
  
 <span data-ttu-id="43954-105">サーバーは、1 つの BizTalk グループに関連付けられたのみできます。</span><span class="sxs-lookup"><span data-stu-id="43954-105">A server can only be associated with one BizTalk group.</span></span> <span data-ttu-id="43954-106">サーバーが別のグループに既に属している場合、まず現在のグループからサーバーを削除し、その後でサーバーを新しいグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43954-106">If a server already belongs to another group, you must first remove that server from its current group before you can add it to a new group.</span></span> <span data-ttu-id="43954-107">BizTalk グループからサーバーを削除する方法の詳細については、次を参照してください。[グループからサーバーを削除する方法](../core/how-to-remove-a-server-from-a-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="43954-107">For information about removing a server from a BizTalk group, see [How to Remove a Server from a Group](../core/how-to-remove-a-server-from-a-group.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43954-108">BizTalk Server 環境内の異なるサーバーに関連付けられた BizTalk グループどうしは、メッセージの交換以外の連携を行いません。</span><span class="sxs-lookup"><span data-stu-id="43954-108">BizTalk groups associated with different servers in a BizTalk Server environment do not interact except to exchange messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="43954-109">BizTalk Server ランタイムは、BizTalk グループに追加するコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43954-109">The BizTalk Server runtime must be installed on the computer you want to add to the BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="43954-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="43954-110">Prerequisites</span></span>  
 <span data-ttu-id="43954-111">ここで示す手順を実行するには、SSO 管理者グループのメンバーおよび Windows 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43954-111">To perform this procedure, you must be logged on as a member of the SSO Administrators group and as a member of the Windows Administrators group.</span></span>  
  
### <a name="to-add-a-server-to-a-biztalk-group"></a><span data-ttu-id="43954-112">サーバーを BizTalk グループに追加するには</span><span class="sxs-lookup"><span data-stu-id="43954-112">To add a server to a BizTalk group</span></span>  
  
1.  <span data-ttu-id="43954-113">このコンピューターに BizTalk Server グループに追加する、をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 構成**.</span><span class="sxs-lookup"><span data-stu-id="43954-113">On the computer that you want to add to a BizTalk Server group to, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="43954-114">**Microsoft BizTalk Server 構成****カスタム構成**です。</span><span class="sxs-lookup"><span data-stu-id="43954-114">In **Microsoft BizTalk Server Configuration**, select **Custom configuration**.</span></span>  
  
3.  <span data-ttu-id="43954-115">**データベース サーバー名**サーバーが参加先 BizTalk グループの SQL Server の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="43954-115">In **Database server name**, type the name of the SQL Server for the BizTalk Group the server is joining.</span></span>  
  
4.  <span data-ttu-id="43954-116">**サービス資格情報**、適切なユーザー名とサービスを使用し、パスワードを入力**構成**です。</span><span class="sxs-lookup"><span data-stu-id="43954-116">In **Service credential**, type the appropriate user name and password that the services will use, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="43954-117">画面の左側にあるナビゲーション ツリーで、クリックして**エンタープライズ SSO**です。</span><span class="sxs-lookup"><span data-stu-id="43954-117">In the navigation tree on the left side of the screen, click **Enterprise SSO**.</span></span>  
  
6.  <span data-ttu-id="43954-118">**エンタープライズ シングル サインオン**] ページで [**既存の SSO システムに参加**です。</span><span class="sxs-lookup"><span data-stu-id="43954-118">On the **Enterprise Single Sign-On** page, click **Join an existing SSO system**.</span></span>  
  
     <span data-ttu-id="43954-119">参加先 BizTalk Server グループのマスター SSO データベース サーバーに対する、適切なサーバー名およびデータベース名が指定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="43954-119">Ensure that the server name and database name point to the master SSO database server for the BizTalk Server group the server is joining.</span></span>  
  
7.  <span data-ttu-id="43954-120">画面の左側にあるナビゲーション ツリーで、クリックして**グループ**です。</span><span class="sxs-lookup"><span data-stu-id="43954-120">In the navigation tree on the left side of the screen, click **Group**.</span></span>  
  
8.  <span data-ttu-id="43954-121">**グループ**] ページで [**既存の BizTalk グループに参加**です。</span><span class="sxs-lookup"><span data-stu-id="43954-121">On the **Group** page, click **Join an existing BizTalk Group**.</span></span>  
  
     <span data-ttu-id="43954-122">参加先 BizTalk Server グループのデータベースに対する、適切なサーバー名およびデータベース名が指定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="43954-122">Ensure that the server name and database name point to the databases for the BizTalk Server group the server is joining.</span></span>  
  
9. <span data-ttu-id="43954-123">メニュー バーで、をクリックして**構成の適用**をこのコンピューターでエンタープライズ シングル サインオンとグループの両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="43954-123">On the menu bar, click **Apply Configuration** to configure both Enterprise Single Sign-On and the Group on this computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43954-124">参照</span><span class="sxs-lookup"><span data-stu-id="43954-124">See Also</span></span>  
 <span data-ttu-id="43954-125">[構成フレームワークを使用した作業](../install-and-config-guides/working-with-the-configuration-framework.md) </span><span class="sxs-lookup"><span data-stu-id="43954-125">[Working with the Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md) </span></span>  
 <span data-ttu-id="43954-126">[グループを管理します。](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="43954-126">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="43954-127">[BizTalk グループ](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="43954-127">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="43954-128">[1 つのグループからサーバーを移動する方法](../core/how-to-move-a-server-from-one-group-to-another.md) </span><span class="sxs-lookup"><span data-stu-id="43954-128">[How to Move a Server from One Group to Another](../core/how-to-move-a-server-from-one-group-to-another.md) </span></span>  
 <span data-ttu-id="43954-129">[グループからサーバーを削除する方法](../core/how-to-remove-a-server-from-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="43954-129">[How to Remove a Server from a Group](../core/how-to-remove-a-server-from-a-group.md) </span></span>  
 <span data-ttu-id="43954-130">[グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="43954-130">[How to Modify Group Properties](../core/how-to-modify-group-properties.md) </span></span>  
 [<span data-ttu-id="43954-131">サーバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="43954-131">Managing Servers</span></span>](../core/managing-servers.md)