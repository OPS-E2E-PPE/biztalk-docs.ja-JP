---
title: 1 つのグループからサーバーを移動する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, servers
- groups, moving
- managing [groups], moving servers
- servers, moving
- managing [servers], moving
- servers, groups
ms.assetid: 3f789a62-f597-426b-9cea-74c1fe22b694
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c9e5dfdf266d2205283afa7cd9804c31fc93ff3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254570"
---
# <a name="how-to-move-a-server-from-one-group-to-another"></a><span data-ttu-id="35468-102">サーバーをあるグループから別のグループに移動する方法</span><span class="sxs-lookup"><span data-stu-id="35468-102">How to Move a Server from One Group to Another</span></span>
<span data-ttu-id="35468-103">1 つの BizTalk Server グループに関連付けることができるサーバーは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="35468-103">A server can only be associated with one BizTalk Server group.</span></span> <span data-ttu-id="35468-104">サーバーをあるグループから別のグループに移動するには、まず元のグループの構成を解除してそのグループからサーバーを削除したうえで、新しいグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35468-104">To move a server from one group to another, you must first remove the server from the original group by unconfiguring it, and then add the server to the new group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="35468-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="35468-105">Prerequisites</span></span>  
 <span data-ttu-id="35468-106">ここで示す手順を実行するには、SSO 管理者グループのメンバーおよび Windows 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="35468-106">To perform this procedure, you must be logged on as a member of the SSO Administrators group and as a member of the Windows Administrators group.</span></span>  
  
### <a name="to-move-a-server-from-one-biztalk-group-to-another"></a><span data-ttu-id="35468-107">サーバーをあるサーバーから別の BizTalk グループに移動するには</span><span class="sxs-lookup"><span data-stu-id="35468-107">To move a server from one BizTalk group to another</span></span>  
  
1.  <span data-ttu-id="35468-108">BizTalk グループから別に移動するコンピューターでをクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalkServer構成**.</span><span class="sxs-lookup"><span data-stu-id="35468-108">On the computer that you want to move from the BizTalk group to another, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="35468-109">メニュー バーで、をクリックして**機能の構成解除**です。</span><span class="sxs-lookup"><span data-stu-id="35468-109">On the menu bar, click **Unconfigure Features**.</span></span>  
  
3.  <span data-ttu-id="35468-110">**機能の構成解除**ダイアログ ボックスで、**エンタープライズ SSO**を選択**グループ**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="35468-110">In the **Unconfigure Features** dialog box, select **Enterprise SSO**, select **Group**, and then click **OK**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="35468-111">グループの構成を解除すると、そのコンピューターで既に構成されているすべての依存機能の構成が解除されます。</span><span class="sxs-lookup"><span data-stu-id="35468-111">Unconfiguring a group will also unconfigure all dependent features that are already configured on that computer.</span></span>  
  
4.  <span data-ttu-id="35468-112">**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35468-112">Click **Yes**.</span></span>  
  
5.  <span data-ttu-id="35468-113">**Microsoft BizTalk Server 構成**ウィンドウで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="35468-113">In the **Microsoft BizTalk Server Configuration** window, click **Next**.</span></span>  
  
     <span data-ttu-id="35468-114">エンタープライズ SSO、グループ、および、それらに依存する機能の構成が解除されます。</span><span class="sxs-lookup"><span data-stu-id="35468-114">Enterprise SSO, the Group, and their dependent features are unconfigured.</span></span>  
  
6.  <span data-ttu-id="35468-115">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35468-115">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="35468-116">**Microsoft BizTalk Server 構成**ウィンドウで、**カスタム構成**です。</span><span class="sxs-lookup"><span data-stu-id="35468-116">In the **Microsoft BizTalk Server Configuration** window, select **Custom configuration**.</span></span>  
  
8.  <span data-ttu-id="35468-117">**データベース サーバー名**サーバーを移動する、BizTalk グループの SQL server の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="35468-117">In **Database server name**, type the name of the SQL server for the BizTalk Group where you are moving the server.</span></span>  
  
9. <span data-ttu-id="35468-118">**サービス資格情報**、適切なユーザー名とサービスを使用し、パスワードを入力**構成**です。</span><span class="sxs-lookup"><span data-stu-id="35468-118">In **Service credential**, type the appropriate user name and password that the services will use, and then click **Configure**.</span></span>  
  
10. <span data-ttu-id="35468-119">画面の左側にあるナビゲーション ツリーで、クリックして**エンタープライズ SSO**です。</span><span class="sxs-lookup"><span data-stu-id="35468-119">In the navigation tree on the left side of the screen, click **Enterprise SSO**.</span></span>  
  
11. <span data-ttu-id="35468-120">**エンタープライズ シングル サインオン**] ページで [**既存の SSO システムに参加**です。</span><span class="sxs-lookup"><span data-stu-id="35468-120">On the **Enterprise Single Sign-On** page, click **Join an existing SSO system**.</span></span>  
  
     <span data-ttu-id="35468-121">移動先 BizTalk Server グループのマスター SSO データベース サーバーに対する、適切なサーバー名およびデータベース名が指定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35468-121">Ensure that the server name and database name point to the master SSO database server for the BizTalk Server group where you are moving the server.</span></span>  
  
12. <span data-ttu-id="35468-122">画面の左側にあるナビゲーション ツリーで、クリックして**グループ**です。</span><span class="sxs-lookup"><span data-stu-id="35468-122">In the navigation tree on the left side of the screen, click **Group**.</span></span>  
  
13. <span data-ttu-id="35468-123">**グループ**] ページで [**既存の BizTalk グループに参加**です。</span><span class="sxs-lookup"><span data-stu-id="35468-123">On the **Group** page, click **Join an existing BizTalk Group**.</span></span>  
  
     <span data-ttu-id="35468-124">移動先 BizTalk Server グループのデータベースに対する、適切なサーバー名およびデータベース名が指定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35468-124">Ensure that the server name and database name point to the databases for the BizTalk Server group where you are moving the server.</span></span>  
  
14. <span data-ttu-id="35468-125">メニュー バーで、をクリックして**構成の適用**をこのコンピューターでエンタープライズ シングル サインオンとグループの両方を構成します。</span><span class="sxs-lookup"><span data-stu-id="35468-125">On the menu bar, click **Apply Configuration** to configure both Enterprise Single Sign-On and the Group on this computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35468-126">参照</span><span class="sxs-lookup"><span data-stu-id="35468-126">See Also</span></span>  
 <span data-ttu-id="35468-127">[グループを管理します。](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="35468-127">[Managing Groups](../core/managing-groups.md) </span></span>  
 <span data-ttu-id="35468-128">[BizTalk グループ](../core/biztalk-groups.md) </span><span class="sxs-lookup"><span data-stu-id="35468-128">[BizTalk Groups](../core/biztalk-groups.md) </span></span>  
 <span data-ttu-id="35468-129">[サーバー グループを追加する方法](../core/how-to-add-a-server-to-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="35468-129">[How to Add a Server to a Group](../core/how-to-add-a-server-to-a-group.md) </span></span>  
 <span data-ttu-id="35468-130">[グループからサーバーを削除する方法](../core/how-to-remove-a-server-from-a-group.md) </span><span class="sxs-lookup"><span data-stu-id="35468-130">[How to Remove a Server from a Group](../core/how-to-remove-a-server-from-a-group.md) </span></span>  
 <span data-ttu-id="35468-131">[グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md) </span><span class="sxs-lookup"><span data-stu-id="35468-131">[How to Modify Group Properties](../core/how-to-modify-group-properties.md) </span></span>  
 <span data-ttu-id="35468-132">[構成フレームワークを使用した作業](../install-and-config-guides/working-with-the-configuration-framework.md) </span><span class="sxs-lookup"><span data-stu-id="35468-132">[Working with the Configuration Framework](../install-and-config-guides/working-with-the-configuration-framework.md) </span></span>  
 <span data-ttu-id="35468-133">[ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md) </span><span class="sxs-lookup"><span data-stu-id="35468-133">[How to Add a Host Instance](../core/how-to-add-a-host-instance.md) </span></span>  
 [<span data-ttu-id="35468-134">サーバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="35468-134">Managing Servers</span></span>](../core/managing-servers.md)