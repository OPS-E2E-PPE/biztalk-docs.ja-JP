---
title: 送信ポートまたは送信ポート グループを停止する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send ports], stopping
- managing [send port groups], stopping
- stopping, send ports
- send port groups, stopping
- stopping, send port groups
- send ports, stopping
ms.assetid: a7a5eab3-34fe-4417-900a-c37ec16ec009
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94ac3391a7a14955198f7e7635765665d48af1ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255322"
---
# <a name="how-to-stop-a-send-port-or-send-port-group"></a><span data-ttu-id="6a526-102">送信ポートまたは送信ポート グループを停止する方法</span><span class="sxs-lookup"><span data-stu-id="6a526-102">How to Stop a Send Port or Send Port Group</span></span>
<span data-ttu-id="6a526-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを停止する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a526-103">This topic describes how to use the BizTalk Server Administration console to stop a send port or send port group.</span></span> <span data-ttu-id="6a526-104">送信ポートまたは送信ポート グループを停止すると、それ以降、メッセージは処理されなくなります。</span><span class="sxs-lookup"><span data-stu-id="6a526-104">When you stop a send port or send port group, it no longer processes messages.</span></span> <span data-ttu-id="6a526-105">BizTalk Server は、停止された送信ポートまたは送信ポート グループに対する、すべてのアクティベーション メッセージを中断します。</span><span class="sxs-lookup"><span data-stu-id="6a526-105">BizTalk Server suspends all activation messages to a stopped send port or send port group.</span></span> <span data-ttu-id="6a526-106">ただし、送信ポート グループを停止しても、そこに含まれる個々の送信ポートの状態は変わりません。</span><span class="sxs-lookup"><span data-stu-id="6a526-106">Stopping a send port group does not affect the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a526-107">既定では、BizTalk アプリケーションを開始すると、そこに含まれるすべてのアイテムが開始されます。</span><span class="sxs-lookup"><span data-stu-id="6a526-107">By default, starting a BizTalk application starts all of the artifacts that it contains.</span></span> <span data-ttu-id="6a526-108">詳細については、次を参照してください。[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="6a526-108">For more information, see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6a526-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="6a526-109">Prerequisites</span></span>  
 <span data-ttu-id="6a526-110">このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a526-110">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6a526-111">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="6a526-111">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-stop-a-send-port-or-send-port-group"></a><span data-ttu-id="6a526-112">送信ポートまたは送信ポート グループを停止するには</span><span class="sxs-lookup"><span data-stu-id="6a526-112">To stop a send port or send port group</span></span>  
  
1.  <span data-ttu-id="6a526-113">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="6a526-113">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6a526-114">コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、送信ポートまたはする送信ポート グループを含むアプリケーションを展開停止します。</span><span class="sxs-lookup"><span data-stu-id="6a526-114">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to stop.</span></span>  
  
3.  <span data-ttu-id="6a526-115">をクリックして**送信ポート**または**送信ポート グループ**送信ポートを右クリックし、または送信ポートと、をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="6a526-115">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port, and then click **Stop**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a526-116">参照</span><span class="sxs-lookup"><span data-stu-id="6a526-116">See Also</span></span>  
 [<span data-ttu-id="6a526-117">送信ポートと送信ポート グループの管理</span><span class="sxs-lookup"><span data-stu-id="6a526-117">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)