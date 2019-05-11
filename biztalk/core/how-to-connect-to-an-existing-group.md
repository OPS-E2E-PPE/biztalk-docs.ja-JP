---
title: 既存のグループに接続する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.procedure.connecttogroup
helpviewer_keywords:
- groups, existing
- groups, connecting
- managing [groups], connecting
ms.assetid: 1eedbcd5-f3f1-4da5-b91c-67377131f889
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea2b32ef67ad219d09e50824be5d83880c929c76
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385763"
---
# <a name="how-to-connect-to-an-existing-group"></a><span data-ttu-id="cbcca-102">既存のグループに接続する方法</span><span class="sxs-lookup"><span data-stu-id="cbcca-102">How to Connect to an Existing Group</span></span>
<span data-ttu-id="cbcca-103">使用することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]これらのグループは、同じドメイン内または信頼されたドメイン内のコンピューターにある限り、企業内の 1 つまたは複数の BizTalk Server グループをリモートで管理する、企業内のコンピューターの管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="cbcca-103">You can use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console on any computer in your enterprise to remotely manage one or more BizTalk Server groups within your enterprise, as long as these groups are located on computers within the same domain or within trusted domains.</span></span>  
  
 <span data-ttu-id="cbcca-104">BizTalk Server 管理コンソールで、BizTalk Server 管理ノードは、最上位レベルのノードのすべての BizTalk グループであり、BizTalk Server 管理コンソールに既存の BizTalk Server グループを追加するときに使用するレベルです。</span><span class="sxs-lookup"><span data-stu-id="cbcca-104">The BizTalk Server Administration node in the BizTalk Server Administration console is the highest-level node for all BizTalk groups, and is the level that you use when adding an existing BizTalk Server group to the BizTalk Server Administration console.</span></span> <span data-ttu-id="cbcca-105">グループを追加するときに接続する、既存のサーバーと BizTalk 管理データベースを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbcca-105">When you add a group, you must specify an existing server and BizTalk Management database to which you want to connect.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cbcca-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="cbcca-106">Prerequisites</span></span>  
 <span data-ttu-id="cbcca-107">この手順を実行するには、必要がありますまたはログインする BizTalk Server Operators グループのメンバーとして、BizTalk Server 管理者グループのメンバーとして。</span><span class="sxs-lookup"><span data-stu-id="cbcca-107">To perform this procedure, you must be logged on as a member of the BizTalk Server Operators group or as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-connect-to-an-existing-group"></a><span data-ttu-id="cbcca-108">既存のグループに接続するには</span><span class="sxs-lookup"><span data-stu-id="cbcca-108">To connect to an existing group</span></span>  
  
1. <span data-ttu-id="cbcca-109">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="cbcca-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="cbcca-110">コンソール ツリーで、右クリック**BizTalk Server 管理**、 をクリックし、**既存グループへの接続**します。</span><span class="sxs-lookup"><span data-stu-id="cbcca-110">In the console tree, right-click **BizTalk Server Administration**, and then click **Connect to Existing Group**.</span></span>  
  
3. <span data-ttu-id="cbcca-111">**既存の BizTalk Server 構成データベースへの接続** ダイアログ ボックスで、 **SQL Server 名**ドロップダウン リスト ボックスで、BizTalk をホストする Microsoft SQL Server インスタンスの名前を選択します。管理のデータベース (構成データベースとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="cbcca-111">In the **Connect to Existing BizTalk Server Configuration Database** dialog box, in the **SQL Server name** drop-down list box, select the name of the Microsoft SQL Server instance that hosts the BizTalk Management database (also referred to as the Configuration database).</span></span> <span data-ttu-id="cbcca-112">SQL Server のインスタンスを選択すると、BizTalk Server はそのコンピューター上の BizTalk Server データベースを検出するために自動的に試行します。</span><span class="sxs-lookup"><span data-stu-id="cbcca-112">When you select the instance of SQL Server, BizTalk Server automatically attempts to detect BizTalk Server databases on that computer.</span></span>  
  
4. <span data-ttu-id="cbcca-113">**データベース名**ドロップダウン リスト ボックスで、BizTalk Server 管理データベースを選択します (**BizTalkMgmtDb**) クリックして、接続先**OK**します。</span><span class="sxs-lookup"><span data-stu-id="cbcca-113">In the **Database name** drop-down list box, select the BizTalk Server Management database (**BizTalkMgmtDb**) to which you want to connect, and then click **OK**.</span></span>  
  
    <span data-ttu-id="cbcca-114">BizTalk Server 管理コンソールでは、コンソール ツリーに BizTalk Server グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbcca-114">The BizTalk Server Administration console adds the BizTalk Server group to the console tree.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cbcca-115">場合は、BizTalk Server 管理データベースが SQL Server クラスターに格納されているし、クラスターがフェールオーバー中では、管理データベースに接続しようとしたときに、次のようなエラーを受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cbcca-115">If the BizTalk Server Management database is housed on a SQL Server cluster and the cluster is in the process of failing over then you may receive an error similar to the following when you attempt to connect to the Management database:</span></span>  
   >   
   >  <span data-ttu-id="cbcca-116">グループの読み込みに失敗しました [\<servername\>:\<管理データベース\>] データ プロバイダー。</span><span class="sxs-lookup"><span data-stu-id="cbcca-116">Failed to load Group [\<servername\>:\<management database\>] data providers.</span></span>  
   >   
   >  <span data-ttu-id="cbcca-117">And</span><span class="sxs-lookup"><span data-stu-id="cbcca-117">And</span></span>  
   >   
   >  <span data-ttu-id="cbcca-118">追加情報:</span><span class="sxs-lookup"><span data-stu-id="cbcca-118">ADDITIONAL INFORMATION:</span></span>  
   >   
   >  <span data-ttu-id="cbcca-119">WMI クラスのインスタンスが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="cbcca-119">Instance of the WMI class is not found.</span></span> <span data-ttu-id="cbcca-120">(WinMgmt)。</span><span class="sxs-lookup"><span data-stu-id="cbcca-120">(WinMgmt)</span></span>  
   >   
   >  <span data-ttu-id="cbcca-121">BizTalk データベースがフェールオーバーされるときに利用できないために、このエラーが発生することができます。</span><span class="sxs-lookup"><span data-stu-id="cbcca-121">This error can occur because the BizTalk databases are not available while they are being failed over.</span></span> <span data-ttu-id="cbcca-122">回避策にこの問題は、SQL Server のクラスター化されたインスタンスまでの待機はオンライン BizTalk Server 管理コンソールを使用して接続する前にです。</span><span class="sxs-lookup"><span data-stu-id="cbcca-122">To workaround this issue, wait until after the clustered instance of SQL Server is online before attempting to connect to it with the BizTalk Server Administration console.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbcca-123">参照</span><span class="sxs-lookup"><span data-stu-id="cbcca-123">See Also</span></span>  
 <span data-ttu-id="cbcca-124">[グループの管理](../core/managing-groups.md) </span><span class="sxs-lookup"><span data-stu-id="cbcca-124">[Managing Groups](../core/managing-groups.md) </span></span>  
 [<span data-ttu-id="cbcca-125">BizTalk グループ</span><span class="sxs-lookup"><span data-stu-id="cbcca-125">BizTalk Groups</span></span>](../core/biztalk-groups.md)