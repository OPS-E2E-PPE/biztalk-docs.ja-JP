---
title: BizTalk グループの復旧 |Microsoft Docs
ms.custom: ''
ms.date: 01/30/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1010e55-7e3d-4565-8604-ea652ea4da8c
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e637b974fc49fcfa3b1b6c27452ccc7d036359f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384429"
---
# <a name="how-to-recover-the-biztalk-group"></a><span data-ttu-id="72eb0-102">BizTalk グループを復旧する方法</span><span class="sxs-lookup"><span data-stu-id="72eb0-102">How to Recover the BizTalk Group</span></span>
<span data-ttu-id="72eb0-103">BizTalk Server システム復旧プロセスの一部として既存の BizTalk グループには、再び参加させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="72eb0-103">You must rejoin the BizTalk Server to an existing BizTalk group as part of the system recovery process.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="72eb0-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="72eb0-104">Prerequisites</span></span>  
 <span data-ttu-id="72eb0-105">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72eb0-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
 <span data-ttu-id="72eb0-106">回復する場合は[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Standard Edition は、サーバーの回復を容易にするスクリプトをダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="72eb0-106">If you are recovering [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition, you must download a script that facilitates recovery of the server.</span></span> <span data-ttu-id="72eb0-107">ダウンロード[RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462)します。</span><span class="sxs-lookup"><span data-stu-id="72eb0-107">Download [RestoreConfig.vbe](https://www.microsoft.com/download/details.aspx?id=7462).</span></span>  
  
## <a name="recover-the-biztalk-group-standard-edition"></a><span data-ttu-id="72eb0-108">BizTalk グループ (Standard Edition) の復旧します。</span><span class="sxs-lookup"><span data-stu-id="72eb0-108">Recover the BizTalk group (Standard Edition)</span></span>  
  
1. <span data-ttu-id="72eb0-109">クリックして**開始**、型**cmd**、し、**コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="72eb0-109">Click **Start**, type **cmd**, and then select **Command Prompt**.</span></span>  
  
2. <span data-ttu-id="72eb0-110">コマンド プロンプトで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="72eb0-110">At the command prompt, type:</span></span>  
  
    <span data-ttu-id="72eb0-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span><span class="sxs-lookup"><span data-stu-id="72eb0-111">**RestoreConfig.vbe**  *\<SavedConfigXML\>*</span></span>  
  
    <span data-ttu-id="72eb0-112">場所*\<SavedConfigXML\>* は完全なパスと保存されている構成ファイルのファイル名。</span><span class="sxs-lookup"><span data-stu-id="72eb0-112">Where *\<SavedConfigXML\>* is the full path and filename of the saved configuration file.</span></span>  
  
    <span data-ttu-id="72eb0-113">上記の場合、エラーが発生することがなくが終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72eb0-113">The above should exit without displaying any errors.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="72eb0-114">回復する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット コンピューターで Standard Edition を実行する必要がある**RestoreConfig.vbe** 32 ビットのレジストリを更新できるため、32 ビット コマンド プロンプトからです。</span><span class="sxs-lookup"><span data-stu-id="72eb0-114">To recover [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Standard Edition on a 64-bit computer, you must run **RestoreConfig.vbe** from the 32-bit command prompt so that it can update the 32-bit registry.</span></span> <span data-ttu-id="72eb0-115">32 ビット コマンド プロンプトを開くには、次のようにクリックします。**開始**、 をクリック**実行**、型**c:\windows\syswow64\cmd.exe**、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="72eb0-115">To open the 32-bit command prompt, click **Start**, click **Run**, type **c:\windows\syswow64\cmd.exe**, and then click **OK**.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="72eb0-116">失敗したコンピューターの名前は、保存されている構成ファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="72eb0-116">The name of the computer that failed is contained in the saved configuration file.</span></span> <span data-ttu-id="72eb0-117">同じ名前に復元しているコンピューターの名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="72eb0-117">The name of the computer that you are restoring onto must have that same name.</span></span> <span data-ttu-id="72eb0-118">その名前を持つコンピューターでは、前述のスクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="72eb0-118">You must run the script above on a computer with that name.</span></span> <span data-ttu-id="72eb0-119">ただし、保存されている構成ファイルで失敗したコンピューターの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="72eb0-119">You can, however, change the name of the computer that failed in the saved configuration file.</span></span> <span data-ttu-id="72eb0-120">これを行う場合は、別の名前でコンピューターには、上記のスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="72eb0-120">If you do so, you can run the script above onto a computer with a different name.</span></span>  
  
## <a name="recover-the-biztalk-group-developer-edition-or-enterprise-edition"></a><span data-ttu-id="72eb0-121">BizTalk グループ (Developer Edition または Enterprise Edition) の復旧します。</span><span class="sxs-lookup"><span data-stu-id="72eb0-121">Recover the BizTalk group (Developer Edition or Enterprise Edition)</span></span>  
  
1.  <span data-ttu-id="72eb0-122">開いている**BizTalk Server 構成**([スタート] メニュー)。</span><span class="sxs-lookup"><span data-stu-id="72eb0-122">Open **BizTalk Server Configuration** (Start menu).</span></span>
  
2.  <span data-ttu-id="72eb0-123">BizTalk Server 管理コンソールで次のように選択します。**グループ**します。</span><span class="sxs-lookup"><span data-stu-id="72eb0-123">In BizTalk Server Administration, select **Group**.</span></span>  
  
3.  <span data-ttu-id="72eb0-124">詳細] ウィンドウで、[**既存の BizTalk グループに参加**、リモートの BizTalk 管理 (BizTalkMgmtDb) データベースを入力します。</span><span class="sxs-lookup"><span data-stu-id="72eb0-124">In the details pane, select **Join an existing BizTalk Group**, and then enter the remote BizTalk Management (BizTalkMgmtDb) database.</span></span>  
  
4.  <span data-ttu-id="72eb0-125">選択**構成の適用**します。</span><span class="sxs-lookup"><span data-stu-id="72eb0-125">Select **Apply Configuration**.</span></span>  
  
5.  <span data-ttu-id="72eb0-126">選択**ファイル**、し、**終了**します。</span><span class="sxs-lookup"><span data-stu-id="72eb0-126">Select **File**, and then select **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72eb0-127">参照</span><span class="sxs-lookup"><span data-stu-id="72eb0-127">See Also</span></span>  
 [<span data-ttu-id="72eb0-128">BizTalk Server を実行しているコンピューターの復旧</span><span class="sxs-lookup"><span data-stu-id="72eb0-128">Recovering a Computer Running BizTalk Server</span></span>](../core/recovering-a-computer-running-biztalk-server.md)
