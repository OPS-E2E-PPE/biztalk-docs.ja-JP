---
title: "送信ポート グループから送信ポートを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send port groups, deleting send ports
- managing [send port groups], deleting send ports
- managing [send ports], deleting send ports
- deleting, send ports
- send ports, deleting from send port groups
ms.assetid: a2289bfe-5bc9-4bc7-949c-5152ffb5bc62
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d109064a1286bcd622479a4075ef2d23dc8d320c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-send-port-from-a-send-port-group"></a><span data-ttu-id="734a3-102">送信ポート グループから送信ポートを削除する方法</span><span class="sxs-lookup"><span data-stu-id="734a3-102">How to Remove a Send Port from a Send Port Group</span></span>
<span data-ttu-id="734a3-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポート グループから特定の送信ポートを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="734a3-103">This topic describes how to use the BizTalk Server Administration console to remove a send port from a send port group.</span></span> <span data-ttu-id="734a3-104">送信ポートを送信ポート グループから削除しても、アプリケーションや BizTalk 管理データベースからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="734a3-104">When you do this, the send port is not deleted from the application or the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="734a3-105">削除する送信ポートは、あらかじめ停止状態または参加解除状態にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="734a3-105">Before you can remove a send port, it must be in a stopped or unenlisted state.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="734a3-106">メッセージをルーティングするには、送信ポート グループは、少なくとも 1 つの送信ポートを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="734a3-106">To route messages, a send port group must contain at least one send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="734a3-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="734a3-107">Prerequisites</span></span>  
 <span data-ttu-id="734a3-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="734a3-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="734a3-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="734a3-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-send-port-from-a-send-port-group"></a><span data-ttu-id="734a3-110">送信ポート グループから送信ポートを削除するには</span><span class="sxs-lookup"><span data-stu-id="734a3-110">To remove a send port from a send port group</span></span>  
  
1.  <span data-ttu-id="734a3-111">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="734a3-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="734a3-112">コンソール ツリーで、BizTalk グループを展開し、送信ポート グループから送信ポートを削除する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="734a3-112">In the console tree, expand the BizTalk group and the BizTalk application in which you want to remove a send port from a send port group.</span></span>  
  
3.  <span data-ttu-id="734a3-113">をクリックして**送信ポート グループ**送信ポート グループを右クリックし、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="734a3-113">Click **Send Port Groups**, right-click the send port group, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="734a3-114">**名前**をクリックしてをクリックし、削除、送信ポート**削除**です。</span><span class="sxs-lookup"><span data-stu-id="734a3-114">Under **Name**, click the send port to remove, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="734a3-115">参照</span><span class="sxs-lookup"><span data-stu-id="734a3-115">See Also</span></span>  
 <span data-ttu-id="734a3-116">[作成して、送信ポート グループを構成します。](../core/creating-and-configuring-send-port-groups.md) </span><span class="sxs-lookup"><span data-stu-id="734a3-116">[Creating and Configuring Send Port Groups](../core/creating-and-configuring-send-port-groups.md) </span></span>  
 [<span data-ttu-id="734a3-117">作成して、送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="734a3-117">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)