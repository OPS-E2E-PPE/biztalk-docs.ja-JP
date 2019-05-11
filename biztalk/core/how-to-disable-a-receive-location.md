---
title: 無効にする方法、受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], disabling
- receive locations, disabling
- disabling, receive locations
ms.assetid: 079a5c2c-3aec-49b3-afac-f3202404bca1
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67356b22c0cc4aeae6001a15a83245104a0048f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385202"
---
# <a name="how-to-disable-a-receive-location"></a><span data-ttu-id="31d25-102">無効にする方法、受信場所</span><span class="sxs-lookup"><span data-stu-id="31d25-102">How to Disable a Receive Location</span></span>
<span data-ttu-id="31d25-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所を無効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31d25-103">This topic describes how to use the BizTalk Server Administration console to disable a receive location.</span></span> <span data-ttu-id="31d25-104">受信場所を無効にすると、メッセージの受信を停止します。</span><span class="sxs-lookup"><span data-stu-id="31d25-104">When you disable a receive location, it stops receiving messages.</span></span> <span data-ttu-id="31d25-105">場合、受信場所を無効にした後できる再度有効にすること、もう一度メッセージを受信するようにします。</span><span class="sxs-lookup"><span data-stu-id="31d25-105">If you want, after disabling a receive location, you can enable it again, so that it will again receive messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="31d25-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="31d25-106">Prerequisites</span></span>  
 <span data-ttu-id="31d25-107">このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31d25-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="31d25-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="31d25-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-disable-a-receive-location"></a><span data-ttu-id="31d25-109">受信場所を無効にするには</span><span class="sxs-lookup"><span data-stu-id="31d25-109">To disable a receive location</span></span>  
  
1. <span data-ttu-id="31d25-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="31d25-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="31d25-111">コンソール ツリーで、BizTalk グループと受信場所を無効にする BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="31d25-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to disable a receive location.</span></span>  
  
3. <span data-ttu-id="31d25-112">をクリックして**受信場所**、受信場所を右クリックし、クリックして**を無効にする**します。</span><span class="sxs-lookup"><span data-stu-id="31d25-112">Click **Receive Locations**, right-click the receive location, and then click **Disable**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d25-113">参照</span><span class="sxs-lookup"><span data-stu-id="31d25-113">See Also</span></span>  
 <span data-ttu-id="31d25-114">[受信場所の管理](../core/managing-receive-locations.md) </span><span class="sxs-lookup"><span data-stu-id="31d25-114">[Managing Receive Locations](../core/managing-receive-locations.md) </span></span>  
 [<span data-ttu-id="31d25-115">有効にする方法、受信場所</span><span class="sxs-lookup"><span data-stu-id="31d25-115">How to Enable a Receive Location</span></span>](../core/how-to-enable-a-receive-location.md)