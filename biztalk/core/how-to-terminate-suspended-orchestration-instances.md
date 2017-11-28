---
title: "中断したオーケストレーション インスタンスを終了する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, terminating [HAT]
- messages, saving [HAT]
- HAT, saving messages
- HAT, terminating pipelines
- HAT, terminiating orchestrations
- orchestrations, terminating [HAT]
ms.assetid: b5d44cce-b05c-47f9-9015-5b10c2312bf1
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc0160be5aeeef43b9595953893b4ea1af82c62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a><span data-ttu-id="7891a-102">中断したオーケストレーション インスタンスを終了する方法</span><span class="sxs-lookup"><span data-stu-id="7891a-102">How to Terminate Suspended Orchestration Instances</span></span>
<span data-ttu-id="7891a-103">中断したオーケストレーション インスタンスまたはポートは、BizTalk Server 管理コンソールのクエリ結果ペインまたはプレビュー ペインから終了できます。</span><span class="sxs-lookup"><span data-stu-id="7891a-103">You can terminate any suspended orchestration instances or ports from the Query results or preview pane in the BizTalk Server Administration Console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7891a-104">順次配送の送信ポートの各インスタンスは、関連付けられているいくつかのメッセージがあります。</span><span class="sxs-lookup"><span data-stu-id="7891a-104">Each instance of an ordered delivery a send port may have several messages associated with it.</span></span> <span data-ttu-id="7891a-105">誤終了やデータ損失を防ぐために、インスタンスを終了する前にこのような関連付けをすべて確認してください。</span><span class="sxs-lookup"><span data-stu-id="7891a-105">To prevent accidental termination or data loss, be sure you have reviewed all such associations before terminating an instance.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7891a-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="7891a-106">Prerequisites</span></span>  
 <span data-ttu-id="7891a-107">この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7891a-107">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-terminate-suspended-orchestration-instances"></a><span data-ttu-id="7891a-108">中断したオーケストレーション インスタンスを終了するには</span><span class="sxs-lookup"><span data-stu-id="7891a-108">To terminate suspended orchestration instances</span></span>  
  
1.  <span data-ttu-id="7891a-109">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="7891a-109">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7891a-110">コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7891a-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="7891a-111">詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。</span><span class="sxs-lookup"><span data-stu-id="7891a-111">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="7891a-112">**クエリ式**グループにおいて、**値**列で、選択**中断サービス インスタンスの**ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="7891a-112">In the **Query Expression** group, in the **Value** column, select **Suspended Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="7891a-113">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7891a-113">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="7891a-114">1 つのインスタンスを終了する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\***) を選択、**サービス名**フィルター**値**列で、サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7891a-114">To terminate a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select the **Service Name** filter and then in the **Value** column, specify the service name.</span></span>  
  
    -   <span data-ttu-id="7891a-115">インスタンスをまとめてを終了する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\***) を選択**結果をグループ化**し、**値**列で、サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7891a-115">To terminate instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select **Group Results By** and then in the **Value** column, specify the service name.</span></span>  
  
6.  <span data-ttu-id="7891a-116">をクリックして**クエリを実行**です。</span><span class="sxs-lookup"><span data-stu-id="7891a-116">Click **Run Query**.</span></span>  
  
7.  <span data-ttu-id="7891a-117">クエリ結果リストで、オーケストレーション インスタンスまたはグループのインスタンスを終了して、をクリックするを右クリックして**インスタンスの終了**または**インスタンスを終了**です。</span><span class="sxs-lookup"><span data-stu-id="7891a-117">In the query results list, right-click the orchestration instance or group of instances you want to terminate, and then click **Terminate Instance** or **Terminate Instances**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7891a-118">参照</span><span class="sxs-lookup"><span data-stu-id="7891a-118">See Also</span></span>  
 [<span data-ttu-id="7891a-119">オーケストレーション、ポート、およびメッセージのエラーの調査</span><span class="sxs-lookup"><span data-stu-id="7891a-119">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)