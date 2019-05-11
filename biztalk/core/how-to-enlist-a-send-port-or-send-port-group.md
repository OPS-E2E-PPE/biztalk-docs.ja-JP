---
title: 送信ポートまたは送信ポート グループを参加させる方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enlisting, send port groups
- enlisting, send ports
- send port groups, enlisting
- send ports, enlisting
- managing [send ports], enlisting
- managing [send port groups], enlisting
ms.assetid: d4298b8e-7dc7-4382-af86-c4db0982b7e0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb7ff544b1c6d5ae5559dd4b64348a92cacb56b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337893"
---
# <a name="how-to-enlist-a-send-port-or-send-port-group"></a><span data-ttu-id="f449c-102">送信ポートまたは送信ポート グループを参加させる方法</span><span class="sxs-lookup"><span data-stu-id="f449c-102">How to Enlist a Send Port or Send Port Group</span></span>
<span data-ttu-id="f449c-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートまたは送信ポート グループを参加させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f449c-103">This topic describes how to use the BizTalk Server Administration console to enlist a send port or send port group.</span></span> <span data-ttu-id="f449c-104">送信ポートまたは送信ポート グループを参加させると、送信ポートまたは送信ポート グループが BizTalk ホストに関連付けられ、送信ポートまたは送信ポート グループのサブスクリプションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f449c-104">Enlisting a send port or send port group associates the send port or send port group with a BizTalk host and creates the subscriptions for the send port or send port group.</span></span> <span data-ttu-id="f449c-105">送信ポート グループに送信ポートが含まれていない場合は、送信ポート グループを参加させてもサブスクリプションは作成されません。</span><span class="sxs-lookup"><span data-stu-id="f449c-105">If a send port group does not contain a send port, enlisting the send port group does not create any subscriptions.</span></span> <span data-ttu-id="f449c-106">また、送信ポート グループを参加させても、送信ポート グループに含まれている送信ポートの状態は変わりません。</span><span class="sxs-lookup"><span data-stu-id="f449c-106">In addition, enlisting a send port group does not change the state of any send ports that it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f449c-107">送信ポートまたは送信ポート グループを開始すると、自動的に参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="f449c-107">Starting a send port or send port group also automatically enlists it.</span></span> <span data-ttu-id="f449c-108">既定では、アプリケーションを開始すると、そこに含まれるすべてのアイテムを開始して参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="f449c-108">In addition, by default starting an application enlists and starts all of its artifacts.</span></span> <span data-ttu-id="f449c-109">詳細については、次を参照してください。[送信ポートまたは送信ポート グループを開始する方法](../core/how-to-start-a-send-port-or-send-port-group.md)します。</span><span class="sxs-lookup"><span data-stu-id="f449c-109">For more information, see [How to Start a Send Port or Send Port Group](../core/how-to-start-a-send-port-or-send-port-group.md).</span></span> <span data-ttu-id="f449c-110">参照してください[BizTalk アプリケーション開始および停止方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="f449c-110">Also see [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f449c-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="f449c-111">Prerequisites</span></span>  
 <span data-ttu-id="f449c-112">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f449c-112">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="f449c-113">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="f449c-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-enlist-a-send-port-or-send-port-group"></a><span data-ttu-id="f449c-114">送信ポートまたは送信ポート グループを参加させるには</span><span class="sxs-lookup"><span data-stu-id="f449c-114">To enlist a send port or send port group</span></span>  
  
1. <span data-ttu-id="f449c-115">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f449c-115">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f449c-116">コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、送信ポートまたは送信ポート グループにするを含むアプリケーションを展開し、参加します。</span><span class="sxs-lookup"><span data-stu-id="f449c-116">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group, expand **Applications**, and then expand the application containing the send port or send port group that you want to enlist.</span></span>  
  
3. <span data-ttu-id="f449c-117">クリックして**送信ポート**または**送信ポート グループ**送信ポートまたは送信ポート グループを右クリックし、クリックして**参加**します。</span><span class="sxs-lookup"><span data-stu-id="f449c-117">Click **Send Ports** or **Send Port Groups**, right-click the send port or send port group, and then click **Enlist**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f449c-118">参照</span><span class="sxs-lookup"><span data-stu-id="f449c-118">See Also</span></span>  
 [<span data-ttu-id="f449c-119">送信ポートと送信ポート グループの管理</span><span class="sxs-lookup"><span data-stu-id="f449c-119">Managing Send Ports and Send Port Groups</span></span>](../core/managing-send-ports-and-send-port-groups.md)