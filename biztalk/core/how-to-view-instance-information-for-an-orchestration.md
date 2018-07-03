---
title: オーケストレーションのインスタンス情報を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, viewing
- managing [orchestrations], viewing
ms.assetid: 860ac2b2-c556-4e1f-8b7f-18ab8be52db4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 761f29d6f341410fec544fb0d6fdc032f671775c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983995"
---
# <a name="how-to-view-instance-information-for-an-orchestration"></a><span data-ttu-id="a4ac3-102">オーケストレーションのインスタンス情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="a4ac3-102">How to View Instance Information for an Orchestration</span></span>
<span data-ttu-id="a4ac3-103">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションのインスタンス情報を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a4ac3-103">This topic describes how to view instance information for an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="a4ac3-104">サービスのインスタンスとは、後続の処理や追跡を目的に BizTalk Server が処理しているオーケストレーションのインスタンス、または、メッセージ ボックスにシリアル化したオーケストレーションのインスタンスを指します。</span><span class="sxs-lookup"><span data-stu-id="a4ac3-104">A service instance is an instance of an orchestration that BizTalk Server is either processing or has serialized into the MessageBox for further processing or tracking.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a4ac3-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="a4ac3-105">Prerequisites</span></span>  
 <span data-ttu-id="a4ac3-106">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a4ac3-106">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a4ac3-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="a4ac3-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-an-orchestration"></a><span data-ttu-id="a4ac3-108">オーケストレーションのインスタンス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="a4ac3-108">To view instance information for an orchestration</span></span>  
  
1. <span data-ttu-id="a4ac3-109">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="a4ac3-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a4ac3-110">コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]展開し、BizTalk グループを展開し、**アプリケーション**、し、インスタンス情報を表示するオーケストレーションを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="a4ac3-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to view instance information.</span></span>  
  
3. <span data-ttu-id="a4ac3-111">をクリックして**オーケストレーション**を選択、オーケストレーション インスタンスの情報を表示する] をクリックして**ビュー**、し、[**インスタンス情報**。</span><span class="sxs-lookup"><span data-stu-id="a4ac3-111">Click **Orchestrations**, select the orchestration for which you want to view instance information, click **View**, and then select **Instance Information**.</span></span>  
  
    <span data-ttu-id="a4ac3-112">ページ下部のクエリ結果パネルに、オーケストレーションのすべてのインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a4ac3-112">The query results panel in the lower section of the page displays all instances of the orchestration.</span></span>  
  
    <span data-ttu-id="a4ac3-113">オーケストレーションのクエリおよびビューの別のインスタンス情報を絞り込む、下にあるボックスをクリックします。**値**、検索対象フィールドの表示、およびクリックするインスタンスの種類を選択します。**クエリの実行**します。</span><span class="sxs-lookup"><span data-stu-id="a4ac3-113">To refine the query and view different instance information for the orchestration, click the box under **Value** for the Search For field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="a4ac3-114">クエリの作成の詳細については、「関連項目」で検索に関するトピックを選んで参照してください。</span><span class="sxs-lookup"><span data-stu-id="a4ac3-114">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ac3-115">参照</span><span class="sxs-lookup"><span data-stu-id="a4ac3-115">See Also</span></span>  
 <span data-ttu-id="a4ac3-116">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="a4ac3-116">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="a4ac3-117">[実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="a4ac3-117">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="a4ac3-118">[中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="a4ac3-118">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="a4ac3-119">[メッセージを検索する方法](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a4ac3-119">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="a4ac3-120">サブスクリプションを検索する方法</span><span class="sxs-lookup"><span data-stu-id="a4ac3-120">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)