---
title: '手順 1: RFC を呼び出すための vPrev BizTalk プロジェクトの変更 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, modifying previous version of BizTalk project for invoking an RFC
- migration
ms.assetid: 2d4a6cd7-d216-4e0f-8f82-41e044cd325b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e2624ede6d2710db2d82311c2f452f8be372aa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969651"
---
# <a name="step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc"></a><span data-ttu-id="9366e-102">手順 1: RFC を呼び出すための vPrev BizTalk プロジェクトの変更します。</span><span class="sxs-lookup"><span data-stu-id="9366e-102">Step 1: Modify the vPrev BizTalk Project for Invoking an RFC</span></span>
<span data-ttu-id="9366e-103">![ステップ 1/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span><span class="sxs-lookup"><span data-stu-id="9366e-103">![Step 1 of 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-1of3.gif "Step_1of3")</span></span>  
  
 <span data-ttu-id="9366e-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="9366e-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="9366e-105">**目標:** この手順で、次を変更する既存の vPrev BizTalk プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="9366e-105">**Objective:** In this step, you make the following changes to the existing vPrev BizTalk project:</span></span>  
  
- <span data-ttu-id="9366e-106">WCF ベースを使用して、SD_RFC_CUSTOMER_GET RFC のメタデータを生成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9366e-106">Generate metadata for the SD_RFC_CUSTOMER_GET RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="9366e-107">WCF ベースを使用して、RFC を呼び出すための要求メッセージに vPrev SAP アダプターを使用して、RFC を呼び出すための要求メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9366e-107">Map the request message for invoking the RFC using the vPrev SAP adapter to a request message for invoking the RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="9366e-108">WCF ベースを使用して受信応答メッセージにマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]vPrev SAP アダプターの応答メッセージにします。</span><span class="sxs-lookup"><span data-stu-id="9366e-108">Map the response message received using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the response message for the vPrev SAP adapter.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="9366e-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="9366e-109">Prerequisite</span></span>  
  
-   <span data-ttu-id="9366e-110">SAP システムで SD_RFC_CUSTOMER_GET RFC を呼び出すための vPrev BizTalk プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="9366e-110">You must have a vPrev BizTalk project to invoke the SD_RFC_CUSTOMER_GET RFC in the SAP system.</span></span>  
  
### <a name="to-modify-the-vprev-biztalk-project"></a><span data-ttu-id="9366e-111">VPrev BizTalk プロジェクトを変更するには</span><span class="sxs-lookup"><span data-stu-id="9366e-111">To modify the vPrev BizTalk project</span></span>  
  
1. <span data-ttu-id="9366e-112">WCF ベースを使用して、SD_RFC_CUSTOMER_GET RFC のメタデータを生成[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9366e-112">Generate metadata for the SD_RFC_CUSTOMER_GET RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="9366e-113">使用することができます、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]メタデータを生成します。</span><span class="sxs-lookup"><span data-stu-id="9366e-113">You can use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate metadata.</span></span>  
  
    <span data-ttu-id="9366e-114">Rfc のメタデータを生成する方法の詳細については、次を参照してください。[参照、SAP で RFC 操作のメタデータを検索し、get](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="9366e-114">For instructions on how to generate metadata for RFCs, see [Browse, search and get metadata for RFC operations in SAP](../../adapters-and-accelerators/adapter-sap/browse-search-and-get-metadata-for-rfc-operations-in-sap.md).</span></span> <span data-ttu-id="9366e-115">スキーマを生成すると後のような名前のファイル*SapBindingSchema.xsd* BizTalk プロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="9366e-115">After the schema is generated, a file with the name similar to *SapBindingSchema.xsd* is added to the BizTalk project.</span></span> <span data-ttu-id="9366e-116">このファイルには、WCF ベースを使用して SD_RFC_CUSTOMER_GET を呼び出すためのスキーマが含まれています。[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9366e-116">This file contains the schema for invoking the SD_RFC_CUSTOMER_GET using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
2. <span data-ttu-id="9366e-117">SD_RFC_CUSTOMER_GET RFC のメタデータを生成すると、ポートのバインド ファイルも作成します。</span><span class="sxs-lookup"><span data-stu-id="9366e-117">Generating the metadata for the SD_RFC_CUSTOMER_GET RFC also creates a port binding file.</span></span> <span data-ttu-id="9366e-118">次の手順で、SAP システムにメッセージを送信する Wcf-custom 送信ポートを作成するこのバインド ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9366e-118">In the next step, this binding file will be used to create a WCF-Custom send port to send messages to the SAP system.</span></span> <span data-ttu-id="9366e-119">操作の SOAP アクションは、メタデータの生成対象の操作にも設定されます。</span><span class="sxs-lookup"><span data-stu-id="9366e-119">The SOAP action for the operation is also set to the operation for which you generated metadata.</span></span> <span data-ttu-id="9366e-120">SD_RFC_CUSTOMER_GET RFC のメタデータを生成する場合など、送信ポートでの SOAP アクションの操作名では、"SD_RFC_CUSTOMER_GET"になります。</span><span class="sxs-lookup"><span data-stu-id="9366e-120">For example, if you generate metadata for the SD_RFC_CUSTOMER_GET RFC, the operation name in the SOAP action on the send port will be “SD_RFC_CUSTOMER_GET”.</span></span> <span data-ttu-id="9366e-121">ただし、操作名とオーケストレーションの一部異なる可能性があります、たとえば、作成した論理送信ポートで"Operation_1"。</span><span class="sxs-lookup"><span data-stu-id="9366e-121">However, the operation name on the logical send port that you create as part of the orchestration could be different, for example, “Operation_1”.</span></span> <span data-ttu-id="9366e-122">その結果、送信ポートを使用して SAP システムにメッセージを送信するときに、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9366e-122">As a result, when you send messages to the SAP system using the send port, you get an error.</span></span> <span data-ttu-id="9366e-123">これを回避するには、ことを確認しますで論理送信ポート、オーケストレーションでは、メタデータを生成する操作名と同じ操作名。</span><span class="sxs-lookup"><span data-stu-id="9366e-123">To prevent this, make sure the operation name on the logical send port in your orchestration is the same as the operation name for which you generated metadata.</span></span>  
  
    <span data-ttu-id="9366e-124">そのため、このチュートリアルでは、場合 SD_RFC_CUSTOMER_GET RFC のメタデータを生成するための名前を変更"SD_RFC_CUSTOMER_GET"する論理送信ポートの操作。</span><span class="sxs-lookup"><span data-stu-id="9366e-124">So, in the case of this tutorial, because you generate metadata for the SD_RFC_CUSTOMER_GET RFC, change the name of the logical send port operation to “SD_RFC_CUSTOMER_GET”.</span></span>  
  
3. <span data-ttu-id="9366e-125">要求メッセージは、WCF ベースを使用して生成されたスキーマに vPrev SAP アダプターを使用して生成されたスキーマをマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9366e-125">For the request message, map the schema generated using vPrev SAP adapter to the schema generated using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
   1. <span data-ttu-id="9366e-126">BizTalk マッパーは、BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="9366e-126">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="9366e-127">BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-127">Right-click the BizTalk project, point to **Add**, and then click **New Item**.</span></span>  
  
       <span data-ttu-id="9366e-128">**新しい項目の追加**ダイアログ ボックスで、左側のウィンドウから**マップ ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-128">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="9366e-129">右側のウィンドウから次のように選択します。**マップ**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-129">From the right pane, select **Map**.</span></span> <span data-ttu-id="9366e-130">マップの名前を指定します。 **RequestMap.btm**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-130">Specify a name for the map, such as **RequestMap.btm**.</span></span> <span data-ttu-id="9366e-131">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9366e-131">Click **Add**.</span></span>  
  
   2. <span data-ttu-id="9366e-132">送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-132">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
   3. <span data-ttu-id="9366e-133">**BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev SAP アダプターの要求メッセージのスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="9366e-133">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the vPrev SAP adapter.</span></span> <span data-ttu-id="9366e-134">このチュートリアルでは、次のように選択します。 *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-134">For this tutorial, select *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*,and then click **OK**.</span></span>  
  
   4. <span data-ttu-id="9366e-135">**送信元スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GET_Request*、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-135">In the **Root Node for Source Schema** dialog box, select *SD_RFC_CUSTOMER_GET_Request*, and then click **OK**.</span></span>  
  
   5. <span data-ttu-id="9366e-136">送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-136">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
   6. <span data-ttu-id="9366e-137">**BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの要求メッセージのスキーマを選択して[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9366e-137">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the request message for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="9366e-138">このチュートリアルでは、次のように選択します。 *SAP_Migration.SapBindingSchema*、[ok] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9366e-138">For this tutorial, select *SAP_Migration.SapBindingSchema*, and then click OK.</span></span>  
  
   7. <span data-ttu-id="9366e-139">**ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GET*、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-139">In the **Root Node for Target Schema** dialog box, select *SD_RFC_CUSTOMER_GET*, and then click **OK**.</span></span>  
  
       <span data-ttu-id="9366e-140">次の図に示すように、両方のスキーマでは、それぞれの要素をマップします。</span><span class="sxs-lookup"><span data-stu-id="9366e-140">Map the respective elements in both the schemas as illustrated in the following figure.</span></span> <span data-ttu-id="9366e-141">文字列左スペース削除 functoid を使用して CUSTOMER_T 要素をマップします。</span><span class="sxs-lookup"><span data-stu-id="9366e-141">Map the CUSTOMER_T element using a String Left Trim functoid.</span></span> <span data-ttu-id="9366e-142">、**ツールボックス**、ドラッグ、**文字列左スペース削除**functoid し、マッパーのグリッドにドロップします。</span><span class="sxs-lookup"><span data-stu-id="9366e-142">To do so, from the **Toolbox**, drag the **String Left Trim** functoid and drop it on the mapper grid.</span></span> <span data-ttu-id="9366e-143">接続、 **CUSTOMER_T** functoid への送信元スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="9366e-143">Connect the **CUSTOMER_T** element in the source schema to the functoid.</span></span> <span data-ttu-id="9366e-144">同様に、接続、 **CUSTOMER_T**を functoid に送信先スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="9366e-144">Similarly, connect the **CUSTOMER_T** element in the destination schema to the functoid.</span></span> <span data-ttu-id="9366e-145">次の図は、functoid を使用して 2 つの要素をマップする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9366e-145">The following figure illustrates how the two elements are mapped via the functoid.</span></span>  
  
       <span data-ttu-id="9366e-146">![アダプター バージョン間の要求メッセージをマップ](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")</span><span class="sxs-lookup"><span data-stu-id="9366e-146">![Map the request messages between adapter versions](../../adapters-and-accelerators/adapter-sap/media/f12f280d-766f-4647-bced-435354206fb9.gif "f12f280d-766f-4647-bced-435354206fb9")</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="9366e-147">文字列左スペース削除 functoid の詳細についてを参照してください"文字列左トリミング Functoid" [ http://go.microsoft.com/fwlink/?LinkId=105774](http://go.microsoft.com/fwlink/?LinkId=105774)します。</span><span class="sxs-lookup"><span data-stu-id="9366e-147">For more information about the String Left Trim functoid, see "String Left Trim Functoid" at [http://go.microsoft.com/fwlink/?LinkId=105774](http://go.microsoft.com/fwlink/?LinkId=105774).</span></span>  
  
   8. <span data-ttu-id="9366e-148">マップを保存します。</span><span class="sxs-lookup"><span data-stu-id="9366e-148">Save the map.</span></span>  
  
4. <span data-ttu-id="9366e-149">応答メッセージは、WCF ベースを使用して生成されたスキーマに vPrev SAP アダプターを使用して生成されたスキーマをマップ[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9366e-149">For the response message, map the schema generated using vPrev SAP adapter to the schema generated using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
   1. <span data-ttu-id="9366e-150">BizTalk マッパーは、BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="9366e-150">Add a BizTalk mapper to the BizTalk project.</span></span> <span data-ttu-id="9366e-151">BizTalk プロジェクトを右クリックし、[**追加**、] をクリック**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-151">Right-click the BizTalk project, point to **Add**, and click **New Item**.</span></span>  
  
       <span data-ttu-id="9366e-152">**新しい項目の追加**ダイアログ ボックスで、左側のウィンドウから**マップ ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-152">In the **Add New Item** dialog box, from the left pane, select **Map Files**.</span></span> <span data-ttu-id="9366e-153">右側のウィンドウから次のように選択します。**マップ**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-153">From the right pane, select **Map**.</span></span> <span data-ttu-id="9366e-154">マップの名前を指定します。 **ResponseMap.btm**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-154">Specify a name for the map, such as **ResponseMap.btm**.</span></span> <span data-ttu-id="9366e-155">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9366e-155">Click **Add**.</span></span>  
  
   2. <span data-ttu-id="9366e-156">送信元スキーマ ペインで、次のようにクリックします。**ソース スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-156">From the Source Schema pane, click **Open Source Schema**.</span></span>  
  
   3. <span data-ttu-id="9366e-157">**BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、WCF ベースの応答メッセージのスキーマを選択して[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="9366e-157">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="9366e-158">このチュートリアルでは、次のように選択します。 *SAP_Migration.SapBindingSchema*、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-158">For this tutorial, select *SAP_Migration.SapBindingSchema*, and then click **OK**.</span></span>  
  
   4. <span data-ttu-id="9366e-159">**送信元スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GETResponse*、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-159">In the **Root Node for Source Schema** dialog box, select *SD_RFC_CUSTOMER_GETResponse*, and then click **OK**.</span></span>  
  
   5. <span data-ttu-id="9366e-160">送信先スキーマ ペインで、次のようにクリックします。**送信先スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-160">From the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
   6. <span data-ttu-id="9366e-161">**BizTalk 型の選択** ダイアログ ボックスで、プロジェクト名を展開し、展開**スキーマ**、vPrev SAP アダプターの応答メッセージのスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="9366e-161">In the **BizTalk Type Picker** dialog box, expand the project name, expand **Schemas**, and select the schema for the response message for the vPrev SAP adapter.</span></span> <span data-ttu-id="9366e-162">このチュートリアルでは、次のように選択します。 *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-162">For this tutorial, select *SAP_Migration.SD_RFC_CUSTOMER_GET__x32003*, and then click **OK**.</span></span>  
  
   7. <span data-ttu-id="9366e-163">**ターゲット スキーマのルート ノード**ダイアログ ボックスで、 *SD_RFC_CUSTOMER_GET_Response*、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-163">In the **Root Node for Target Schema** dialog box, select *SD_RFC_CUSTOMER_GET_Response*, and then click **OK**.</span></span>  
  
   8. <span data-ttu-id="9366e-164">次の図に示すように、両方のスキーマでは、それぞれの要素をマップします。</span><span class="sxs-lookup"><span data-stu-id="9366e-164">Map the respective elements in both the schemas as illustrated in the following figure.</span></span>  
  
       <span data-ttu-id="9366e-165">![アダプター バージョン間の応答メッセージをマップ](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")</span><span class="sxs-lookup"><span data-stu-id="9366e-165">![Map the response messages between adapter versions](../../adapters-and-accelerators/adapter-sap/media/d8dddaba-d978-4159-bcc6-6a6bfee36564.gif "d8dddaba-d978-4159-bcc6-6a6bfee36564")</span></span>  
  
   9. <span data-ttu-id="9366e-166">マップを保存します。</span><span class="sxs-lookup"><span data-stu-id="9366e-166">Save the map.</span></span>  
  
5. <span data-ttu-id="9366e-167">保存し、BizTalk ソリューションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="9366e-167">Save and build the BizTalk solution.</span></span> <span data-ttu-id="9366e-168">クリックして、ソリューションを右クリックして**ソリューションのビルド**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-168">Right-click the solution, and then click **Build Solution**.</span></span>  
  
6. <span data-ttu-id="9366e-169">ソリューションを展開する。</span><span class="sxs-lookup"><span data-stu-id="9366e-169">Deploy the solution.</span></span> <span data-ttu-id="9366e-170">クリックして、ソリューションを右クリックして**ソリューションの配置**します。</span><span class="sxs-lookup"><span data-stu-id="9366e-170">Right-click the solution, and then click **Deploy Solution**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9366e-171">次の手順</span><span class="sxs-lookup"><span data-stu-id="9366e-171">Next Steps</span></span>  
 <span data-ttu-id="9366e-172">Wcf-custom 送信ポートを作成および構成」の説明に従って、この手順で作成したマップを使用するように[手順 2: BizTalk Server 管理コンソールでオーケストレーションを構成](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)します。</span><span class="sxs-lookup"><span data-stu-id="9366e-172">Create a WCF-Custom send port, and configure it to use the maps you created in this step, as described in [Step 2: Configure the Orchestration in BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9366e-173">参照</span><span class="sxs-lookup"><span data-stu-id="9366e-173">See Also</span></span>  
 [<span data-ttu-id="9366e-174">チュートリアル 2: SAP の RFC BizTalk プロジェクトを移行する</span><span class="sxs-lookup"><span data-stu-id="9366e-174">Tutorial 2: Migrating an SAP RFC BizTalk Project</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-2-migrating-an-sap-rfc-biztalk-project.md)