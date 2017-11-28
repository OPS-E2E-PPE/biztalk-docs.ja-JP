---
title: "送信ポートのインスタンスの情報を表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, viewing
- managing [send ports], viewing
- viewing, send ports
ms.assetid: 37cf6561-5341-4a05-b531-33ab0334966e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78632bdb9b5da6d4fd4de7fc35b91f410e2e5f42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-view-instance-information-for-a-send-port"></a><span data-ttu-id="89134-102">送信ポートのインスタンス情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="89134-102">How to View Instance Information for a Send Port</span></span>
<span data-ttu-id="89134-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートの実行中のサービス インスタンスを一覧表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89134-103">This topic describes how to use the BizTalk Server Administration console to view a list of the running service instances of a send port.</span></span> <span data-ttu-id="89134-104">サービス インスタンスとは、メッセージが送信ポートに送信されたときに作成される、送信ポート サービスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="89134-104">A service instance is an instance of the send port service that is created when a message is sent to the send port.</span></span> <span data-ttu-id="89134-105">このトピックの手順を実行すると、送信ポートのグループ概要ページにインスタンス情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="89134-105">When you follow the procedure in this topic, instance information displays in the Group Overview page for the send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="89134-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="89134-106">Prerequisites</span></span>  
 <span data-ttu-id="89134-107">このトピックの手順を実行するには、BizTalk Server 管理者グループまたは BizTalk Server Operators グループのメンバー アカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89134-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> <span data-ttu-id="89134-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="89134-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-a-send-port"></a><span data-ttu-id="89134-109">送信ポートのインスタンス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="89134-109">To view instance information for a send port</span></span>  
  
1.  <span data-ttu-id="89134-110">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="89134-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="89134-111">コンソール ツリーで、BizTalk グループを展開し、送信ポートのサービス インスタンス情報を表示する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="89134-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to view service instance information for a send port.</span></span>  
  
3.  <span data-ttu-id="89134-112">をクリックして**送信ポート**、送信ポートを右クリックし、順にポイント**ビュー**、順にクリック**インスタンス情報**です。</span><span class="sxs-lookup"><span data-stu-id="89134-112">Click **Send Ports**, right-click the send port, point to **View**, and then click **Instance Information**.</span></span>  
  
     <span data-ttu-id="89134-113">ページ下部のクエリ結果パネルに、送信ポートの実行中のインスタンスがすべて表示されます。</span><span class="sxs-lookup"><span data-stu-id="89134-113">The query results panel in the lower section of the page displays all running instances of the send port.</span></span>  
  
4.  <span data-ttu-id="89134-114">クエリを絞り込んで、送信ポートの別のサービス インスタンスの情報を表示 のボックスをクリックして**値**、検索対象フィールドの表示、およびをクリックするインスタンスの種類を選択して**クエリの実行**です。</span><span class="sxs-lookup"><span data-stu-id="89134-114">To refine the query and view different service instance information for the send port, click the box under **Value** for the Search For field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="89134-115">クエリの作成の詳細については、「関連項目」で検索に関するトピックを選んで参照してください。</span><span class="sxs-lookup"><span data-stu-id="89134-115">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89134-116">参照</span><span class="sxs-lookup"><span data-stu-id="89134-116">See Also</span></span>  
 <span data-ttu-id="89134-117">[作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="89134-117">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 <span data-ttu-id="89134-118">[実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="89134-118">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="89134-119">[中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="89134-119">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="89134-120">[メッセージを検索する方法](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="89134-120">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="89134-121">サブスクリプションを検索する方法</span><span class="sxs-lookup"><span data-stu-id="89134-121">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)