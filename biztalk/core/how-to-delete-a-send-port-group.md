---
title: 送信ポート グループを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting
- managing [send port groups], deleting
- deleting, send port groups
ms.assetid: 90c01e58-d35c-4cb2-ac6d-92199199fb42
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bf0e1a75799671ecd2e52515481c3d3be32ee67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013691"
---
# <a name="how-to-delete-a-send-port-group"></a><span data-ttu-id="6ea74-102">送信ポート グループを削除する方法</span><span class="sxs-lookup"><span data-stu-id="6ea74-102">How to Delete a Send Port Group</span></span>
<span data-ttu-id="6ea74-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポート グループを BizTalk アプリケーションから削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ea74-103">This topic describes how use the BizTalk Server Administration console to delete a send port group from a BizTalk application.</span></span> <span data-ttu-id="6ea74-104">送信ポート グループを BizTalk アプリケーションから削除すると、そのグループの BizTalk 管理データベースからも送信ポート グループが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6ea74-104">When you do this, the send port group is also deleted from the BizTalk Management database for the group.</span></span> <span data-ttu-id="6ea74-105">送信ポート グループを削除しても、そこに含まれる送信ポートは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6ea74-105">Deleting a send port group does not delete any send ports that it contains.</span></span>  
  
 <span data-ttu-id="6ea74-106">送信ポート グループを削除できるのは、次の条件を満たしている場合だけです。</span><span class="sxs-lookup"><span data-stu-id="6ea74-106">You can delete a send port group only if it meets the following conditions:</span></span>  
  
-   <span data-ttu-id="6ea74-107">送信ポート グループにオーケストレーションがバインドされていない: </span><span class="sxs-lookup"><span data-stu-id="6ea74-107">An orchestration is not bound to the send port group.</span></span> <span data-ttu-id="6ea74-108">次の手順で、バインドを削除するには、ケースの場合は、[オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="6ea74-108">If this is the case, you can remove the binding by following the instructions in [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
-   <span data-ttu-id="6ea74-109">送信ポート グループが停止および参加解除されている: </span><span class="sxs-lookup"><span data-stu-id="6ea74-109">The send port group is both stopped and unenlisted.</span></span> <span data-ttu-id="6ea74-110">停止、および送信ポートを参加解除については、[送信ポートまたは送信ポート グループを参加解除する方法](../core/how-to-unenlist-a-send-port-or-send-port-group.md)と[送信ポートまたは送信ポート グループを停止する方法](../core/how-to-stop-a-send-port-or-send-port-group.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ea74-110">For instructions on stopping and unenlisting a send port, see [How to Unenlist a Send Port or Send Port Group](../core/how-to-unenlist-a-send-port-or-send-port-group.md) and [How to Stop a Send Port or Send Port Group](../core/how-to-stop-a-send-port-or-send-port-group.md).</span></span>  
  
-   <span data-ttu-id="6ea74-111">送信ポート グループがパーティで参照されていない: </span><span class="sxs-lookup"><span data-stu-id="6ea74-111">The send port group is not referenced by a party.</span></span> <span data-ttu-id="6ea74-112">パーティから送信ポート グループへの参照を削除する方法の詳細については、[方法を表示または編集するパーティ](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ea74-112">For instructions on removing a reference to a send port group from a party, see [How to View or Edit a Party](http://msdn.microsoft.com/library/42e6f3a0-8f7d-4f6c-ab05-a1fab7bf46ca).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6ea74-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="6ea74-113">Prerequisites</span></span>  
 <span data-ttu-id="6ea74-114">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ea74-114">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6ea74-115">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="6ea74-115">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-send-port-group"></a><span data-ttu-id="6ea74-116">送信ポート グループを削除するには</span><span class="sxs-lookup"><span data-stu-id="6ea74-116">To delete a send port group</span></span>  
  
1. <span data-ttu-id="6ea74-117">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="6ea74-117">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="6ea74-118">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]展開し、BizTalk グループを展開し、**アプリケーション**、し、削除する送信ポート グループを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="6ea74-118">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the send port group that you want to delete.</span></span>  
  
3. <span data-ttu-id="6ea74-119">をクリックして**送信ポート グループ**送信ポート グループを右クリックし、クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="6ea74-119">Click **Send Port Groups**, right-click the send port group, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea74-120">参照</span><span class="sxs-lookup"><span data-stu-id="6ea74-120">See Also</span></span>  
 [<span data-ttu-id="6ea74-121">送信ポート グループの作成および構成</span><span class="sxs-lookup"><span data-stu-id="6ea74-121">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)