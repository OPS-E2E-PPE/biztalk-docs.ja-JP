---
title: インスタンス情報を表示する方法、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], viewing
- receive ports, viewing
- viewing, receive ports
ms.assetid: dad038bc-1202-489b-b144-a93bf1f53c0c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ece5525e18eda82d480adec407f92f9f632453e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970251"
---
# <a name="how-to-view-instance-information-for-a-receive-port"></a><span data-ttu-id="60805-102">受信ポートのインスタンス情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="60805-102">How to View Instance Information for a Receive Port</span></span>
<span data-ttu-id="60805-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートのサービス インスタンスを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="60805-103">This topic describes how to use the BizTalk Server Administration console to view the service instances for a receive port.</span></span> <span data-ttu-id="60805-104">受信ポートでメッセージを受け取るたびに、メッセージを処理するサービス インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="60805-104">Each time the receive port receives a message, a service instance is created to process the message.</span></span> <span data-ttu-id="60805-105">このトピックの手順を実行すると、受信ポートのグループ概要ページにインスタンス情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="60805-105">When you follow the procedure in this topic, instance information displays in the Group Overview page for the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="60805-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="60805-106">Prerequisites</span></span>  
 <span data-ttu-id="60805-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="60805-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="60805-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="60805-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-a-receive-port"></a><span data-ttu-id="60805-109">受信ポートのインスタンス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="60805-109">To view instance information for a receive port</span></span>  
  
1. <span data-ttu-id="60805-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="60805-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="60805-111">コンソール ツリーで、BizTalk グループを展開し、受信ポートのインスタンス情報を表示する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="60805-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to view instance information for a receive port.</span></span>  
  
3. <span data-ttu-id="60805-112">クリックして**受信ポート**、受信ポートの選択**ビュー**、順にクリックします**インスタンス情報**します。</span><span class="sxs-lookup"><span data-stu-id="60805-112">Click **Receive Ports**, select the receive port, click **View**, and then click **Instance Information**.</span></span>  
  
    <span data-ttu-id="60805-113">ページ下部のクエリ結果パネルに、受信ポートのすべてのインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60805-113">The query results panel in the lower section of the page displays all instances of the receive port.</span></span>  
  
4. <span data-ttu-id="60805-114">受信ポートの別のインスタンス情報を表示して、クエリを絞り込む、下にあるボックスをクリックします**値**の、**検索の**フィールドで、表示する をクリックし、インスタンスの種類を選択します。**実行。クエリ**します。</span><span class="sxs-lookup"><span data-stu-id="60805-114">To refine the query and view different instance information for the receive port, click the box under **Value** for the **Search For** field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="60805-115">クエリの作成の詳細については、「関連項目」で検索に関するトピックを選んで参照してください。</span><span class="sxs-lookup"><span data-stu-id="60805-115">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60805-116">参照</span><span class="sxs-lookup"><span data-stu-id="60805-116">See Also</span></span>  
 <span data-ttu-id="60805-117">[受信ポートの管理](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="60805-117">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 <span data-ttu-id="60805-118">[実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="60805-118">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="60805-119">[中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="60805-119">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="60805-120">[メッセージを検索する方法](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="60805-120">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="60805-121">サブスクリプションを検索する方法</span><span class="sxs-lookup"><span data-stu-id="60805-121">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)