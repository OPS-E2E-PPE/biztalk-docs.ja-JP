---
title: 送信ポート グループから送信ポートを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send port groups, deleting send ports
- managing [send port groups], deleting send ports
- managing [send ports], deleting send ports
- deleting, send ports
- send ports, deleting from send port groups
ms.assetid: a2289bfe-5bc9-4bc7-949c-5152ffb5bc62
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c9ab95b645d3bcdcef249de9b65fcf3891677d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335049"
---
# <a name="how-to-remove-a-send-port-from-a-send-port-group"></a><span data-ttu-id="4c08c-102">送信ポート グループから送信ポートを削除する方法</span><span class="sxs-lookup"><span data-stu-id="4c08c-102">How to Remove a Send Port from a Send Port Group</span></span>
<span data-ttu-id="4c08c-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポート グループから送信ポートを削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="4c08c-103">This topic describes how to use the BizTalk Server Administration console to remove a send port from a send port group.</span></span> <span data-ttu-id="4c08c-104">これを行うと、送信ポートは、アプリケーションまたは BizTalk 管理データベースから削除されません。</span><span class="sxs-lookup"><span data-stu-id="4c08c-104">When you do this, the send port is not deleted from the application or the BizTalk Management database.</span></span>  
  
 <span data-ttu-id="4c08c-105">送信ポートを削除する前にこれは、停止または参加解除の状態に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c08c-105">Before you can remove a send port, it must be in a stopped or unenlisted state.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c08c-106">メッセージをルーティングするには、送信ポート グループは、少なくとも 1 つの送信ポートを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c08c-106">To route messages, a send port group must contain at least one send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4c08c-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="4c08c-107">Prerequisites</span></span>  
 <span data-ttu-id="4c08c-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c08c-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4c08c-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="4c08c-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-send-port-from-a-send-port-group"></a><span data-ttu-id="4c08c-110">送信ポート グループから送信ポートを削除するには</span><span class="sxs-lookup"><span data-stu-id="4c08c-110">To remove a send port from a send port group</span></span>  
  
1. <span data-ttu-id="4c08c-111">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="4c08c-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4c08c-112">コンソール ツリーで、BizTalk グループと、送信ポート グループから送信ポートを削除する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="4c08c-112">In the console tree, expand the BizTalk group and the BizTalk application in which you want to remove a send port from a send port group.</span></span>  
  
3. <span data-ttu-id="4c08c-113">クリックして**送信ポート グループ**送信ポート グループを右クリックし、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4c08c-113">Click **Send Port Groups**, right-click the send port group, and then click **Properties**.</span></span>  
  
4. <span data-ttu-id="4c08c-114">**名前**、してをクリックし、削除、送信ポートをクリックします。**削除**します。</span><span class="sxs-lookup"><span data-stu-id="4c08c-114">Under **Name**, click the send port to remove, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c08c-115">参照</span><span class="sxs-lookup"><span data-stu-id="4c08c-115">See Also</span></span>  
 <span data-ttu-id="4c08c-116">[作成と送信ポート グループの構成](../core/creating-and-configuring-send-port-groups.md) </span><span class="sxs-lookup"><span data-stu-id="4c08c-116">[Creating and Configuring Send Port Groups](../core/creating-and-configuring-send-port-groups.md) </span></span>  
 [<span data-ttu-id="4c08c-117">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="4c08c-117">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)