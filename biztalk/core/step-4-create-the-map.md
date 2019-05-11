---
title: 手順 4:マップを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f7f1f6d-0e57-4a65-b91d-c81fcc832961
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cf9def7682b9334af451b5230cc2790fb7a6021
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392543"
---
# <a name="step-4-create-the-map"></a><span data-ttu-id="b0afe-102">手順 4:マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-102">Step 4: Create the Map</span></span>
<span data-ttu-id="b0afe-103">![手順 4. 5 の](../core/media/step-4of5.gif "Step_4of5")</span><span class="sxs-lookup"><span data-stu-id="b0afe-103">![Step 4 of 5](../core/media/step-4of5.gif "Step_4of5")</span></span>  
  
 <span data-ttu-id="b0afe-104">**所要時間:** 6 分</span><span class="sxs-lookup"><span data-stu-id="b0afe-104">**Time to complete:** 6 minutes</span></span>  
  
 <span data-ttu-id="b0afe-105">**目標:** この手順では、要求メッセージを RequestDecline メッセージに変換するマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-105">**Objective:** In this step, you create a map that transforms Request message to RequestDecline message.</span></span>  
  
 <span data-ttu-id="b0afe-106">**目的:** マップにより、要求の ID 番号と総計を倉庫在庫システムに返される要求拒否メッセージに含まれること。</span><span class="sxs-lookup"><span data-stu-id="b0afe-106">**Purpose:** The map ensures that the request ID number and the grand total are included in the request decline message returned to the warehouse inventory system.</span></span> <span data-ttu-id="b0afe-107">送信メッセージに対して定義されたフィールドに、受信メッセージ内のフィールドをリンクするのにには、BizTalk マッパーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-107">You use BizTalk Mapper to link fields in an incoming message to fields defined for the outgoing message.</span></span> <span data-ttu-id="b0afe-108">これは、機能は、これら 2 つのメッセージには、同じスキーマ構造があるないため必要です。</span><span class="sxs-lookup"><span data-stu-id="b0afe-108">This is necessary because these two messages do not have the same schema structure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b0afe-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="b0afe-109">Prerequisites</span></span>  
 <span data-ttu-id="b0afe-110">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="b0afe-110">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="b0afe-111">この手順を開始する前に行う必要があります[手順 2。在庫要求スキーマの作成](../core/step-2-create-the-inventory-request-schema.md)と[手順 3。要求拒否スキーマの作成](../core/step-3-create-the-request-decline-schema.md)です。</span><span class="sxs-lookup"><span data-stu-id="b0afe-111">Before you begin this step you must complete [Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) and [Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="b0afe-112">手順</span><span class="sxs-lookup"><span data-stu-id="b0afe-112">Procedures</span></span>  
 <span data-ttu-id="b0afe-113">マップは、要求スキーマと RequestDecline スキーマに依存します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-113">The map depends on the Request schema and the RequestDecline schema.</span></span>  <span data-ttu-id="b0afe-114">はるか、マップで使用するには、スキーマを使用してプロジェクトをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="b0afe-114">You much compile the project with the schema before you can use them on a map.</span></span>  
  
#### <a name="to-compile-the-eaischemas-project"></a><span data-ttu-id="b0afe-115">EAISchemas プロジェクトをコンパイルするには</span><span class="sxs-lookup"><span data-stu-id="b0afe-115">To compile the EAISchemas project</span></span>  
  
-   <span data-ttu-id="b0afe-116">ソリューション エクスプ ローラーで右クリックして**EAISchemas**、 をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-116">In Solution Explorer, right-click **EAISchemas**, and then click **Build**.</span></span>  
  
#### <a name="to-create-the-map"></a><span data-ttu-id="b0afe-117">マップを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b0afe-117">To create the map</span></span>  
  
1.  <span data-ttu-id="b0afe-118">ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントして、**追加**、 をクリックし、**新しい項目の**。</span><span class="sxs-lookup"><span data-stu-id="b0afe-118">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="b0afe-119">**新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b0afe-119">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="b0afe-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="b0afe-120">Use this</span></span>|<span data-ttu-id="b0afe-121">目的</span><span class="sxs-lookup"><span data-stu-id="b0afe-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b0afe-122">**インストール済みテンプレート**</span><span class="sxs-lookup"><span data-stu-id="b0afe-122">**Installed Templates**</span></span>|<span data-ttu-id="b0afe-123">クリックして**マップ ファイル**、 をクリックし、**マップ**します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-123">Click **Map Files**, and then click **Map**.</span></span>|  
    |<span data-ttu-id="b0afe-124">**名前**</span><span class="sxs-lookup"><span data-stu-id="b0afe-124">**Name**</span></span>|<span data-ttu-id="b0afe-125">型**MapToReqDecline.btm**します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-125">Type **MapToReqDecline.btm**.</span></span>|  
  
3.  <span data-ttu-id="b0afe-126">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b0afe-126">Click **Add**.</span></span>  
  
     <span data-ttu-id="b0afe-127">次の図は、送信元スキーマ、送信先スキーマ、およびマッパー グリッドを示します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-127">The following figure shows the Source Schema, Destination Schema, and Mapper Grid.</span></span>  
  
     <span data-ttu-id="b0afe-128">![MapToReqDenied マップ](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")</span><span class="sxs-lookup"><span data-stu-id="b0afe-128">![MapToReqDenied map](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")</span></span>  
  
4.  <span data-ttu-id="b0afe-129">**送信元スキーマ**ウィンドウで、をクリックして**ソース スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-129">In the **Source Schema** pane, click **Open Source Schema**.</span></span>  
  
5.  <span data-ttu-id="b0afe-130">**BizTalk 型の選択** ダイアログ ボックスで、展開**EAISchemas**、展開**スキーマ**、 をクリックして**eaischemas.request**順にクリックします**Ok**します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-130">In the **BizTalk Type Picker** dialog box, expand **EAISchemas**, expand **Schemas**, click **EAISchemas.Request**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b0afe-131">**送信元スキーマ**ウィンドウで、右クリックして**\<スキーマ\>**、順にクリックします**ツリー ノードの展開**します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-131">In the **Source Schema** pane, right-click **\<Schema\>**, and then click **Expand Tree Node**.</span></span>  
  
7.  <span data-ttu-id="b0afe-132">**送信先スキーマ**ウィンドウで、をクリックして**送信先スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-132">In the **Destination Schema** pane, click **Open Destination Schema**.</span></span>  
  
8.  <span data-ttu-id="b0afe-133">**BizTalk 型の選択** ダイアログ ボックスで、展開**EAISchemas**、展開**スキーマ**、 をクリックして**eaischemas.requestdecline**、し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-133">In the **BizTalk Type Picker** dialog box, expand **EAISchemas**, expand **Schemas**, click **EAISchemas.RequestDecline**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="b0afe-134">**送信先スキーマ**ウィンドウで、右クリックして**\<スキーマ\>**、順にクリックします**ツリー ノードの展開**します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-134">In the **Destination Schema** pane, right-click **\<Schema\>**, and then click **Expand Tree Node**.</span></span>  
  
10. <span data-ttu-id="b0afe-135">**送信元スキーマ**ウィンドウで、ドラッグ、 **ReqID**フィールドを**ReqID**で、**送信先スキーマ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="b0afe-135">In the **Source Schema** pane, drag the **ReqID** field to the **ReqID** in the **Destination Schema** pane.</span></span> <span data-ttu-id="b0afe-136">2 つの要素を接続する線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0afe-136">A line appears connecting the two elements.</span></span>  
  
11. <span data-ttu-id="b0afe-137">**送信元スキーマ**ウィンドウで、ドラッグ、 **GrandTotal**フィールドを**GrandTotal**フィールドに、**送信先スキーマ**ペイン、データをマップするには他の 1 つのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="b0afe-137">In the **Source Schema** pane, drag the **GrandTotal** field to the **GrandTotal** field in the **Destination Schema** pane to map the data from one schema to the other.</span></span>  
  
12. <span data-ttu-id="b0afe-138">**ファイル** メニューのをクリックして**すべて保存**作業を保存できます。</span><span class="sxs-lookup"><span data-stu-id="b0afe-138">On the **File** menu, click **Save All** to save your work.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="b0afe-139">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="b0afe-139">What did I just do?</span></span>  
 <span data-ttu-id="b0afe-140">この手順では、要求メッセージを RequestDecline メッセージに変換するマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-140">In this step, you created a map that transforms Request message to RequestDecline message.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="b0afe-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="b0afe-141">Next Steps</span></span>  
 <span data-ttu-id="b0afe-142">EAISchemas プロジェクトをビルドするとします。</span><span class="sxs-lookup"><span data-stu-id="b0afe-142">You build the EAISchemas project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0afe-143">参照</span><span class="sxs-lookup"><span data-stu-id="b0afe-143">See Also</span></span>  
 <span data-ttu-id="b0afe-144">[ステップ 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="b0afe-144">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="b0afe-145">[手順 2:在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="b0afe-145">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="b0afe-146">[ステップ 3:要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="b0afe-146">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="b0afe-147">[手順 4:マップを作成します。](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="b0afe-147">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="b0afe-148">[手順 5:EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="b0afe-148">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 [<span data-ttu-id="b0afe-149">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="b0afe-149">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)