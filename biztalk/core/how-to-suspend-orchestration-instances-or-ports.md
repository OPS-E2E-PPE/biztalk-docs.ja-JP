---
title: "オーケストレーションのインスタンスまたはポートを中断する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, suspending
- instances, suspending
- suspending
- HAT, suspending orchestrations
- HAT, suspending pipelines
- suspending, ports
- suspending, orchestrations
- orchestrations, suspending
- HAT, suspending ports
- suspending, instances
- ports, suspending
ms.assetid: cacc7e58-7d3e-4d6b-adb0-618fdc4f0d89
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62d91c8d1e02b7283a430f7c82c572b6a989d108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-suspend-orchestration-instances-or-ports"></a><span data-ttu-id="f5b15-102">オーケストレーションのインスタンスまたはポートを中断する方法</span><span class="sxs-lookup"><span data-stu-id="f5b15-102">How to Suspend Orchestration Instances or Ports</span></span>
<span data-ttu-id="f5b15-103">BizTalk Server 管理コンソールのクエリ結果一覧から、オーケストレーションのインスタンスまたはポートを中断できます。</span><span class="sxs-lookup"><span data-stu-id="f5b15-103">You can suspend orchestration instances or ports from a query results list in the BizTalk Server Administration Console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f5b15-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="f5b15-104">Prerequisites</span></span>  
 <span data-ttu-id="f5b15-105">この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5b15-105">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-suspend-orchestration-instances-or-ports"></a><span data-ttu-id="f5b15-106">オーケストレーションのインスタンスまたはポートを中断するには</span><span class="sxs-lookup"><span data-stu-id="f5b15-106">To suspend orchestration instances or ports</span></span>  
  
1.  <span data-ttu-id="f5b15-107">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="f5b15-107">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f5b15-108">コンソール ツリーで  **BizTalk Server 管理コンソール**、し、BizTalk グループ をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5b15-108">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="f5b15-109">詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。</span><span class="sxs-lookup"><span data-stu-id="f5b15-109">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="f5b15-110">**クエリ式**グループの 、**値**列をオン**サービス インスタンスを実行している**ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="f5b15-110">In the **Query Expression** group, in the **Value** column, select **Running Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="f5b15-111">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f5b15-111">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="f5b15-112">1 つのインスタンスを中断する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\***) を選択、**サービス名**フィルターと次に、**値**列で、サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b15-112">To suspend a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select the **Service Name** filter and then in the **Value** column, specify the service name.</span></span>  
  
    -   <span data-ttu-id="f5b15-113">インスタンスをまとめてを中断する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\***) を選択**結果をグループ化**し、**値**列で、サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5b15-113">To suspend instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select **Group Results By** and then in the **Value** column, specify the service name.</span></span>  
  
6.  <span data-ttu-id="f5b15-114">をクリックして**クエリを実行**です。</span><span class="sxs-lookup"><span data-stu-id="f5b15-114">Click **Run Query**.</span></span>  
  
7.  <span data-ttu-id="f5b15-115">クエリ結果リストで、中断、をクリックして、アクティブなオーケストレーションまたはポートを右クリックして**インスタンスの中断**または**インスタンスの中断**です。</span><span class="sxs-lookup"><span data-stu-id="f5b15-115">In the query results list, right-click the active orchestration or port you want to suspend, and then click **Suspend Instance** or **Suspend Instances**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b15-116">参照</span><span class="sxs-lookup"><span data-stu-id="f5b15-116">See Also</span></span>  
 [<span data-ttu-id="f5b15-117">オーケストレーション、ポート、およびメッセージのエラーの調査</span><span class="sxs-lookup"><span data-stu-id="f5b15-117">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)