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
ms.openlocfilehash: 59910e1af14ff9d21ea196d9ec92202772541876
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335488"
---
# <a name="how-to-recover-the-biztalk-server-configuration"></a><span data-ttu-id="4bde0-102">BizTalk Server 構成を復旧する方法</span><span class="sxs-lookup"><span data-stu-id="4bde0-102">How to Recover the BizTalk Server Configuration</span></span>
<span data-ttu-id="4bde0-103">BizTalk サーバーの回復の一部として、BizTalk Server をインストールしたときに作成した構成ファイルをインポートすることも必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bde0-103">As part of recovering your BizTalk server, you must also import the configuration file that you created when you installed BizTalk Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4bde0-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="4bde0-104">Prerequisites</span></span>  
 <span data-ttu-id="4bde0-105">ここで示す手順を実行するには、管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bde0-105">You must be logged on as a member of the Administrators group to perform this procedure.</span></span>  
  
### <a name="to-recover-the-biztalk-server-configuration"></a><span data-ttu-id="4bde0-106">BizTalk Server 構成を復旧するには</span><span class="sxs-lookup"><span data-stu-id="4bde0-106">To recover the BizTalk Server configuration</span></span>  
  
1. <span data-ttu-id="4bde0-107">メモ帳を使用して、以前バックアップした、BizTalk Server 構成ファイルを編集し、BizTalk Server サービスのすべてのユーザー アカウントのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="4bde0-107">Using Notepad, edit the BizTalk Server configuration file that you previously backed up, and enter the user account passwords for all of the BizTalk Server services.</span></span>  
  
2. <span data-ttu-id="4bde0-108">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 構成**します。</span><span class="sxs-lookup"><span data-stu-id="4bde0-108">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Configuration**.</span></span>  
  
3. <span data-ttu-id="4bde0-109">**Microsoft BizTalk Server 構成**、 をクリックして**構成のインポート**します。</span><span class="sxs-lookup"><span data-stu-id="4bde0-109">In **Microsoft BizTalk Server Configuration**, click **Import Configuration**.</span></span>  
  
    <span data-ttu-id="4bde0-110">機能の前に表示される無効のアイコンがないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4bde0-110">Verify that there are no invalidation icons appearing in front of any feature.</span></span> <span data-ttu-id="4bde0-111">構成エラーがある機能のいずれかの場合は、それらを修正する時間をようになりました。</span><span class="sxs-lookup"><span data-stu-id="4bde0-111">If any of the features have configuration errors, now is the time to correct them.</span></span>  
  
4. <span data-ttu-id="4bde0-112">**[構成の適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4bde0-112">Click **Apply Configuration**.</span></span>  
  
    <span data-ttu-id="4bde0-113">BizTalk Server の機能が構成した後は、すべて、構成ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="4bde0-113">After all of the BizTalk Server features are configured, close the configuration window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bde0-114">参照</span><span class="sxs-lookup"><span data-stu-id="4bde0-114">See Also</span></span>  
 <span data-ttu-id="4bde0-115">[BizTalk Server を実行しているコンピューターの回復](../core/recovering-a-computer-running-biztalk-server.md) </span><span class="sxs-lookup"><span data-stu-id="4bde0-115">[Recovering a Computer Running BizTalk Server](../core/recovering-a-computer-running-biztalk-server.md) </span></span>  
 [<span data-ttu-id="4bde0-116">BizTalk Server の構成をバックアップする方法</span><span class="sxs-lookup"><span data-stu-id="4bde0-116">How to Back Up The BizTalk Server Configuration</span></span>](../core/how-to-back-up-the-biztalk-server-configuration.md)