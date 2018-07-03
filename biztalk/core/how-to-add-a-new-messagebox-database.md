---
title: 新しいメッセージ ボックス データベースを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, MessageBox database
- MessageBox database, adding
- managing [MessageBox database], adding
ms.assetid: 98d850dc-fe3e-43dd-8b5d-9b8c23c006ae
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db394722afcdf9e5972a925963b5200b4eba157e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974523"
---
# <a name="how-to-add-a-new-messagebox-database"></a><span data-ttu-id="3614c-102">新しいメッセージ ボックス データベースを追加する方法</span><span class="sxs-lookup"><span data-stu-id="3614c-102">How to Add a New MessageBox Database</span></span>
<span data-ttu-id="3614c-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用すると、BizTalk Server 環境に新しいメッセージ ボックス データベースを追加できます。</span><span class="sxs-lookup"><span data-stu-id="3614c-103">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console to add a new MessageBox database to your BizTalk Server deployment.</span></span> <span data-ttu-id="3614c-104">メッセージ ボックス データベースは、協調動作するサーバー間で作業項目の負荷分散を行う基盤です。</span><span class="sxs-lookup"><span data-stu-id="3614c-104">MessageBox databases are the basis for load-balancing work items across servers that do cooperative processing.</span></span> <span data-ttu-id="3614c-105">システムで処理可能なメッセージの数を増加するには、新しいメッセージ ボックス データベースの追加が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="3614c-105">To increase the number of messages that your system can process, you may need to add additional MessageBox databases.</span></span>  
  
 <span data-ttu-id="3614c-106">新しいメッセージ ボックス データベースの作成時に、オーケストレーション、送信ポート、または送信ポート グループを参加させることはできません。</span><span class="sxs-lookup"><span data-stu-id="3614c-106">You cannot create a new MessageBox database and have enlisted orchestrations, send ports, or send port groups at the same time.</span></span> <span data-ttu-id="3614c-107">オーケストレーション、送信ポート、または送信ポート グループを参加させると、BizTalk Server により新しいメッセージ ボックス データベースにコピーすべきデータに対して、アクセスが生じます。</span><span class="sxs-lookup"><span data-stu-id="3614c-107">Enlisted orchestrations, send ports, or send port groups access data that BizTalk Server must copy to the new MessageBox database.</span></span> <span data-ttu-id="3614c-108">このデータへのアクセスが発生している間、BizTalk Server では、そのデータを新しいメッセージ ボックス データベースにコピーすることができません。</span><span class="sxs-lookup"><span data-stu-id="3614c-108">While this data is being accessed, BizTalk Server cannot copy it into the new MessageBox database.</span></span>  
  
 <span data-ttu-id="3614c-109">メッセージ ボックス データベースとして指定するデータベースは、ローカルでもリモートでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="3614c-109">You can designate both local and remote databases as MessageBox databases.</span></span> <span data-ttu-id="3614c-110">BizTalk Server データベースについては、次を参照してください。 [BizTalk Server でのデータベース](../core/databases-in-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="3614c-110">For information about BizTalk Server databases, see [Databases in BizTalk Server](../core/databases-in-biztalk-server.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3614c-111">新しいメッセージ ボックスを追加するすべての SQL Server コンピューターで、SQL Server エージェントが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3614c-111">SQL Server Agent must be running on all of the SQL servers to which you want to add a new MessageBox database.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3614c-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="3614c-112">Prerequisites</span></span>  
 <span data-ttu-id="3614c-113">メッセージ ボックス データベースを管理する管理者は、必要なユーザー権利が必要です。</span><span class="sxs-lookup"><span data-stu-id="3614c-113">Administrators who manage MessageBox databases must have the required user rights.</span></span> <span data-ttu-id="3614c-114">メッセージ ボックス データベースの管理と新しいメッセージの公開の無効化には、次のユーザー権利が必要です。</span><span class="sxs-lookup"><span data-stu-id="3614c-114">You must have the following user rights to manage MessageBox databases and disable new message publication:</span></span>  
  
-   <span data-ttu-id="3614c-115">BizTalk Server Administrators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3614c-115">You must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
-   <span data-ttu-id="3614c-116">データベースが存在するコンピューターの SQL Server 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3614c-116">You must be a SQL Server Administrator on the computer where the database exists.</span></span>  
  
### <a name="to-add-a-new-messagebox-database"></a><span data-ttu-id="3614c-117">新しいメッセージ ボックス データベースを追加するには</span><span class="sxs-lookup"><span data-stu-id="3614c-117">To add a new MessageBox database</span></span>  
  
1. <span data-ttu-id="3614c-118">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="3614c-118">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="3614c-119">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]BizTalk グループを展開し、クリックして**プラットフォームの設定**します。</span><span class="sxs-lookup"><span data-stu-id="3614c-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, and then click **Platform Settings**.</span></span>  
  
3. <span data-ttu-id="3614c-120">右クリック**メッセージ ボックス**、 をクリックして**新規**、 をクリックし、**メッセージ ボックス**します。</span><span class="sxs-lookup"><span data-stu-id="3614c-120">Right-click **Message Boxes**, click **New**, and then click **Message Box**.</span></span>  
  
4. <span data-ttu-id="3614c-121">**メッセージ ボックスのプロパティ** ダイアログ ボックスで、次の操作をクリックして**OK**:</span><span class="sxs-lookup"><span data-stu-id="3614c-121">In the **Message Box Properties** dialog box, do the following, and then click **OK**:</span></span>  
  
   |<span data-ttu-id="3614c-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3614c-122">Use this</span></span>|<span data-ttu-id="3614c-123">目的</span><span class="sxs-lookup"><span data-stu-id="3614c-123">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="3614c-124">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="3614c-124">**SQL Server**</span></span>|<span data-ttu-id="3614c-125">メッセージ ボックス データベースをホストする SQL Server の名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="3614c-125">Displays the name of the SQL server that hosts the MessageBox database.</span></span>|  
   |<span data-ttu-id="3614c-126">**[データベース]**</span><span class="sxs-lookup"><span data-stu-id="3614c-126">**Database**</span></span>|<span data-ttu-id="3614c-127">メッセージ ボックス データベースの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="3614c-127">Displays the name of the MessageBox database.</span></span>|  
   |<span data-ttu-id="3614c-128">**マスター サブスクリプション メッセージ ボックス**</span><span class="sxs-lookup"><span data-stu-id="3614c-128">**Master subscription message box**</span></span>|<span data-ttu-id="3614c-129">選択したメッセージ ボックス データベースがマスターかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="3614c-129">Indicates whether the selected MessageBox database is the master.</span></span> <span data-ttu-id="3614c-130">現在のメッセージ ボックス データベースがマスターの場合、このチェック ボックスはオンになっており、操作できません。</span><span class="sxs-lookup"><span data-stu-id="3614c-130">If the current MessageBox database is the master, this check box is selected and unavailable.</span></span> <span data-ttu-id="3614c-131">既定では、構成ウィザードを実行したとき最初に作成したメッセージ ボックス データベースがマスターになります。</span><span class="sxs-lookup"><span data-stu-id="3614c-131">The first MessageBox database created when you run the Configuration Wizard is the master by default.</span></span>|  
   |<span data-ttu-id="3614c-132">**新しいメッセージの公開を無効にします。**</span><span class="sxs-lookup"><span data-stu-id="3614c-132">**Disable new message publication**</span></span>|<span data-ttu-id="3614c-133">このメッセージ ボックス データベースでアクティベーション メッセージを受信しない場合、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3614c-133">Select this check box to specify that you do not want this MessageBox database to receive activation messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3614c-134">参照</span><span class="sxs-lookup"><span data-stu-id="3614c-134">See Also</span></span>  
 <span data-ttu-id="3614c-135">[メッセージ ボックス データベースの管理](../core/managing-messagebox-databases.md) </span><span class="sxs-lookup"><span data-stu-id="3614c-135">[Managing MessageBox Databases](../core/managing-messagebox-databases.md) </span></span>  
 <span data-ttu-id="3614c-136">[新しいメッセージの公開を無効にする方法](../core/how-to-disable-new-message-publication.md) </span><span class="sxs-lookup"><span data-stu-id="3614c-136">[How to Disable New Message Publication](../core/how-to-disable-new-message-publication.md) </span></span>  
 <span data-ttu-id="3614c-137">[メッセージ ボックス データベースを削除する方法](../core/how-to-delete-a-messagebox-database.md) </span><span class="sxs-lookup"><span data-stu-id="3614c-137">[How to Delete a MessageBox Database](../core/how-to-delete-a-messagebox-database.md) </span></span>  
 <span data-ttu-id="3614c-138">[バックアップおよび BizTalk Server データベースを復元します。](../core/backing-up-and-restoring-biztalk-server-databases.md) </span><span class="sxs-lookup"><span data-stu-id="3614c-138">[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md) </span></span>  
 [<span data-ttu-id="3614c-139">メッセージ ボックス データベース</span><span class="sxs-lookup"><span data-stu-id="3614c-139">The MessageBox Database</span></span>](../core/the-messagebox-database.md)