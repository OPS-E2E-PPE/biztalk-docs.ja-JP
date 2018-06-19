---
title: '手順 4: マップの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: 9fcbce54a488cb687ad0fb2c7a1931243c8cd882
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973984"
---
# <a name="step-4-create-the-map"></a><span data-ttu-id="d4f80-102">ステップ 4: マップの作成</span><span class="sxs-lookup"><span data-stu-id="d4f80-102">Step 4: Create the Map</span></span>
<span data-ttu-id="d4f80-103">![手順 5 の 4](../core/media/step-4of5.gif "Step_4of5")</span><span class="sxs-lookup"><span data-stu-id="d4f80-103">![Step 4 of 5](../core/media/step-4of5.gif "Step_4of5")</span></span>  
  
 <span data-ttu-id="d4f80-104">**所要時間:** 6 分</span><span class="sxs-lookup"><span data-stu-id="d4f80-104">**Time to complete:** 6 minutes</span></span>  
  
 <span data-ttu-id="d4f80-105">**目標:** この手順では、要求メッセージを RequestDecline メッセージに変換するマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4f80-105">**Objective:** In this step, you create a map that transforms Request message to RequestDecline message.</span></span>  
  
 <span data-ttu-id="d4f80-106">**目的:** マップ、倉庫在庫システムに返される要求拒否メッセージで、要求 ID 番号と総計が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d4f80-106">**Purpose:** The map ensures that the request ID number and the grand total are included in the request decline message returned to the warehouse inventory system.</span></span> <span data-ttu-id="d4f80-107">ここでは BizTalk マッパーを使用して、送信メッセージ用に定義されているフィールドに受信メッセージのフィールドを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="d4f80-107">You use BizTalk Mapper to link fields in an incoming message to fields defined for the outgoing message.</span></span> <span data-ttu-id="d4f80-108">この操作は、2 種類のメッセージのスキーマ構造が異なるため、必要です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-108">This is necessary because these two messages do not have the same schema structure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d4f80-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="d4f80-109">Prerequisites</span></span>  
 <span data-ttu-id="d4f80-110">このステップを開始する前に、以下の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="d4f80-110">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="d4f80-111">この手順を開始する前に行う必要があります[手順 2: 在庫要求スキーマの作成](../core/step-2-create-the-inventory-request-schema.md)と[手順 3: 要求拒否スキーマを作成する](../core/step-3-create-the-request-decline-schema.md)です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-111">Before you begin this step you must complete [Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) and [Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d4f80-112">手順</span><span class="sxs-lookup"><span data-stu-id="d4f80-112">Procedures</span></span>  
 <span data-ttu-id="d4f80-113">マップは、Request スキーマまたは RequestDecline スキーマのいずれであるかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="d4f80-113">The map depends on the Request schema and the RequestDecline schema.</span></span>  <span data-ttu-id="d4f80-114">これらのスキーマをマップで使用するには、スキーマを使用してプロジェクトをコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d4f80-114">You much compile the project with the schema before you can use them on a map.</span></span>  
  
#### <a name="to-compile-the-eaischemas-project"></a><span data-ttu-id="d4f80-115">EAISchemas プロジェクトをコンパイルするには</span><span class="sxs-lookup"><span data-stu-id="d4f80-115">To compile the EAISchemas project</span></span>  
  
-   <span data-ttu-id="d4f80-116">ソリューション エクスプ ローラーで右クリック**EAISchemas**、クリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-116">In Solution Explorer, right-click **EAISchemas**, and then click **Build**.</span></span>  
  
#### <a name="to-create-the-map"></a><span data-ttu-id="d4f80-117">マップを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d4f80-117">To create the map</span></span>  
  
1.  <span data-ttu-id="d4f80-118">ソリューション エクスプ ローラーで右クリックし、 **EAISchemas**プロジェクトをポイントし、**追加**、順にクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="d4f80-118">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="d4f80-119">**新しい項目の追加 - EAISchemas**  ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="d4f80-119">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="d4f80-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="d4f80-120">Use this</span></span>|<span data-ttu-id="d4f80-121">目的</span><span class="sxs-lookup"><span data-stu-id="d4f80-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="d4f80-122">**インストールされたテンプレート**</span><span class="sxs-lookup"><span data-stu-id="d4f80-122">**Installed Templates**</span></span>|<span data-ttu-id="d4f80-123">をクリックして**マップ ファイル**、クリックして**マップ**です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-123">Click **Map Files**, and then click **Map**.</span></span>|  
    |<span data-ttu-id="d4f80-124">**名前**</span><span class="sxs-lookup"><span data-stu-id="d4f80-124">**Name**</span></span>|<span data-ttu-id="d4f80-125">型**MapToReqDecline.btm**です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-125">Type **MapToReqDecline.btm**.</span></span>|  
  
3.  <span data-ttu-id="d4f80-126">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d4f80-126">Click **Add**.</span></span>  
  
     <span data-ttu-id="d4f80-127">送信元スキーマ、送信先スキーマ、およびマッパー グリッドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d4f80-127">The following figure shows the Source Schema, Destination Schema, and Mapper Grid.</span></span>  
  
     <span data-ttu-id="d4f80-128">![MapToReqDenied マップ](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")</span><span class="sxs-lookup"><span data-stu-id="d4f80-128">![MapToReqDenied map](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")</span></span>  
  
4.  <span data-ttu-id="d4f80-129">**送信元スキーマ** ウィンドウで、をクリックして**ソース スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-129">In the **Source Schema** pane, click **Open Source Schema**.</span></span>  
  
5.  <span data-ttu-id="d4f80-130">**BizTalk 型の選択** ダイアログ ボックスで、展開**EAISchemas**、展開**スキーマ**をクリックして**eaischemas.request**をクリックして**Ok**です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-130">In the **BizTalk Type Picker** dialog box, expand **EAISchemas**, expand **Schemas**, click **EAISchemas.Request**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="d4f80-131">**送信元スキーマ** ウィンドウを右クリックして**\<スキーマ\>**、クリックして**ツリー ノードの展開**です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-131">In the **Source Schema** pane, right-click **\<Schema\>**, and then click **Expand Tree Node**.</span></span>  
  
7.  <span data-ttu-id="d4f80-132">**送信先スキーマ** ウィンドウで、をクリックして**送信先スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-132">In the **Destination Schema** pane, click **Open Destination Schema**.</span></span>  
  
8.  <span data-ttu-id="d4f80-133">**BizTalk 型の選択** ダイアログ ボックスで、展開**EAISchemas**、展開**スキーマ**をクリックして**eaischemas.requestdecline**、し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-133">In the **BizTalk Type Picker** dialog box, expand **EAISchemas**, expand **Schemas**, click **EAISchemas.RequestDecline**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="d4f80-134">**送信先スキーマ** ウィンドウを右クリックして**\<スキーマ\>**、クリックして**ツリー ノードの展開**です。</span><span class="sxs-lookup"><span data-stu-id="d4f80-134">In the **Destination Schema** pane, right-click **\<Schema\>**, and then click **Expand Tree Node**.</span></span>  
  
10. <span data-ttu-id="d4f80-135">**送信元スキーマ** ウィンドウで、ドラッグ、 **ReqID**フィールドを**ReqID**で、**送信先スキーマ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="d4f80-135">In the **Source Schema** pane, drag the **ReqID** field to the **ReqID** in the **Destination Schema** pane.</span></span> <span data-ttu-id="d4f80-136">これら 2 要素を接続する線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d4f80-136">A line appears connecting the two elements.</span></span>  
  
11. <span data-ttu-id="d4f80-137">**送信元スキーマ** ウィンドウで、ドラッグ、 **GrandTotal**フィールドを**GrandTotal**フィールドで、**送信先スキーマ**ペイン、データをマップするには他の 1 つのスキーマです。</span><span class="sxs-lookup"><span data-stu-id="d4f80-137">In the **Source Schema** pane, drag the **GrandTotal** field to the **GrandTotal** field in the **Destination Schema** pane to map the data from one schema to the other.</span></span>  
  
12. <span data-ttu-id="d4f80-138">**ファイル** メニューのをクリックして**すべて保存**作業内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="d4f80-138">On the **File** menu, click **Save All** to save your work.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="d4f80-139">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="d4f80-139">What did I just do?</span></span>  
 <span data-ttu-id="d4f80-140">このステップでは、Request メッセージを RequestDecline メッセージに変換するマップを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d4f80-140">In this step, you created a map that transforms Request message to RequestDecline message.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d4f80-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="d4f80-141">Next Steps</span></span>  
 <span data-ttu-id="d4f80-142">EAISchemas プロジェクトをビルドします。</span><span class="sxs-lookup"><span data-stu-id="d4f80-142">You build the EAISchemas project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4f80-143">参照</span><span class="sxs-lookup"><span data-stu-id="d4f80-143">See Also</span></span>  
 <span data-ttu-id="d4f80-144">[手順 1: EAISchemas プロジェクトを作成します。](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="d4f80-144">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="d4f80-145">[手順 2: 在庫要求スキーマを作成します。](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="d4f80-145">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="d4f80-146">[手順 3: 要求拒否スキーマを作成します。](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="d4f80-146">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="d4f80-147">[手順 4: マップを作成します。](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="d4f80-147">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="d4f80-148">[手順 5: EAISchemas プロジェクトをビルドします。](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="d4f80-148">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 [<span data-ttu-id="d4f80-149">BizTalk マッパーを使用してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4f80-149">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)