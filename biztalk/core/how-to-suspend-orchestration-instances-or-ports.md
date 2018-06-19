---
title: オーケストレーションのインスタンスまたはポートを中断する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62d91c8d1e02b7283a430f7c82c572b6a989d108
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22256698"
---
# <a name="how-to-suspend-orchestration-instances-or-ports"></a><span data-ttu-id="18916-102">オーケストレーションのインスタンスまたはポートを中断する方法</span><span class="sxs-lookup"><span data-stu-id="18916-102">How to Suspend Orchestration Instances or Ports</span></span>
<span data-ttu-id="18916-103">BizTalk Server 管理コンソールのクエリ結果一覧から、オーケストレーションのインスタンスまたはポートを中断できます。</span><span class="sxs-lookup"><span data-stu-id="18916-103">You can suspend orchestration instances or ports from a query results list in the BizTalk Server Administration Console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="18916-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="18916-104">Prerequisites</span></span>  
 <span data-ttu-id="18916-105">この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="18916-105">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-suspend-orchestration-instances-or-ports"></a><span data-ttu-id="18916-106">オーケストレーションのインスタンスまたはポートを中断するには</span><span class="sxs-lookup"><span data-stu-id="18916-106">To suspend orchestration instances or ports</span></span>  
  
1.  <span data-ttu-id="18916-107">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="18916-107">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="18916-108">コンソール ツリーで  **BizTalk Server 管理コンソール**, 、し、BizTalk グループ をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18916-108">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="18916-109">詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18916-109">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="18916-110">**クエリ式** グループの **値** 列で、選択 **サービス インスタンスを実行している** ドロップダウン リスト ボックスからです。</span><span class="sxs-lookup"><span data-stu-id="18916-110">In the **Query Expression** group, in the **Value** column, select **Running Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="18916-111">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18916-111">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="18916-112">単一のインスタンスを中断する、 **フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***) を選択、 **サービス名** フィルターし、次に、 **値**  列で、サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="18916-112">To suspend a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select the **Service Name** filter and then in the **Value** column, specify the service name.</span></span>  
  
    -   <span data-ttu-id="18916-113">インスタンスをまとめてを中断する、 **フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***) を選択 **結果をグループ化** し、次に、 **値**  列で、サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="18916-113">To suspend instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select **Group Results By** and then in the **Value** column, specify the service name.</span></span>  
  
6.  <span data-ttu-id="18916-114">クリックして **クエリを実行**します。</span><span class="sxs-lookup"><span data-stu-id="18916-114">Click **Run Query**.</span></span>  
  
7.  <span data-ttu-id="18916-115">クエリ結果の一覧で、中断、およびをクリックするアクティブなオーケストレーションまたはポートを右クリックして **インスタンスの中断** または **インスタンスの中断**します。</span><span class="sxs-lookup"><span data-stu-id="18916-115">In the query results list, right-click the active orchestration or port you want to suspend, and then click **Suspend Instance** or **Suspend Instances**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18916-116">参照</span><span class="sxs-lookup"><span data-stu-id="18916-116">See Also</span></span>  
 [<span data-ttu-id="18916-117">オーケストレーション、ポート、およびメッセージのエラーの調査</span><span class="sxs-lookup"><span data-stu-id="18916-117">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)