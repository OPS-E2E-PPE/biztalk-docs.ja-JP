---
title: BizTalk Server の構成を回復する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1d39e50-4296-49c7-bd1e-63b1325af168
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 179ff0690c7c07dcf58bf2d7fd92a885435509cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980339"
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a><span data-ttu-id="3fad3-102">BizTalk Server 構成を復旧する方法</span><span class="sxs-lookup"><span data-stu-id="3fad3-102">How to Recover the BizTalk Server Configuration</span></span>
<span data-ttu-id="3fad3-103">BizTalk Server を復旧するときには、BizTalk Server をインストールしたときに作成した構成ファイルもインポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fad3-103">As part of recovering your BizTalk server, you must also import the configuration file that you created when you installed BizTalk Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3fad3-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="3fad3-104">Prerequisites</span></span>  
 <span data-ttu-id="3fad3-105">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3fad3-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-the-biztalk-server-configuration"></a><span data-ttu-id="3fad3-106">BizTalk Server 構成を復旧するには</span><span class="sxs-lookup"><span data-stu-id="3fad3-106">To recover the BizTalk Server configuration</span></span>  
  
1. <span data-ttu-id="3fad3-107">メモ帳を使用して、以前バックアップした BizTalk Server 構成ファイルを編集し、すべての BizTalk Server サービスに対するユーザー アカウントのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="3fad3-107">Using Notepad, edit the BizTalk Server configuration file that you previously backed up, and enter the user account passwords for all of the BizTalk Server services.</span></span>  
  
2. <span data-ttu-id="3fad3-108">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 構成**します。</span><span class="sxs-lookup"><span data-stu-id="3fad3-108">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
3. <span data-ttu-id="3fad3-109">**Microsoft BizTalk Server 構成**、 をクリックして**構成のインポート**します。</span><span class="sxs-lookup"><span data-stu-id="3fad3-109">In **Microsoft BizTalk Server Configuration**, click **Import Configuration**.</span></span>  
  
    <span data-ttu-id="3fad3-110">機能の前に無効のアイコンが表示されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3fad3-110">Verify that there are no invalidation icons appearing in front of any feature.</span></span> <span data-ttu-id="3fad3-111">構成エラーがある機能が存在する場合は、ここで修正します。</span><span class="sxs-lookup"><span data-stu-id="3fad3-111">If any of the features have configuration errors, now is the time to correct them.</span></span>  
  
4. <span data-ttu-id="3fad3-112">**[構成の適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3fad3-112">Click **Apply Configuration**.</span></span>  
  
    <span data-ttu-id="3fad3-113">すべての BizTalk Server 機能の構成が終了したら、構成ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3fad3-113">After all of the BizTalk Server features are configured, close the configuration window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fad3-114">参照</span><span class="sxs-lookup"><span data-stu-id="3fad3-114">See Also</span></span>  
 <span data-ttu-id="3fad3-115">[BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="3fad3-115">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="3fad3-116">BizTalk Server の構成をバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="3fad3-116">How to Back Up The BizTalk Server Configuration</span></span>](../core/how-to-back-up-the-biztalk-server-configuration.md)