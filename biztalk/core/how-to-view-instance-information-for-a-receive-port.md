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
ms.openlocfilehash: 520e3e5de989f1a9800fab21a31f2997f634d8e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383128"
---
# <a name="how-to-view-instance-information-for-a-receive-port"></a><span data-ttu-id="a5a40-102">インスタンス情報を表示する方法、受信ポート</span><span class="sxs-lookup"><span data-stu-id="a5a40-102">How to View Instance Information for a Receive Port</span></span>
<span data-ttu-id="a5a40-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートのサービス インスタンスを表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5a40-103">This topic describes how to use the BizTalk Server Administration console to view the service instances for a receive port.</span></span> <span data-ttu-id="a5a40-104">受信ポートがメッセージを受信するたびに、サービス インスタンスは、メッセージの処理に作成されます。</span><span class="sxs-lookup"><span data-stu-id="a5a40-104">Each time the receive port receives a message, a service instance is created to process the message.</span></span> <span data-ttu-id="a5a40-105">このトピックの手順を実行するときに、受信ポートのグループ概要ページにインスタンス情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5a40-105">When you follow the procedure in this topic, instance information displays in the Group Overview page for the receive port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a5a40-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="a5a40-106">Prerequisites</span></span>  
 <span data-ttu-id="a5a40-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5a40-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a5a40-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="a5a40-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-a-receive-port"></a><span data-ttu-id="a5a40-109">受信ポートのインスタンス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="a5a40-109">To view instance information for a receive port</span></span>  
  
1. <span data-ttu-id="a5a40-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="a5a40-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a5a40-111">コンソール ツリーで、BizTalk グループと受信ポートのインスタンス情報を表示する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="a5a40-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to view instance information for a receive port.</span></span>  
  
3. <span data-ttu-id="a5a40-112">クリックして**受信ポート**、受信ポートの選択**ビュー**、順にクリックします**インスタンス情報**します。</span><span class="sxs-lookup"><span data-stu-id="a5a40-112">Click **Receive Ports**, select the receive port, click **View**, and then click **Instance Information**.</span></span>  
  
    <span data-ttu-id="a5a40-113">ページの下部に、クエリ結果 パネルには、受信ポートのすべてのインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5a40-113">The query results panel in the lower section of the page displays all instances of the receive port.</span></span>  
  
4. <span data-ttu-id="a5a40-114">受信ポートの別のインスタンス情報を表示して、クエリを絞り込む、下にあるボックスをクリックします**値**の、**検索の**フィールドで、表示する をクリックし、インスタンスの種類を選択します。**実行。クエリ**します。</span><span class="sxs-lookup"><span data-stu-id="a5a40-114">To refine the query and view different instance information for the receive port, click the box under **Value** for the **Search For** field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="a5a40-115">クエリの作成に関する詳細については、参照の検索のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5a40-115">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5a40-116">参照</span><span class="sxs-lookup"><span data-stu-id="a5a40-116">See Also</span></span>  
 <span data-ttu-id="a5a40-117">[受信ポートの管理](../core/managing-receive-ports.md) </span><span class="sxs-lookup"><span data-stu-id="a5a40-117">[Managing Receive Ports](../core/managing-receive-ports.md) </span></span>  
 <span data-ttu-id="a5a40-118">[実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="a5a40-118">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="a5a40-119">[中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="a5a40-119">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="a5a40-120">[メッセージを検索する方法](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a5a40-120">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="a5a40-121">サブスクリプションを検索する方法</span><span class="sxs-lookup"><span data-stu-id="a5a40-121">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)