---
title: "オーケストレーションのインスタンスの情報を表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, viewing
- managing [orchestrations], viewing
ms.assetid: 860ac2b2-c556-4e1f-8b7f-18ab8be52db4
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84129d48fba15dadfc97722ead85b1535a8fa597
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-instance-information-for-an-orchestration"></a><span data-ttu-id="05f06-102">オーケストレーションのインスタンス情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="05f06-102">How to View Instance Information for an Orchestration</span></span>
<span data-ttu-id="05f06-103">このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションのインスタンス情報を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="05f06-103">This topic describes how to view instance information for an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="05f06-104">サービスのインスタンスとは、後続の処理や追跡を目的に BizTalk Server が処理しているオーケストレーションのインスタンス、または、メッセージ ボックスにシリアル化したオーケストレーションのインスタンスを指します。</span><span class="sxs-lookup"><span data-stu-id="05f06-104">A service instance is an instance of an orchestration that BizTalk Server is either processing or has serialized into the MessageBox for further processing or tracking.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="05f06-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="05f06-105">Prerequisites</span></span>  
 <span data-ttu-id="05f06-106">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="05f06-106">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="05f06-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="05f06-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-an-orchestration"></a><span data-ttu-id="05f06-108">オーケストレーションのインスタンス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="05f06-108">To view instance information for an orchestration</span></span>  
  
1.  <span data-ttu-id="05f06-109">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="05f06-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="05f06-110">コンソール ツリーで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、BizTalk グループを展開し、**アプリケーション**、し、インスタンス情報を表示するオーケストレーションを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="05f06-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to view instance information.</span></span>  
  
3.  <span data-ttu-id="05f06-111">をクリックして**オーケストレーション**インスタンス情報を表示するオーケストレーションをクリックして**ビュー**、し、**インスタンス情報**です。</span><span class="sxs-lookup"><span data-stu-id="05f06-111">Click **Orchestrations**, select the orchestration for which you want to view instance information, click **View**, and then select **Instance Information**.</span></span>  
  
     <span data-ttu-id="05f06-112">ページ下部のクエリ結果パネルに、オーケストレーションのすべてのインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="05f06-112">The query results panel in the lower section of the page displays all instances of the orchestration.</span></span>  
  
     <span data-ttu-id="05f06-113">オーケストレーションの別のインスタンス情報をクエリおよびビューを絞り込むを下にあるボックスをクリックして**値**、検索対象フィールドの表示、およびをクリックするインスタンスの種類を選択して**クエリの実行**です。</span><span class="sxs-lookup"><span data-stu-id="05f06-113">To refine the query and view different instance information for the orchestration, click the box under **Value** for the Search For field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="05f06-114">クエリの作成の詳細については、「関連項目」で検索に関するトピックを選んで参照してください。</span><span class="sxs-lookup"><span data-stu-id="05f06-114">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05f06-115">参照</span><span class="sxs-lookup"><span data-stu-id="05f06-115">See Also</span></span>  
 <span data-ttu-id="05f06-116">[オーケストレーションの管理](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="05f06-116">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="05f06-117">[実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="05f06-117">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="05f06-118">[中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="05f06-118">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="05f06-119">[メッセージを検索する方法](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="05f06-119">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="05f06-120">サブスクリプションを検索する方法</span><span class="sxs-lookup"><span data-stu-id="05f06-120">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)