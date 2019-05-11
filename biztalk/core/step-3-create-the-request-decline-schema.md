---
title: 手順 3:要求拒否スキーマの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1ce166c-1be1-4ef4-9d00-3da7038d4ada
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 039fd40448d2545e360c5599b1448c6bcbf9c6e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392649"
---
# <a name="step-3-create-the-request-decline-schema"></a><span data-ttu-id="3a548-102">手順 3:要求拒否スキーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a548-102">Step 3: Create the Request Decline Schema</span></span>
<span data-ttu-id="3a548-103">![手順 5 の 3](../core/media/step-3of5.gif "Step_3of5")</span><span class="sxs-lookup"><span data-stu-id="3a548-103">![Step 3 of 5](../core/media/step-3of5.gif "Step_3of5")</span></span>  
  
 <span data-ttu-id="3a548-104">**所要時間:** 7 分</span><span class="sxs-lookup"><span data-stu-id="3a548-104">**Time to complete:** 7 minutes</span></span>  
  
 <span data-ttu-id="3a548-105">**目標:** この手順でメッセージのスキーマを作成する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス プロセスで在庫補充要求を拒否した場合は、倉庫に返送します。</span><span class="sxs-lookup"><span data-stu-id="3a548-105">**Objective:** In this step, you create the schema for the message [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends back to the warehouse if the business process rejects the inventory replenishment request.</span></span>  
  
 <span data-ttu-id="3a548-106">**目的:** スキーマは、データと要求拒否メッセージの構造を定義します。</span><span class="sxs-lookup"><span data-stu-id="3a548-106">**Purpose:** The schema defines the data and the structure of the request decline message.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="3a548-107">スキーマを使用して、メッセージ内のデータとの対話を識別します。</span><span class="sxs-lookup"><span data-stu-id="3a548-107">uses the schema to identify and interact with the data in the message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3a548-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="3a548-108">Prerequisites</span></span>  
 <span data-ttu-id="3a548-109">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3a548-109">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="3a548-110">この手順を開始する前に行う必要があります[手順 1。EAISchemas プロジェクトの作成](../core/step-1-create-eaischemas-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="3a548-110">Before you begin this step you must complete [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="3a548-111">手順</span><span class="sxs-lookup"><span data-stu-id="3a548-111">Procedures</span></span>  
  
#### <a name="to-create-the-request-decline-schema"></a><span data-ttu-id="3a548-112">要求拒否スキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="3a548-112">To create the Request Decline schema</span></span>  
  
1.  <span data-ttu-id="3a548-113">ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。</span><span class="sxs-lookup"><span data-stu-id="3a548-113">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="3a548-114">**新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3a548-114">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="3a548-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="3a548-115">Use this</span></span>|<span data-ttu-id="3a548-116">目的</span><span class="sxs-lookup"><span data-stu-id="3a548-116">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="3a548-117">**インストール済みテンプレート**</span><span class="sxs-lookup"><span data-stu-id="3a548-117">**Installed Templates**</span></span>|<span data-ttu-id="3a548-118">クリックして**スキーマ ファイル**、 をクリックし、**スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="3a548-118">Click **Schema Files**, and then click **Schema**.</span></span>|  
    |<span data-ttu-id="3a548-119">**名前**</span><span class="sxs-lookup"><span data-stu-id="3a548-119">**Name**</span></span>|<span data-ttu-id="3a548-120">「`RequestDecline.xsd`.</span><span class="sxs-lookup"><span data-stu-id="3a548-120">Type `RequestDecline.xsd`.</span></span>|  
  
3.  <span data-ttu-id="3a548-121">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a548-121">Click **Add**.</span></span>  
  
4.  <span data-ttu-id="3a548-122">BizTalk エディターでは、スキーマ ツリーからクリックして、**ルート**ノードを選択します。</span><span class="sxs-lookup"><span data-stu-id="3a548-122">In BizTalk Editor, from schema tree, click the **Root** node to select it.</span></span>  
  
5.  <span data-ttu-id="3a548-123">プロパティ ペインでの値を変更、**ノード名**プロパティを`DeclineReq`、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3a548-123">In the Properties pane, change the value of the **Node Name** property to `DeclineReq`, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="3a548-124">スキーマ ツリーで、右クリックし、 **DeclineReq**に**スキーマ ノードの挿入**、 をクリックし、**子フィールド要素**します。</span><span class="sxs-lookup"><span data-stu-id="3a548-124">In schema tree, right-click the **DeclineReq** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  
  
7.  <span data-ttu-id="3a548-125">型`ReqID`要素、および、ENTER キーを押して新しい名前として。</span><span class="sxs-lookup"><span data-stu-id="3a548-125">Type `ReqID` as the new name for the element, and then press ENTER.</span></span>  
  
8.  <span data-ttu-id="3a548-126">という名前の 2 番目の子フィールド要素を追加`GrandTotal`します。</span><span class="sxs-lookup"><span data-stu-id="3a548-126">Add a second child field element named `GrandTotal`.</span></span>  
  
9. <span data-ttu-id="3a548-127">**[ファイル]** メニューの **[すべてを保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3a548-127">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="3a548-128">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="3a548-128">What did I just do?</span></span>  
 <span data-ttu-id="3a548-129">この手順で作成したメッセージのスキーマを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ビジネス プロセスで在庫要求が拒否された場合、倉庫に返送します。</span><span class="sxs-lookup"><span data-stu-id="3a548-129">In this step, you created the schema for the message that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends back to the warehouse if the business process rejects the inventory request.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3a548-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="3a548-130">Next Steps</span></span>  
 <span data-ttu-id="3a548-131">要求メッセージを再フォーマットして要求拒否メッセージを作成するオーケストレーションに必要なマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a548-131">You create the map needed by the orchestration to create request decline message by reformatting request message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a548-132">参照</span><span class="sxs-lookup"><span data-stu-id="3a548-132">See Also</span></span>  
 [<span data-ttu-id="3a548-133">ステップ 1: EAISchemas プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a548-133">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
 <span data-ttu-id="3a548-134">[手順 2:在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="3a548-134">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="3a548-135">[手順 4:マップを作成します。](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="3a548-135">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="3a548-136">[手順 5:EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="3a548-136">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 [<span data-ttu-id="3a548-137">BizTalk エディターを使用したスキーマの作成</span><span class="sxs-lookup"><span data-stu-id="3a548-137">Creating Schemas Using BizTalk Editor</span></span>](../core/creating-schemas-using-biztalk-editor.md)