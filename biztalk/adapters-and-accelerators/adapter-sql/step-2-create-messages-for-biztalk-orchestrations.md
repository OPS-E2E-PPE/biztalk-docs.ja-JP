---
title: '手順 2: BizTalk オーケストレーションのメッセージを作成する |Microsoft Docs'
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
ms.openlocfilehash: 9bad2f052efa561020ba04060a8290137a08f542
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995363"
---
# <a name="step-2-create-messages-for-biztalk-orchestrations"></a><span data-ttu-id="f1e2a-102">手順 2: BizTalk オーケストレーションのメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-102">Step 2: Create Messages for BizTalk Orchestrations</span></span>
<span data-ttu-id="f1e2a-103">![手順 2 の 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span><span class="sxs-lookup"><span data-stu-id="f1e2a-103">![Step 2 of 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span></span>  
  
 <span data-ttu-id="f1e2a-104">**所要時間:** 5 分</span><span class="sxs-lookup"><span data-stu-id="f1e2a-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="f1e2a-105">**目標:** このステップでオーケストレーションを BizTalk プロジェクトに追加し、で生成したスキーマのメッセージを作成[手順 1: 操作のスキーマの生成](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-105">**Objective:** In this step, you add an orchestration to the BizTalk project and create messages for the schemas you generated in [Step 1: Generate Schema for Operations](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f1e2a-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="f1e2a-106">Prerequisites</span></span>  
 <span data-ttu-id="f1e2a-107">完了する必要があります[手順 1: 操作のスキーマの生成](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-107">You must have completed [Step 1: Generate Schema for Operations](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).</span></span>  
  
### <a name="to-create-messages-in-an-orchestration"></a><span data-ttu-id="f1e2a-108">オーケストレーションでメッセージを作成するには</span><span class="sxs-lookup"><span data-stu-id="f1e2a-108">To create messages in an orchestration</span></span>  
  
1. <span data-ttu-id="f1e2a-109">BizTalk オーケストレーションの BizTalk プロジェクトに追加[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f1e2a-109">Add a BizTalk orchestration to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:</span></span>  
  
   1.  <span data-ttu-id="f1e2a-110">ソリューション エクスプ ローラーで、BizTalk プロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-110">From Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span>  
  
   2.  <span data-ttu-id="f1e2a-111">**新しい項目の追加**] ダイアログ ボックスから、**カテゴリ**ボックスで、[**オーケストレーション ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-111">In the **Add New Item** dialog box, from the **Categories** box, click **Orchestration Files**.</span></span> <span data-ttu-id="f1e2a-112">**テンプレート**ボックスで、 **BizTalk オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-112">From the **Templates** box, click **BizTalk Orchestration**.</span></span>  
  
   3.  <span data-ttu-id="f1e2a-113">BizTalk オーケストレーションの名前を入力し、クリックして**追加**します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-113">Type a name for the BizTalk orchestration, and then click **Add**.</span></span> <span data-ttu-id="f1e2a-114">このチュートリアルでは、名前を入力します。`EmployeeOrch.odx`します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-114">For this tutorial, enter the name `EmployeeOrch.odx`.</span></span>  
  
2. <span data-ttu-id="f1e2a-115">開く、**オーケストレーション**がまだ開いていない場合、BizTalk プロジェクトのウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-115">Open the **Orchestration View** window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="f1e2a-116">これを行うには、次のようにクリックします。**ビュー**、 をポイント**その他の Windows**、順にクリックします**オーケストレーション**します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-116">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3. <span data-ttu-id="f1e2a-117">オーケストレーションへメッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-117">Add messages to the orchestration.</span></span>  
  
   1.  <span data-ttu-id="f1e2a-118">**オーケストレーション**、右クリック**メッセージ**、順にクリックします**新しいメッセージ**します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-118">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
   2.  <span data-ttu-id="f1e2a-119">新しく作成されたメッセージを右クリックし、**プロパティ ウィンドウ**します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-119">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
   3.  <span data-ttu-id="f1e2a-120">**プロパティ**ウィンドウ **[message_1]** 次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-120">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
       |<span data-ttu-id="f1e2a-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="f1e2a-121">Use this</span></span>|<span data-ttu-id="f1e2a-122">目的</span><span class="sxs-lookup"><span data-stu-id="f1e2a-122">To do this</span></span>|  
       |--------------|----------------|  
       |<span data-ttu-id="f1e2a-123">[Identifier]</span><span class="sxs-lookup"><span data-stu-id="f1e2a-123">Identifier</span></span>|<span data-ttu-id="f1e2a-124">「`NotifyReceive`.</span><span class="sxs-lookup"><span data-stu-id="f1e2a-124">Type `NotifyReceive`.</span></span>|  
       |<span data-ttu-id="f1e2a-125">メッセージ型</span><span class="sxs-lookup"><span data-stu-id="f1e2a-125">Message Type</span></span>|<span data-ttu-id="f1e2a-126">ドロップダウン リストから展開**スキーマ**、選び**Employee_PurchaseOrder.Notification**Employee_PurchaseOrder は、BizTalk プロジェクトの名前です。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-126">From the drop-down list, expand **Schemas**, and select **Employee_PurchaseOrder.Notification**, where Employee_PurchaseOrder is the name of your BizTalk project.</span></span> <span data-ttu-id="f1e2a-127">通知は、スキーマの生成、**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-127">Notification is the schema generated for the **Notification** operation.</span></span>|  
  
   4.  <span data-ttu-id="f1e2a-128">4 つの新しいメッセージを追加する前の手順を繰り返します: 要求-応答メッセージの設定、UPDATE_EMPLOYEE を呼び出すストアド プロシージャと、別の要求-応答メッセージの設定を実行するための**挿入**操作**Purchase_Order**テーブル。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-128">Repeat the previous step to add four new messages—a request-response message set for invoking the UPDATE_EMPLOYEE stored procedure and another request-response message set for performing the **Insert** operation on **Purchase_Order** table.</span></span>  
  
       |<span data-ttu-id="f1e2a-129">識別子を設定するには</span><span class="sxs-lookup"><span data-stu-id="f1e2a-129">Set Identifier to</span></span>|<span data-ttu-id="f1e2a-130">メッセージの種類を設定</span><span class="sxs-lookup"><span data-stu-id="f1e2a-130">Set Message Type to</span></span>|  
       |-----------------------|-------------------------|  
       |<span data-ttu-id="f1e2a-131">更新</span><span class="sxs-lookup"><span data-stu-id="f1e2a-131">UpdateEmployee</span></span>|<span data-ttu-id="f1e2a-132">*Employee_PurchaseOrder.TypedProcedure_dbo します。UPDATE_EMPLOYEE*ここで、TypedProcedure_dbo します。UPDATE_EMPLOYEE は、スキーマを UPDATE_EMPLOYEE ストアド プロシージャです。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-132">*Employee_PurchaseOrder.TypedProcedure_dbo.UPDATE_EMPLOYEE*, where TypedProcedure_dbo.UPDATE_EMPLOYEE is the schema for the UPDATE_EMPLOYEE stored procedure.</span></span>|  
       |<span data-ttu-id="f1e2a-133">UpdateEmployeeResponse</span><span class="sxs-lookup"><span data-stu-id="f1e2a-133">UpdateEmployeeResponse</span></span>|<span data-ttu-id="f1e2a-134">*Employee_PurchaseOrder.TypedProcedure_dbo します。UPDATE_EMPLOYEEResponse*</span><span class="sxs-lookup"><span data-stu-id="f1e2a-134">*Employee_PurchaseOrder.TypedProcedure_dbo.UPDATE_EMPLOYEEResponse*</span></span>|  
       |<span data-ttu-id="f1e2a-135">InsertPO</span><span class="sxs-lookup"><span data-stu-id="f1e2a-135">InsertPO</span></span>|<span data-ttu-id="f1e2a-136">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*TableOperation_dbo_Purchase_Order.Insert は Purchase_Order テーブルに対する挿入操作のスキーマです。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-136">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*, where TableOperation_dbo_Purchase_Order.Insert is the schema for the Insert operation on the Purchase_Order table.</span></span>|  
       |<span data-ttu-id="f1e2a-137">InsertPOResponse</span><span class="sxs-lookup"><span data-stu-id="f1e2a-137">InsertPOResponse</span></span>|<span data-ttu-id="f1e2a-138">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*</span><span class="sxs-lookup"><span data-stu-id="f1e2a-138">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*</span></span>|  
  
   5.  <span data-ttu-id="f1e2a-139">オーケストレーション ファイルと、BizTalk プロジェクトを保存します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-139">Save the orchestration file and the BizTalk project.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="f1e2a-140">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-140">What did I just do?</span></span>  
 <span data-ttu-id="f1e2a-141">この手順では、受信と送信操作を使用して SQL Server を実行を呼び出すためのメッセージを作成、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-141">In this step, you created messages for invoking performing inbound and outbound operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f1e2a-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="f1e2a-142">Next Steps</span></span>  
 <span data-ttu-id="f1e2a-143">挿入操作の SQL Server とフィルターの通知から通知を受信するオーケストレーション図形を追加する」の説明に従って[レッスン 2: 受信とフィルター通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)します。</span><span class="sxs-lookup"><span data-stu-id="f1e2a-143">You add orchestration shapes to receive notification from SQL Server and filter notifications for Insert operation, as described in [Lesson 2: Receive and Filter Notifications](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e2a-144">参照</span><span class="sxs-lookup"><span data-stu-id="f1e2a-144">See Also</span></span>  
 <span data-ttu-id="f1e2a-145">[レッスン 1: スキーマを生成し、メッセージの作成](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md) </span><span class="sxs-lookup"><span data-stu-id="f1e2a-145">[Lesson 1: Generate Schemas and Create Messages](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md) </span></span>  
 [<span data-ttu-id="f1e2a-146">手順 1: 操作のスキーマを生成する</span><span class="sxs-lookup"><span data-stu-id="f1e2a-146">Step 1: Generate Schema for Operations</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)