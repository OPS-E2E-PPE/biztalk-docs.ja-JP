---
title: '手順 2: BizTalk オーケストレーションのメッセージを作成する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47a4fb98-6085-4aeb-ab39-2f2c3858d4e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89b121d95992eb30240e38da434d1125df9db681
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226114"
---
# <a name="step-2-create-messages-for-biztalk-orchestrations"></a><span data-ttu-id="040d3-102">手順 2: BizTalk オーケストレーションのメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="040d3-102">Step 2: Create Messages for BizTalk Orchestrations</span></span>
<span data-ttu-id="040d3-103">![手順 2 の 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span><span class="sxs-lookup"><span data-stu-id="040d3-103">![Step 2 of 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span></span>  
  
 <span data-ttu-id="040d3-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="040d3-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="040d3-105">**目標:** このステップでオーケストレーションを BizTalk プロジェクトに追加およびで生成したスキーマのメッセージを作成[手順 1: 操作のスキーマの生成](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="040d3-105">**Objective:** In this step, you add an orchestration to the BizTalk project and create messages for the schemas you generated in [Step 1: Generate Schema for Operations](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="040d3-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="040d3-106">Prerequisites</span></span>  
 <span data-ttu-id="040d3-107">完了する必要があります[手順 1: 操作のスキーマの生成](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)です。</span><span class="sxs-lookup"><span data-stu-id="040d3-107">You must have completed [Step 1: Generate Schema for Operations](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).</span></span>  
  
### <a name="to-create-messages-in-an-orchestration"></a><span data-ttu-id="040d3-108">オーケストレーションでメッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="040d3-108">To create messages in an orchestration</span></span>  
  
1.  <span data-ttu-id="040d3-109">BizTalk オーケストレーションの BizTalk プロジェクトに追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="040d3-109">Add a BizTalk orchestration to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="040d3-110">ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックし、**追加**、クリックして**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="040d3-110">From Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span>  
  
    2.  <span data-ttu-id="040d3-111">**新しい項目の追加** ダイアログ ボックスから、**カテゴリ**ボックスで、クリックして**オーケストレーション ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="040d3-111">In the **Add New Item** dialog box, from the **Categories** box, click **Orchestration Files**.</span></span> <span data-ttu-id="040d3-112">**テンプレート**ボックスで、クリックして**BizTalk オーケストレーション**です。</span><span class="sxs-lookup"><span data-stu-id="040d3-112">From the **Templates** box, click **BizTalk Orchestration**.</span></span>  
  
    3.  <span data-ttu-id="040d3-113">BizTalk オーケストレーションの名前を入力し、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="040d3-113">Type a name for the BizTalk orchestration, and then click **Add**.</span></span> <span data-ttu-id="040d3-114">このチュートリアルでは、名前を入力してください。`EmployeeOrch.odx`です。</span><span class="sxs-lookup"><span data-stu-id="040d3-114">For this tutorial, enter the name `EmployeeOrch.odx`.</span></span>  
  
2.  <span data-ttu-id="040d3-115">開く、**オーケストレーション**がまだ開いていない場合、BizTalk プロジェクトのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="040d3-115">Open the **Orchestration View** window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="040d3-116">これを行うには、をクリックして**ビュー**、 をポイント**その他のウィンドウ**、順にクリック**オーケストレーション ビュー**です。</span><span class="sxs-lookup"><span data-stu-id="040d3-116">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3.  <span data-ttu-id="040d3-117">メッセージをオーケストレーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="040d3-117">Add messages to the orchestration.</span></span>  
  
    1.  <span data-ttu-id="040d3-118">**オーケストレーション ビュー**を右クリックして**メッセージ**、クリックして**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="040d3-118">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
    2.  <span data-ttu-id="040d3-119">新しく作成されたメッセージを右クリックし [**プロパティ] ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="040d3-119">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
    3.  <span data-ttu-id="040d3-120">**プロパティ**ウィンドウ**Message_1**を次の操作します。</span><span class="sxs-lookup"><span data-stu-id="040d3-120">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
        |<span data-ttu-id="040d3-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="040d3-121">Use this</span></span>|<span data-ttu-id="040d3-122">目的</span><span class="sxs-lookup"><span data-stu-id="040d3-122">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="040d3-123">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="040d3-123">Identifier</span></span>|<span data-ttu-id="040d3-124">「`NotifyReceive`.</span><span class="sxs-lookup"><span data-stu-id="040d3-124">Type `NotifyReceive`.</span></span>|  
        |<span data-ttu-id="040d3-125">メッセージの種類</span><span class="sxs-lookup"><span data-stu-id="040d3-125">Message Type</span></span>|<span data-ttu-id="040d3-126">ドロップダウン リストから、展開**スキーマ**を選択して**Employee_PurchaseOrder.Notification**Employee_PurchaseOrder は、BizTalk プロジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="040d3-126">From the drop-down list, expand **Schemas**, and select **Employee_PurchaseOrder.Notification**, where Employee_PurchaseOrder is the name of your BizTalk project.</span></span> <span data-ttu-id="040d3-127">通知は、スキーマの生成、**通知**操作します。</span><span class="sxs-lookup"><span data-stu-id="040d3-127">Notification is the schema generated for the **Notification** operation.</span></span>|  
  
    4.  <span data-ttu-id="040d3-128">次の 4 つの新しいメッセージを追加する前の手順を繰り返します — ストアド プロシージャの呼び出し、UPDATE_EMPLOYEE と別の要求-応答メッセージの設定を実行するための要求-応答メッセージが設定、**挿入**操作**Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="040d3-128">Repeat the previous step to add four new messages—a request-response message set for invoking the UPDATE_EMPLOYEE stored procedure and another request-response message set for performing the **Insert** operation on **Purchase_Order** table.</span></span>  
  
        |<span data-ttu-id="040d3-129">識別子に設定します。</span><span class="sxs-lookup"><span data-stu-id="040d3-129">Set Identifier to</span></span>|<span data-ttu-id="040d3-130">メッセージの種類を設定</span><span class="sxs-lookup"><span data-stu-id="040d3-130">Set Message Type to</span></span>|  
        |-----------------------|-------------------------|  
        |<span data-ttu-id="040d3-131">更新</span><span class="sxs-lookup"><span data-stu-id="040d3-131">UpdateEmployee</span></span>|<span data-ttu-id="040d3-132">*Employee_PurchaseOrder.TypedProcedure_dbo です。UPDATE_EMPLOYEE*ここで、TypedProcedure_dbo です。UPDATE_EMPLOYEE は、スキーマ、UPDATE_EMPLOYEE をストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="040d3-132">*Employee_PurchaseOrder.TypedProcedure_dbo.UPDATE_EMPLOYEE*, where TypedProcedure_dbo.UPDATE_EMPLOYEE is the schema for the UPDATE_EMPLOYEE stored procedure.</span></span>|  
        |<span data-ttu-id="040d3-133">UpdateEmployeeResponse</span><span class="sxs-lookup"><span data-stu-id="040d3-133">UpdateEmployeeResponse</span></span>|<span data-ttu-id="040d3-134">*Employee_PurchaseOrder.TypedProcedure_dbo です。UPDATE_EMPLOYEEResponse*</span><span class="sxs-lookup"><span data-stu-id="040d3-134">*Employee_PurchaseOrder.TypedProcedure_dbo.UPDATE_EMPLOYEEResponse*</span></span>|  
        |<span data-ttu-id="040d3-135">InsertPO</span><span class="sxs-lookup"><span data-stu-id="040d3-135">InsertPO</span></span>|<span data-ttu-id="040d3-136">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*TableOperation_dbo_Purchase_Order.Insert は Purchase_Order テーブルに対する挿入操作のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="040d3-136">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*, where TableOperation_dbo_Purchase_Order.Insert is the schema for the Insert operation on the Purchase_Order table.</span></span>|  
        |<span data-ttu-id="040d3-137">InsertPOResponse</span><span class="sxs-lookup"><span data-stu-id="040d3-137">InsertPOResponse</span></span>|<span data-ttu-id="040d3-138">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*</span><span class="sxs-lookup"><span data-stu-id="040d3-138">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*</span></span>|  
  
    5.  <span data-ttu-id="040d3-139">オーケストレーション ファイルと、BizTalk プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="040d3-139">Save the orchestration file and the BizTalk project.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="040d3-140">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="040d3-140">What did I just do?</span></span>  
 <span data-ttu-id="040d3-141">この手順で SQL Server を使用してに対する受信と送信操作を呼び出すためのメッセージを作成した、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="040d3-141">In this step, you created messages for invoking performing inbound and outbound operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="040d3-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="040d3-142">Next Steps</span></span>  
 <span data-ttu-id="040d3-143">挿入操作では、SQL Server とフィルターの通知から通知を受信するオーケストレーション図形を追加する」の説明に従って[レッスン 2: 受信とフィルター通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)です。</span><span class="sxs-lookup"><span data-stu-id="040d3-143">You add orchestration shapes to receive notification from SQL Server and filter notifications for Insert operation, as described in [Lesson 2: Receive and Filter Notifications](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="040d3-144">参照</span><span class="sxs-lookup"><span data-stu-id="040d3-144">See Also</span></span>  
 <span data-ttu-id="040d3-145">[レッスン 1: スキーマを生成し、メッセージ作成](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md) </span><span class="sxs-lookup"><span data-stu-id="040d3-145">[Lesson 1: Generate Schemas and Create Messages](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md) </span></span>  
 [<span data-ttu-id="040d3-146">手順 1: 操作のスキーマを生成します。</span><span class="sxs-lookup"><span data-stu-id="040d3-146">Step 1: Generate Schema for Operations</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)