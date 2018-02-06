---
title: "BizTalk グループを回復 |Microsoft ドキュメント"
ms.custom: 
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3563956daa4848d4d67c1321c23676b21f9e4735
ms.sourcegitcommit: 78376935362715684b451eb6da9f2b1e8c129c2b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-recover-the-biztalk-group"></a><span data-ttu-id="2af24-102">BizTalk グループを復旧する方法</span><span class="sxs-lookup"><span data-stu-id="2af24-102">How to Recover the BizTalk Group</span></span>
<span data-ttu-id="2af24-103">システムの復旧処理では、BizTalk Server を既存の BizTalk グループに再度加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="2af24-103">You must rejoin the BizTalk Server to an existing BizTalk group as part of the system recovery process.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2af24-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="2af24-104">Prerequisites</span></span>  
 <span data-ttu-id="2af24-105">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2af24-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
 <span data-ttu-id="2af24-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition を復旧する場合は、サーバーの復旧を円滑にするスクリプトをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2af24-106">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must download a script that facilitates recovery of the server.</span></span> <span data-ttu-id="2af24-107">ダウンロード[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)です。</span><span class="sxs-lookup"><span data-stu-id="2af24-107">Download [RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462).</span></span>  
  
## <a name="recover-the-biztalk-group-standard-edition"></a><span data-ttu-id="2af24-108">BizTalk グループ (Standard Edition) 回復します。</span><span class="sxs-lookup"><span data-stu-id="2af24-108">Recover the BizTalk group (Standard Edition)</span></span>  
  
1.  <span data-ttu-id="2af24-109">をクリックして**開始**、型**cmd**、し、**コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="2af24-109">Click **Start**, type **cmd**, and then select **Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="2af24-110">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="2af24-110">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="2af24-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span><span class="sxs-lookup"><span data-stu-id="2af24-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span></span>  
  
     <span data-ttu-id="2af24-112">ここで *\<SavedConfigXML\>* は完全なパスと保存されている構成ファイルのファイル名。</span><span class="sxs-lookup"><span data-stu-id="2af24-112">Where *\<SavedConfigXML\>* is the full path and filename of the saved configuration file.</span></span>  
  
     <span data-ttu-id="2af24-113">上記の操作でエラーが発生することはほとんどありません。</span><span class="sxs-lookup"><span data-stu-id="2af24-113">The above should exit without displaying any errors.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2af24-114">回復する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実行する必要があります、64 ビット コンピューターで、Standard Edition、 **RestoreConfig.vbe**のため、更新できる 32 ビット レジストリの 32 ビット コマンド プロンプトからです。</span><span class="sxs-lookup"><span data-stu-id="2af24-114">To recover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition on a 64-bit computer, you must run **RestoreConfig.vbe** from the 32-bit command prompt so that it can update the 32-bit registry.</span></span> <span data-ttu-id="2af24-115">32 ビット コマンド プロンプトを開くにはクリックして **開始**, 、 をクリックして **実行**, 、型 **c:\windows\syswow64\cmd.exe**, 、 をクリックし、 **ok**します。</span><span class="sxs-lookup"><span data-stu-id="2af24-115">To open the 32-bit command prompt, click **Start**, click **Run**, type **c:\windows\syswow64\cmd.exe**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2af24-116">障害が発生したコンピューターの名前は、保存済みの構成ファイルに含まれています。</span><span class="sxs-lookup"><span data-stu-id="2af24-116">The name of the computer that failed is contained in the saved configuration file.</span></span> <span data-ttu-id="2af24-117">復旧するコンピューターの名前は、これと同じ名前でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="2af24-117">The name of the computer that you are restoring onto must have that same name.</span></span> <span data-ttu-id="2af24-118">その名前のコンピューター上で、前述のスクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2af24-118">You must run the script above on a computer with that name.</span></span> <span data-ttu-id="2af24-119">ただし、保存済みの構成ファイルで、障害が発生したコンピューターの名前を変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="2af24-119">You can, however, change the name of the computer that failed in the saved configuration file.</span></span> <span data-ttu-id="2af24-120">これにより、別の名前のコンピューター上で前述のスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2af24-120">If you do so, you can run the script above onto a computer with a different name.</span></span>  
  
## <a name="recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a><span data-ttu-id="2af24-121">(Developer Edition または Enterprise Edition)、BizTalk グループを回復します。</span><span class="sxs-lookup"><span data-stu-id="2af24-121">Recover the BizTalk group (Developer Edition or Enterprise Edition)</span></span>  
  
1.  <span data-ttu-id="2af24-122">開いている**BizTalk Server 構成**([スタート] メニュー)。</span><span class="sxs-lookup"><span data-stu-id="2af24-122">Open **BizTalk Server Configuration** (Start menu).</span></span>
  
2.  <span data-ttu-id="2af24-123">BizTalk Server 管理コンソールで選択**グループ**です。</span><span class="sxs-lookup"><span data-stu-id="2af24-123">In BizTalk Server Administration, select **Group**.</span></span>  
  
3.  <span data-ttu-id="2af24-124">詳細ウィンドウで、次のように選択します。**既存の BizTalk グループに参加**、し、リモート BizTalk 管理データベース (BizTalkMgmtDb) を入力します。</span><span class="sxs-lookup"><span data-stu-id="2af24-124">In the details pane, select **Join an existing BizTalk Group**, and then enter the remote BizTalk Management (BizTalkMgmtDb) database.</span></span>  
  
4.  <span data-ttu-id="2af24-125">選択**構成を適用**です。</span><span class="sxs-lookup"><span data-stu-id="2af24-125">Select **Apply Configuration**.</span></span>  
  
5.  <span data-ttu-id="2af24-126">選択**ファイル**、し、**終了**です。</span><span class="sxs-lookup"><span data-stu-id="2af24-126">Select **File**, and then select **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af24-127">参照</span><span class="sxs-lookup"><span data-stu-id="2af24-127">See Also</span></span>  
 [<span data-ttu-id="2af24-128">BizTalk Server を実行しているコンピューターの復旧</span><span class="sxs-lookup"><span data-stu-id="2af24-128">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)
