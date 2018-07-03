---
title: 追加する方法、受信場所が、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, adding to receive ports
- managing [receive ports], adding receive locations
- receive ports, adding receive locations
- adding, receive locations
ms.assetid: a71d50dc-629e-4b7f-aa59-6d2274d4cac3
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c657c96c7714f04d18a2bd8d6d2d7ef90ad9cbd1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999003"
---
# <a name="how-to-add-a-receive-location-to-a-receive-port"></a><span data-ttu-id="5e635-102">受信ポートに受信場所を追加する方法</span><span class="sxs-lookup"><span data-stu-id="5e635-102">How to Add a Receive Location to a Receive Port</span></span>
<span data-ttu-id="5e635-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートに新しい受信場所を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e635-103">This topic describes how to use the BizTalk Server Administration console to add a new receive location to a receive port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e635-104">バインドできます受信ポートをオーケストレーションに、アプリケーションを構成するときに」の説明に従って[アプリケーションを構成する方法](../core/how-to-configure-an-application.md)」の説明に従って、オーケストレーションをバインドする場合または[のバインドを構成する方法、オーケストレーション](../core/how-to-configure-bindings-for-an-orchestration.md)します。</span><span class="sxs-lookup"><span data-stu-id="5e635-104">You can bind a receive port to an orchestration when you configure an application, as described in [How to Configure an Application](../core/how-to-configure-an-application.md) or when you bind an orchestration, as described in [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5e635-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="5e635-105">Prerequisites</span></span>  
 <span data-ttu-id="5e635-106">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e635-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="5e635-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="5e635-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-receive-location-to-a-receive-port"></a><span data-ttu-id="5e635-108">受信ポートに受信場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="5e635-108">To add a receive location to a receive port</span></span>  
  
1. <span data-ttu-id="5e635-109">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="5e635-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="5e635-110">コンソール ツリーで、BizTalk グループを展開し、受信ポートに受信場所を追加する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="5e635-110">In the console tree, expand the BizTalk group and the BizTalk application for which you want to add a receive location to a receive port.</span></span>  
  
3. <span data-ttu-id="5e635-111">クリックして**受信ポート**、ポイントして、受信場所を追加する受信ポートを右クリックして**新規**、順にクリックします**受信場所**します。</span><span class="sxs-lookup"><span data-stu-id="5e635-111">Click **Receive Ports**, right-click the receive port to which you want to add a receive location, point to **New**, and then click **Receive Location**.</span></span>  
  
4. <span data-ttu-id="5e635-112">**名前**、新しい受信場所の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="5e635-112">In **Name**, type a name for the new receive location.</span></span>  
  
5. <span data-ttu-id="5e635-113">次の手順で、受信場所のプロパティを構成する[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="5e635-113">Configure properties for the receive location by following the instructions in [How to Create a Receive Location](../core/how-to-create-a-receive-location.md), and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e635-114">参照</span><span class="sxs-lookup"><span data-stu-id="5e635-114">See Also</span></span>  
 [<span data-ttu-id="5e635-115">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="5e635-115">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)