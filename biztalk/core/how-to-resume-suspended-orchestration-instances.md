---
title: 中断したオーケストレーション インスタンスを再開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- instances, resuming [HAT]
- HAT, resuming orchestrations
- HAT, resuming pipelines
- orchestrations, resuming
- resuming, pipelines
- resuming, orchestrations
- HAT, debug mode
ms.assetid: da133183-68d9-48d1-9601-8f6d4d5b8898
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f3243173f454d560515d1c3cbb9bef749fc17d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991171"
---
# <a name="how-to-resume-suspended-orchestration-instances"></a><span data-ttu-id="b1d42-102">中断したオーケストレーション インスタンスを再開する方法</span><span class="sxs-lookup"><span data-stu-id="b1d42-102">How to Resume Suspended Orchestration Instances</span></span>
<span data-ttu-id="b1d42-103">"中断 (再開可能)" とマークされているオーケストレーション インスタンスを中断した場合は、クエリ結果ペインまたはプレビュー ペインからオーケストレーション インスタンスの再開を試行できます。</span><span class="sxs-lookup"><span data-stu-id="b1d42-103">If you have suspended orchestration instances that are listed as "suspended resumable," you can attempt to resume the orchestration instance from the query results or preview pane.</span></span> <span data-ttu-id="b1d42-104">ただし、オーケストレーション インスタンスを正常に再開できるのは、中断の原因となった問題が修正済みの場合のみです。</span><span class="sxs-lookup"><span data-stu-id="b1d42-104">Resuming the orchestration instance will only succeed if the underlying problem that caused the orchestration instance to become suspended has also been fixed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b1d42-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="b1d42-105">Prerequisites</span></span>  
 <span data-ttu-id="b1d42-106">この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1d42-106">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-resume-suspended-orchestration-instances"></a><span data-ttu-id="b1d42-107">中断したオーケストレーション インスタンスを再開するには</span><span class="sxs-lookup"><span data-stu-id="b1d42-107">To resume suspended orchestration instances</span></span>  
  
1. <span data-ttu-id="b1d42-108">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="b1d42-108">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="b1d42-109">コンソール ツリーで、展開**BizTalk Server 管理**、し、[BizTalk グループ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1d42-109">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3. <span data-ttu-id="b1d42-110">詳細ウィンドウでをクリックして、**新しいクエリ**タブ。</span><span class="sxs-lookup"><span data-stu-id="b1d42-110">In the details pane, click the **New Query** tab.</span></span>  
  
4. <span data-ttu-id="b1d42-111">**クエリ式**グループに、**値**列で、**中断サービス インスタンスの**ドロップダウン リスト ボックスから。</span><span class="sxs-lookup"><span data-stu-id="b1d42-111">In the **Query Expression** group, in the **Value** column, select **Suspended Service Instances** from the drop-down list box.</span></span>  
  
5. <span data-ttu-id="b1d42-112">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b1d42-112">Do one of the following:</span></span>  
  
   - <span data-ttu-id="b1d42-113">1 つのインスタンスを再開する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\\**<em>) を選択、\**のサービス名</em>* フィルターし、**値**列で、サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1d42-113">To resume a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\\**<em>), select the \**Service Name</em>* filter and then in the **Value** column, specify the service name.</span></span>  
  
   - <span data-ttu-id="b1d42-114">インスタンスをまとめてを再開する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\\**<em>) を選択します \**でのグループの結果</em>* し、**値**列で、サービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1d42-114">To resume instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\\**<em>), select \**Group Results By</em>* and then in the **Value** column, specify the service name.</span></span>  
  
6. <span data-ttu-id="b1d42-115">クリックして**クエリを実行**します。</span><span class="sxs-lookup"><span data-stu-id="b1d42-115">Click **Run Query**.</span></span>  
  
7. <span data-ttu-id="b1d42-116">クエリ結果リストで、再開、およびクリックするオーケストレーション インスタンスを右クリックして**インスタンスの再開**または**インスタンスの再開**します。</span><span class="sxs-lookup"><span data-stu-id="b1d42-116">In the query results list, right-click the orchestration instance you want to resume, and then click **Resume Instance** or **Resume Instances**.</span></span> <span data-ttu-id="b1d42-117">これにより、再開するインスタンスを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b1d42-117">This allows you to select which instances to resume.</span></span>  
  
    <span data-ttu-id="b1d42-118">[サービス インスタンスの状態](../core/service-instance-states.md)詳細については、中断状態にします。</span><span class="sxs-lookup"><span data-stu-id="b1d42-118">[Service Instance States](../core/service-instance-states.md) provides more information on the on the suspended state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d42-119">参照</span><span class="sxs-lookup"><span data-stu-id="b1d42-119">See Also</span></span>  
 [<span data-ttu-id="b1d42-120">オーケストレーション、ポート、およびメッセージのエラーの調査</span><span class="sxs-lookup"><span data-stu-id="b1d42-120">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)
