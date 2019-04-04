---
title: 削除する方法、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], deleting
- deleting, receive ports
- receive ports, deleting
ms.assetid: 69cd86f7-e3cc-4a50-8d15-5f978c94a6be
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65f72ad5bfef99bca7474ea01f3d07ecbe9ef2b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975155"
---
# <a name="how-to-delete-a-receive-port"></a><span data-ttu-id="879d5-102">受信ポートを削除する方法</span><span class="sxs-lookup"><span data-stu-id="879d5-102">How to Delete a Receive Port</span></span>
<span data-ttu-id="879d5-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートを BizTalk アプリケーションから削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="879d5-103">This topic describes how to use the BizTalk Server Administration console to delete a receive port from a BizTalk application.</span></span> <span data-ttu-id="879d5-104">受信ポートを BizTalk アプリケーションから削除すると、そのグループの BizTalk 管理データベースからも受信ポートが削除され、およびこの受信ポートに含まれているすべての受信場所が削除されます。</span><span class="sxs-lookup"><span data-stu-id="879d5-104">When you do this, the receive port is also deleted from the BizTalk Management database for the group, as are all receive locations in this receive port.</span></span>  
  
 <span data-ttu-id="879d5-105">受信ポートがオーケストレーションにバインドされていると、この操作は正常に行われません。</span><span class="sxs-lookup"><span data-stu-id="879d5-105">For this operation to succeed, the receive port cannot be bound to an orchestration.</span></span> <span data-ttu-id="879d5-106">受信ポートのバインドを削除する方法の詳細については、[オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="879d5-106">For instructions on removing the bindings for a receive port, see [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="879d5-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="879d5-107">Prerequisites</span></span>  
 <span data-ttu-id="879d5-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="879d5-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="879d5-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="879d5-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-receive-port"></a><span data-ttu-id="879d5-110">受信ポートを削除するには</span><span class="sxs-lookup"><span data-stu-id="879d5-110">To delete a receive port</span></span>  
  
1. <span data-ttu-id="879d5-111">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="879d5-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="879d5-112">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]展開し、BizTalk グループを展開し、**アプリケーション**、し、削除する受信ポートを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="879d5-112">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the receive port that you want to delete.</span></span>  
  
3. <span data-ttu-id="879d5-113">クリックして**受信ポート**受信ポートを右クリックし、クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="879d5-113">Click **Receive Ports**, right-click the receive port, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="879d5-114">参照</span><span class="sxs-lookup"><span data-stu-id="879d5-114">See Also</span></span>  
 [<span data-ttu-id="879d5-115">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="879d5-115">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)