---
title: "手順 3: Price and Availability プロジェクトを使用して BizTalk マッパーの Contoso LOB アプリケーションの作成はマップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: private process tutorial, creating LOB maps
ms.assetid: a947e0ac-f0cb-4be9-85a8-09daf3675b1a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3478997abd4e5bb15bfeb977e05ca3edc7348e0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-creating-the-contoso-lob-application-maps-for-the-price-and-availability-project-using-biztalk-mapper"></a><span data-ttu-id="09782-102">手順 3: Price and Availability プロジェクトの BizTalk マッパーを使用して用の Contoso LOB アプリケーション マップの作成</span><span class="sxs-lookup"><span data-stu-id="09782-102">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>
<span data-ttu-id="09782-103">ここでは、2 つのマップを作成します。このマップは 2 つの取引先間でメッセージを正常に交換するために必要な変換を定義します。</span><span class="sxs-lookup"><span data-stu-id="09782-103">In this step, you create two maps that define the transformation required to successfully exchange messages between the two trading partners.</span></span> <span data-ttu-id="09782-104">このシナリオでは、Contoso ERP システムは Price and Availability Request のメッセージ形式を既に標準化しています。</span><span class="sxs-lookup"><span data-stu-id="09782-104">For this scenario, the Contoso ERP system has already standardized on a message format for a Price and Availability request.</span></span> <span data-ttu-id="09782-105">2 つのマップは、取引先である Fabrikam からの要求メッセージと応答メッセージを、内部的に定義された Contoso のメッセージにそれぞれマップします。</span><span class="sxs-lookup"><span data-stu-id="09782-105">The two maps will map the request and response messages from the trading partner, Fabrikam, to and from those internally defined Contoso messages, respectively.</span></span>  
  
### <a name="to-add-a-reference-for-the-3a2-priceandavailability-request-schema"></a><span data-ttu-id="09782-106">3A2 PriceAndAvailability Request スキーマの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="09782-106">To add a reference for the 3A2 PriceAndAvailability Request schema</span></span>  
  
1.  <span data-ttu-id="09782-107">ソリューション エクスプ ローラーで、[contosopriceandavailability] プロジェクトを右クリックし、をクリックして**参照の追加**です。</span><span class="sxs-lookup"><span data-stu-id="09782-107">In Solution Explorer, right-click the ContosoPriceAndAvailability project, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="09782-108">[参照の追加] ダイアログ ボックスで、**参照**です。</span><span class="sxs-lookup"><span data-stu-id="09782-108">In the Add Reference dialog box, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="09782-109">フォルダーに移動*\<ドライブ >*: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for rosettanet \bin し、選択、 **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="09782-109">Move to the folder *\<drive>*:\Program Files\Microsoft BizTalk \<version> Accelerator for RosettaNet\Bin, and then select the **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll** assembly.</span></span>  
  
4.  <span data-ttu-id="09782-110">をクリックして**追加**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="09782-110">Click **Add**, and then click **OK**.</span></span>  
  
### <a name="to-create-the-3a2-priceandavailability-request-to-contoso-priceandavailability-request-map"></a><span data-ttu-id="09782-111">3A2 PriceAndAvailability 要求から Contoso PriceAndAvailability 要求へのマップを作成するには</span><span class="sxs-lookup"><span data-stu-id="09782-111">To create the 3A2 PriceAndAvailability request to Contoso PriceAndAvailability request map</span></span>  
  
1.  <span data-ttu-id="09782-112">ソリューション エクスプ ローラーで、contosopriceandavailability プロジェクトを右クリックし、**追加**、クリックして**新しい項目の**です。</span><span class="sxs-lookup"><span data-stu-id="09782-112">In Solution Explorer, right-click the ContosoPriceAndAvailability project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="09782-113">新しい項目の追加 - ContosoPriceAndAvailability ダイアログ ボックスで選択**マップ ファイル**カテゴリ ウィンドウで、選択**マップ**で、**テンプレート**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="09782-113">In the Add New Item - ContosoPriceAndAvailability dialog box, select **Map Files** in the Categories pane, and then select **Map** in the **Templates** pane.</span></span> <span data-ttu-id="09782-114">**名前**ボックスに、入力**PIP3A2RequestToContosoPriceRequest**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="09782-114">In the **Name** box, type **PIP3A2RequestToContosoPriceRequest**, and then click **Add**.</span></span>  
  
### <a name="to-associate-the-schemas-for-the-pip3a2requesttocontosopricerequest-map"></a><span data-ttu-id="09782-115">PIP3A2RequestToContosoPriceRequest マップのスキーマを関連付けるには</span><span class="sxs-lookup"><span data-stu-id="09782-115">To associate the schemas for the PIP3A2RequestToContosoPriceRequest map</span></span>  
  
1.  <span data-ttu-id="09782-116">(Pip3a2requesttocontosopricerequest.btm が表示されます)、BizTalk マッパーで送信元スキーマ ペインで、をクリックして**ソース スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="09782-116">In BizTalk Mapper (with PIP3A2RequestToContosoPriceRequest.btm displayed), in the Source Schema pane, click **Open Source Schema**.</span></span>  
  
2.  <span data-ttu-id="09782-117">BizTalk 型の選択 ダイアログ ボックスで、展開**ContosoPriceAndAvailability**、展開**参照**、展開**Microsoft.Solutions.BTARN.Schemas.RNPIPs**、し、展開**スキーマです。**</span><span class="sxs-lookup"><span data-stu-id="09782-117">In the BizTalk Type Picker dialog box, expand **ContosoPriceAndAvailability**, expand **References**, expand **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, and then expand **Schemas.**</span></span>  
  
3.  <span data-ttu-id="09782-118">選択**Microsoft.Solutions.BTARN.Schemas.RNPIPs です。**</span><span class="sxs-lookup"><span data-stu-id="09782-118">Select **Microsoft.Solutions.BTARN.Schemas.RNPIPs.**</span></span>  
  
     <span data-ttu-id="09782-119">**_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="09782-119">**_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="09782-120">送信先スキーマ ペインで、をクリックして**送信先スキーマを開く**です。</span><span class="sxs-lookup"><span data-stu-id="09782-120">In the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
5.  <span data-ttu-id="09782-121">BizTalk 型の選択 ダイアログ ボックスで、展開**ContosoPriceAndAvailability**、順に展開**スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="09782-121">In the BizTalk Type Picker dialog box, expand **ContosoPriceAndAvailability**, and then expand **Schemas**.</span></span>  
  
6.  <span data-ttu-id="09782-122">選択、 **ContosoPriceAndAvailability.ContosoPriceSchema**スキーマ、およびクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="09782-122">Select the **ContosoPriceAndAvailability.ContosoPriceSchema** schema, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="09782-123">ターゲット スキーマ ダイアログ ボックスのルート ノードで、選択、 **rootPriceRequest**スキーマ、およびクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="09782-123">In the Root Node for Target Schema dialog box, select the **rootPriceRequest** schema, and then click **OK**.</span></span>  
  
### <a name="to-link-schema-fields-in-the-pip3a2requesttocontosopricerequest-map"></a><span data-ttu-id="09782-124">PIP3A2RequestToContosoPriceRequest マップのスキーマ フィールドをリンクするには</span><span class="sxs-lookup"><span data-stu-id="09782-124">To link schema fields in the PIP3A2RequestToContosoPriceRequest map</span></span>  
  
1.  <span data-ttu-id="09782-125">送信先スキーマ ペインで右クリックし、 **\<スキーマ >**ノードをクリックして**ツリー ノードの展開**です。</span><span class="sxs-lookup"><span data-stu-id="09782-125">In the Destination Schema pane, right-click the **\<Schema>** node, and then click **Expand Tree Node**.</span></span>  
  
2.  <span data-ttu-id="09782-126">送信元スキーマ ペインで右クリックし、 **\<スキーマ >**ノードをクリックして**ツリー ノードの展開**です。</span><span class="sxs-lookup"><span data-stu-id="09782-126">In the Source Schema pane, right-click the **\<Schema>** node, and then click **Expand Tree Node**.</span></span>  
  
3.  <span data-ttu-id="09782-127">ドラッグ、 **GlobalProductIdentifier**フィールドを**ProductID**送信先スキーマ ペインでフィールドです。</span><span class="sxs-lookup"><span data-stu-id="09782-127">Drag the **GlobalProductIdentifier** field to the **ProductID** field in the Destination Schema pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="09782-128">検索することができます、 **GlobalProductIdentifier**フィールドで、pip3a2priceandavailabilityquery/productpriceandavailabilityquery/</span><span class="sxs-lookup"><span data-stu-id="09782-128">You can find the **GlobalProductIdentifier** field in the node Pip3A2PriceAndAvailabilityQuery/ProductPriceAndAvailabilityQuery/</span></span>  
    >   
    >  <span data-ttu-id="09782-129">ProductPriceAndAvailability/ProductLineItem/productUnit/</span><span class="sxs-lookup"><span data-stu-id="09782-129">ProductPriceAndAvailability/ProductLineItem/productUnit/</span></span>  
    >   
    >  <span data-ttu-id="09782-130">ProductPackageDescription/ProductIdentification ノードにあります。</span><span class="sxs-lookup"><span data-stu-id="09782-130">ProductPackageDescription/ProductIdentification.</span></span>  
  
4.  <span data-ttu-id="09782-131">**ファイル** メニューのをクリックして**すべて保存**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="09782-131">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09782-132">参照</span><span class="sxs-lookup"><span data-stu-id="09782-132">See Also</span></span>  
 [<span data-ttu-id="09782-133">作成して、Contoso の BizTalk ポートの構成</span><span class="sxs-lookup"><span data-stu-id="09782-133">Creating and Configuring BizTalk Ports for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)