---
title: 追加する方法、受信場所が、受信ポート |Microsoft ドキュメント
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
ms.openlocfilehash: 01a2d51103e8554a221d1598558a0180850c4a5a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247386"
---
# <a name="how-to-add-a-receive-location-to-a-receive-port"></a><span data-ttu-id="e4e26-102">受信ポートに受信場所を追加する方法</span><span class="sxs-lookup"><span data-stu-id="e4e26-102">How to Add a Receive Location to a Receive Port</span></span>
<span data-ttu-id="e4e26-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートに新しい受信場所を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4e26-103">This topic describes how to use the BizTalk Server Administration console to add a new receive location to a receive port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4e26-104">バインドできます受信ポートをオーケストレーションに、アプリケーションを構成するときに」の説明に従って[アプリケーションを構成する方法](../core/how-to-configure-an-application.md)」の説明に従って、オーケストレーションをバインドする場合または[のバインドを構成する方法、オーケストレーション](../core/how-to-configure-bindings-for-an-orchestration.md)です。</span><span class="sxs-lookup"><span data-stu-id="e4e26-104">You can bind a receive port to an orchestration when you configure an application, as described in [How to Configure an Application](../core/how-to-configure-an-application.md) or when you bind an orchestration, as described in [How to Configure Bindings for an Orchestration](../core/how-to-configure-bindings-for-an-orchestration.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e4e26-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="e4e26-105">Prerequisites</span></span>  
 <span data-ttu-id="e4e26-106">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4e26-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="e4e26-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="e4e26-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-receive-location-to-a-receive-port"></a><span data-ttu-id="e4e26-108">受信ポートに受信場所を追加するには</span><span class="sxs-lookup"><span data-stu-id="e4e26-108">To add a receive location to a receive port</span></span>  
  
1.  <span data-ttu-id="e4e26-109">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="e4e26-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e4e26-110">コンソール ツリーで、BizTalk グループを展開し、受信ポートに受信場所を追加する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="e4e26-110">In the console tree, expand the BizTalk group and the BizTalk application for which you want to add a receive location to a receive port.</span></span>  
  
3.  <span data-ttu-id="e4e26-111">をクリックして**受信ポート**をポイントし、受信場所を追加する受信ポートを右クリックして**新規**、順にクリック**受信場所の**します。</span><span class="sxs-lookup"><span data-stu-id="e4e26-111">Click **Receive Ports**, right-click the receive port to which you want to add a receive location, point to **New**, and then click **Receive Location**.</span></span>  
  
4.  <span data-ttu-id="e4e26-112">**名前**、新しい受信場所の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e4e26-112">In **Name**, type a name for the new receive location.</span></span>  
  
5.  <span data-ttu-id="e4e26-113">次の手順で、受信場所のプロパティを構成する[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)、順にクリック **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="e4e26-113">Configure properties for the receive location by following the instructions in [How to Create a Receive Location](../core/how-to-create-a-receive-location.md), and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4e26-114">参照</span><span class="sxs-lookup"><span data-stu-id="e4e26-114">See Also</span></span>  
 [<span data-ttu-id="e4e26-115">受信ポートの管理</span><span class="sxs-lookup"><span data-stu-id="e4e26-115">Managing Receive Ports</span></span>](../core/managing-receive-ports.md)