---
title: 削除する方法、受信ポート |Microsoft ドキュメント
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
ms.openlocfilehash: 0c5ad0b1d69747f3a890fbc20c63b8aa76c30639
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249074"
---
# <a name="how-to-delete-a-receive-port"></a><span data-ttu-id="5a307-102">受信ポートを削除する方法</span><span class="sxs-lookup"><span data-stu-id="5a307-102">How to Delete a Receive Port</span></span>
<span data-ttu-id="5a307-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートを BizTalk アプリケーションから削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5a307-103">This topic describes how to use the BizTalk Server Administration console to delete a receive port from a BizTalk application.</span></span> <span data-ttu-id="5a307-104">受信ポートを BizTalk アプリケーションから削除すると、そのグループの BizTalk 管理データベースからも受信ポートが削除され、およびこの受信ポートに含まれているすべての受信場所が削除されます。</span><span class="sxs-lookup"><span data-stu-id="5a307-104">When you do this, the receive port is also deleted from the BizTalk Management database for the group, as are all receive locations in this receive port.</span></span>  
  
 <span data-ttu-id="5a307-105">受信ポートがオーケストレーションにバインドされていると、この操作は正常に行われません。</span><span class="sxs-lookup"><span data-stu-id="5a307-105">For this operation to succeed, the receive port cannot be bound to an orchestration.</span></span> <span data-ttu-id="5a307-106">受信ポートのバインドを削除する方法の詳細については、次を参照してください。[オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="5a307-106">For instructions on removing the bindings for a receive port, see [How to Unbind an Orchestration](../core/how-to-unbind-an-orchestration.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a307-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="5a307-107">Prerequisites</span></span>  
 <span data-ttu-id="5a307-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a307-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="5a307-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="5a307-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-delete-a-receive-port"></a><span data-ttu-id="5a307-110">受信ポートを削除するには</span><span class="sxs-lookup"><span data-stu-id="5a307-110">To delete a receive port</span></span>  
  
1.  <span data-ttu-id="5a307-111">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="5a307-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5a307-112">コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、BizTalk グループを展開し、**アプリケーション**、し、削除する受信ポートを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="5a307-112">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the receive port that you want to delete.</span></span>  
  
3.  <span data-ttu-id="5a307-113">をクリックして**受信ポート**受信ポートを右クリックし、クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="5a307-113">Click **Receive Ports**, right-click the receive port, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a307-114">参照</span><span class="sxs-lookup"><span data-stu-id="5a307-114">See Also</span></span>  
 [<span data-ttu-id="5a307-115">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="5a307-115">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)