---
title: 送信ポートのインスタンス情報を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, viewing
- managing [send ports], viewing
- viewing, send ports
ms.assetid: 37cf6561-5341-4a05-b531-33ab0334966e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcb1dc5c055a28ce3a651546e21744017c6bc5dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333093"
---
# <a name="how-to-view-instance-information-for-a-send-port"></a><span data-ttu-id="f5240-102">送信ポートのインスタンス情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="f5240-102">How to View Instance Information for a Send Port</span></span>
<span data-ttu-id="f5240-103">このトピックでは、BizTalk Server 管理コンソールを使用して、実行の一覧を表示する方法を説明します。 送信ポートのインスタンスのサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f5240-103">This topic describes how to use the BizTalk Server Administration console to view a list of the running service instances of a send port.</span></span> <span data-ttu-id="f5240-104">サービス インスタンスは、メッセージが送信ポートに送信されるときに作成される送信ポート サービスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f5240-104">A service instance is an instance of the send port service that is created when a message is sent to the send port.</span></span> <span data-ttu-id="f5240-105">このトピックの手順を実行するときに、送信ポートのグループ概要ページにインスタンス情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5240-105">When you follow the procedure in this topic, instance information displays in the Group Overview page for the send port.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f5240-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="f5240-106">Prerequisites</span></span>  
 <span data-ttu-id="f5240-107">このトピックの手順を実行するには、BizTalk Server 管理者グループまたは BizTalk Server Operators グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5240-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> <span data-ttu-id="f5240-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="f5240-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-a-send-port"></a><span data-ttu-id="f5240-109">送信ポートのインスタンス情報を表示するには</span><span class="sxs-lookup"><span data-stu-id="f5240-109">To view instance information for a send port</span></span>  
  
1. <span data-ttu-id="f5240-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="f5240-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="f5240-111">コンソール ツリーで、BizTalk グループと、送信ポートのサービス インスタンスの情報を表示する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="f5240-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to view service instance information for a send port.</span></span>  
  
3. <span data-ttu-id="f5240-112">をクリックして**送信ポート**、送信ポートを右クリックし、 をポイント**ビュー**、 をクリックし、**インスタンス情報**します。</span><span class="sxs-lookup"><span data-stu-id="f5240-112">Click **Send Ports**, right-click the send port, point to **View**, and then click **Instance Information**.</span></span>  
  
    <span data-ttu-id="f5240-113">ページの下部に、クエリ結果 パネルには、送信ポートのすべての実行中のインスタンスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f5240-113">The query results panel in the lower section of the page displays all running instances of the send port.</span></span>  
  
4. <span data-ttu-id="f5240-114">クエリを絞り込むし、送信ポートの別のサービス インスタンスの情報を表示、下にあるボックスをクリックします。**値**、検索対象フィールドの表示、およびクリックするインスタンスの種類を選択します。**クエリの実行**します。</span><span class="sxs-lookup"><span data-stu-id="f5240-114">To refine the query and view different service instance information for the send port, click the box under **Value** for the Search For field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="f5240-115">クエリの作成に関する詳細については、参照の検索のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5240-115">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5240-116">参照</span><span class="sxs-lookup"><span data-stu-id="f5240-116">See Also</span></span>  
 <span data-ttu-id="f5240-117">[作成と送信ポートの構成](../core/creating-and-configuring-send-ports.md) </span><span class="sxs-lookup"><span data-stu-id="f5240-117">[Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md) </span></span>  
 <span data-ttu-id="f5240-118">[実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="f5240-118">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="f5240-119">[中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="f5240-119">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="f5240-120">[メッセージを検索する方法](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f5240-120">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="f5240-121">サブスクリプションを検索する方法</span><span class="sxs-lookup"><span data-stu-id="f5240-121">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)