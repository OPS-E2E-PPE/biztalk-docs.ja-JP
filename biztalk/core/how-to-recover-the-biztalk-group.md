---
title: "BizTalk グループを回復する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23cd2a6550263f707531101db743a6ecdef39e5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-recover-the-biztalk-group"></a><span data-ttu-id="9e4c5-102">BizTalk グループを復旧する方法</span><span class="sxs-lookup"><span data-stu-id="9e4c5-102">How to Recover the BizTalk Group</span></span>
<span data-ttu-id="9e4c5-103">システムの復旧処理では、BizTalk Server を既存の BizTalk グループに再度加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-103">You must rejoin the BizTalk Server to an existing BizTalk group as part of the system recovery process.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9e4c5-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="9e4c5-104">Prerequisites</span></span>  
 <span data-ttu-id="9e4c5-105">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
 <span data-ttu-id="9e4c5-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition を復旧する場合は、サーバーの復旧を円滑にするスクリプトをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-106">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must download a script that facilitates recovery of the server.</span></span> <span data-ttu-id="9e4c5-107">ダウンロード[RestoreConfig.vbe](http://go.microsoft.com/fwlink/?LinkID=195799)です。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-107">Download [RestoreConfig.vbe](http://go.microsoft.com/fwlink/?LinkID=195799).</span></span>  
  
### <a name="to-recover-the-biztalk-group-standard-edition"></a><span data-ttu-id="9e4c5-108">BizTalk グループを復旧するには (Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="9e4c5-108">To recover the BizTalk group (Standard Edition)</span></span>  
  
1.  <span data-ttu-id="9e4c5-109">をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-109">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="9e4c5-110">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-110">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="9e4c5-111">**RestoreConfig.vbe***\<SavedConfigXML >* </span><span class="sxs-lookup"><span data-stu-id="9e4c5-111">**RestoreConfig.vbe**  *\<SavedConfigXML>*</span></span>  
  
     <span data-ttu-id="9e4c5-112">ここで *\<SavedConfigXML >*は完全なパスと保存されている構成ファイルのファイル名。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-112">Where *\<SavedConfigXML>* is the full path and filename of the saved configuration file.</span></span>  
  
     <span data-ttu-id="9e4c5-113">上記の操作でエラーが発生することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-113">The above should exit without displaying any errors.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e4c5-114">回復する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行する必要があります、64 ビット コンピューターで、Standard Edition、 **RestoreConfig.vbe**のため、更新できる 32 ビット レジストリの 32 ビット コマンド プロンプトからです。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-114">To recover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition on a 64-bit computer, you must run **RestoreConfig.vbe** from the 32-bit command prompt so that it can update the 32-bit registry.</span></span> <span data-ttu-id="9e4c5-115">32 ビット コマンド プロンプトを開くには、をクリックして**開始**、 をクリックして**実行**、型**c:\windows\syswow64\cmd.exe**、クリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-115">To open the 32-bit command prompt, click **Start**, click **Run**, type **c:\windows\syswow64\cmd.exe**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e4c5-116">障害が発生したコンピューターの名前は、保存済みの構成ファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-116">The name of the computer that failed is contained in the saved configuration file.</span></span> <span data-ttu-id="9e4c5-117">復旧するコンピューターの名前は、これと同じ名前でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-117">The name of the computer that you are restoring onto must have that same name.</span></span> <span data-ttu-id="9e4c5-118">その名前のコンピューター上で、前述のスクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-118">You must run the script above on a computer with that name.</span></span> <span data-ttu-id="9e4c5-119">ただし、保存済みの構成ファイルで、障害が発生したコンピューターの名前を変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-119">You can, however, change the name of the computer that failed in the saved configuration file.</span></span> <span data-ttu-id="9e4c5-120">これにより、別の名前のコンピューター上で前述のスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-120">If you do so, you can run the script above onto a computer with a different name.</span></span>  
  
### <a name="to-recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a><span data-ttu-id="9e4c5-121">BizTalk グループを復旧するには (Developer Edition または Enterprise Edition)</span><span class="sxs-lookup"><span data-stu-id="9e4c5-121">To recover the BizTalk group (Developer Edition or Enterprise Edition)</span></span>  
  
1.  <span data-ttu-id="9e4c5-122">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 構成**です。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
2.  <span data-ttu-id="9e4c5-123">[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、コンソール ツリーでクリックして**グループ**です。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-123">In [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], in the console tree, click **Group**.</span></span>  
  
3.  <span data-ttu-id="9e4c5-124">詳細ウィンドウで、次のように選択します。**既存の BizTalk グループに参加**、し、適切なリモート BizTalk 管理 (BizTalkMgmtDb) データベースを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-124">In the details pane, select **Join an existing BizTalk Group**, and then specify the appropriate remote BizTalk Management (BizTalkMgmtDb) database.</span></span>  
  
4.  <span data-ttu-id="9e4c5-125">[**構成の適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-125">Click **Apply Configuration**.</span></span>  
  
5.  <span data-ttu-id="9e4c5-126">をクリックして**ファイル**、クリックして**終了**です。</span><span class="sxs-lookup"><span data-stu-id="9e4c5-126">Click **File**, and then click **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e4c5-127">参照</span><span class="sxs-lookup"><span data-stu-id="9e4c5-127">See Also</span></span>  
 [<span data-ttu-id="9e4c5-128">BizTalk Server を実行しているコンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="9e4c5-128">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)