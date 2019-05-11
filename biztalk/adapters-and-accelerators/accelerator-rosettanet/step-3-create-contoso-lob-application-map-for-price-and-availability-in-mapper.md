---
title: 手順 3:Price and Availability プロジェクトを使用して BizTalk マッパーの Contoso LOB アプリケーションを作成するマップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB maps
ms.assetid: a947e0ac-f0cb-4be9-85a8-09daf3675b1a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d7a1289bc11517e97bac706803ad0c78dbc2d5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281152"
---
# <a name="step-3-creating-the-contoso-lob-application-maps-for-the-price-and-availability-project-using-biztalk-mapper"></a><span data-ttu-id="998f8-102">手順 3:Price and Availability プロジェクトの BizTalk マッパーを使用して用の Contoso LOB アプリケーション マップを作成します。</span><span class="sxs-lookup"><span data-stu-id="998f8-102">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>
<span data-ttu-id="998f8-103">この手順では、2 つの取引先間でメッセージを正常に交換するために必要な変換を定義する 2 つのマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="998f8-103">In this step, you create two maps that define the transformation required to successfully exchange messages between the two trading partners.</span></span> <span data-ttu-id="998f8-104">このシナリオで、Contoso ERP システムが Price and Availability 要求のメッセージ形式に標準化されています。</span><span class="sxs-lookup"><span data-stu-id="998f8-104">For this scenario, the Contoso ERP system has already standardized on a message format for a Price and Availability request.</span></span> <span data-ttu-id="998f8-105">2 つのマップは、Fabrikam 取引先からの要求および応答メッセージ、内部的に定義された Contoso のメッセージを送受信するそれぞれマップします。</span><span class="sxs-lookup"><span data-stu-id="998f8-105">The two maps will map the request and response messages from the trading partner, Fabrikam, to and from those internally defined Contoso messages, respectively.</span></span>  
  
### <a name="to-add-a-reference-for-the-3a2-priceandavailability-request-schema"></a><span data-ttu-id="998f8-106">3 a 2 PriceAndAvailability Request スキーマの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="998f8-106">To add a reference for the 3A2 PriceAndAvailability Request schema</span></span>  
  
1.  <span data-ttu-id="998f8-107">ソリューション エクスプ ローラーで [contosopriceandavailability] プロジェクトを右クリックし、クリックして**参照の追加**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-107">In Solution Explorer, right-click the ContosoPriceAndAvailability project, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="998f8-108">[参照の追加] ダイアログ ボックスで、**参照**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-108">In the Add Reference dialog box, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="998f8-109">フォルダーに移動*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \bin を選択し、 **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll**アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="998f8-109">Move to the folder *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin, and then select the **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll** assembly.</span></span>  
  
4.  <span data-ttu-id="998f8-110">クリックして**追加**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-110">Click **Add**, and then click **OK**.</span></span>  
  
### <a name="to-create-the-3a2-priceandavailability-request-to-contoso-priceandavailability-request-map"></a><span data-ttu-id="998f8-111">Contoso の PriceAndAvailability 要求へのマップを 3 a 2 PriceAndAvailability 要求を作成するには</span><span class="sxs-lookup"><span data-stu-id="998f8-111">To create the 3A2 PriceAndAvailability request to Contoso PriceAndAvailability request map</span></span>  
  
1.  <span data-ttu-id="998f8-112">ソリューション エクスプ ローラーで、contosopriceandavailability プロジェクトを右クリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-112">In Solution Explorer, right-click the ContosoPriceAndAvailability project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="998f8-113">新しい項目の追加 - ContosoPriceAndAvailability ダイアログ ボックスでは、次のように選択します。**マップ ファイル**カテゴリ ウィンドウで選択し**マップ**で、**テンプレート**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="998f8-113">In the Add New Item - ContosoPriceAndAvailability dialog box, select **Map Files** in the Categories pane, and then select **Map** in the **Templates** pane.</span></span> <span data-ttu-id="998f8-114">**名前**ボックスに「 **PIP3A2RequestToContosoPriceRequest**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-114">In the **Name** box, type **PIP3A2RequestToContosoPriceRequest**, and then click **Add**.</span></span>  
  
### <a name="to-associate-the-schemas-for-the-pip3a2requesttocontosopricerequest-map"></a><span data-ttu-id="998f8-115">PIP3A2RequestToContosoPriceRequest マップのスキーマを関連付ける</span><span class="sxs-lookup"><span data-stu-id="998f8-115">To associate the schemas for the PIP3A2RequestToContosoPriceRequest map</span></span>  
  
1.  <span data-ttu-id="998f8-116">(Pip3a2requesttocontosopricerequest.btm が表示されます)、BizTalk マッパーで、送信元スキーマ ペインで次のようにクリックします。**ソース スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-116">In BizTalk Mapper (with PIP3A2RequestToContosoPriceRequest.btm displayed), in the Source Schema pane, click **Open Source Schema**.</span></span>  
  
2.  <span data-ttu-id="998f8-117">BizTalk 型の選択 ダイアログ ボックスで、 **ContosoPriceAndAvailability**、展開**参照**、展開**microsoft.solutions.btarn.schemas.rnpips**、し、展開**スキーマ。**</span><span class="sxs-lookup"><span data-stu-id="998f8-117">In the BizTalk Type Picker dialog box, expand **ContosoPriceAndAvailability**, expand **References**, expand **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, and then expand **Schemas.**</span></span>  
  
3.  <span data-ttu-id="998f8-118">選択 **[microsoft.solutions.btarn.schemas.rnpips]。**</span><span class="sxs-lookup"><span data-stu-id="998f8-118">Select **Microsoft.Solutions.BTARN.Schemas.RNPIPs.**</span></span>  
  
     <span data-ttu-id="998f8-119">**_ 3 a2priceandavailabilityquerymessageguideline_v1_3**、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-119">**_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="998f8-120">送信先スキーマ ペインで次のようにクリックします。**送信先スキーマを開く**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-120">In the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
5.  <span data-ttu-id="998f8-121">BizTalk 型の選択 ダイアログ ボックスで、 **ContosoPriceAndAvailability**、順に展開**スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-121">In the BizTalk Type Picker dialog box, expand **ContosoPriceAndAvailability**, and then expand **Schemas**.</span></span>  
  
6.  <span data-ttu-id="998f8-122">選択、 **ContosoPriceAndAvailability.ContosoPriceSchema**スキーマ、およびクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-122">Select the **ContosoPriceAndAvailability.ContosoPriceSchema** schema, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="998f8-123">ターゲット スキーマ ダイアログ ボックスの ルート ノードで選択、 **rootpricerequest**スキーマ、およびクリック**OK**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-123">In the Root Node for Target Schema dialog box, select the **rootPriceRequest** schema, and then click **OK**.</span></span>  
  
### <a name="to-link-schema-fields-in-the-pip3a2requesttocontosopricerequest-map"></a><span data-ttu-id="998f8-124">PIP3A2RequestToContosoPriceRequest マップのスキーマのフィールドをリンクするには</span><span class="sxs-lookup"><span data-stu-id="998f8-124">To link schema fields in the PIP3A2RequestToContosoPriceRequest map</span></span>  
  
1.  <span data-ttu-id="998f8-125">送信先スキーマ ペインで右クリックし、 **\<スキーマ\>** ノードをクリック**ツリー ノードの展開**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-125">In the Destination Schema pane, right-click the **\<Schema\>** node, and then click **Expand Tree Node**.</span></span>  
  
2.  <span data-ttu-id="998f8-126">送信元スキーマ ペインで右クリックし、 **\<スキーマ\>** ノードをクリック**ツリー ノードの展開**します。</span><span class="sxs-lookup"><span data-stu-id="998f8-126">In the Source Schema pane, right-click the **\<Schema\>** node, and then click **Expand Tree Node**.</span></span>  
  
3.  <span data-ttu-id="998f8-127">ドラッグ、 **GlobalProductIdentifier**フィールドを**ProductID**送信先スキーマ ペインでフィールド。</span><span class="sxs-lookup"><span data-stu-id="998f8-127">Drag the **GlobalProductIdentifier** field to the **ProductID** field in the Destination Schema pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="998f8-128">検索することができます、 **GlobalProductIdentifier**フィールドには、pip3a2priceandavailabilityquery/productpriceandavailabilityquery/</span><span class="sxs-lookup"><span data-stu-id="998f8-128">You can find the **GlobalProductIdentifier** field in the node Pip3A2PriceAndAvailabilityQuery/ProductPriceAndAvailabilityQuery/</span></span>  
    >   
    >  <span data-ttu-id="998f8-129">ProductPriceAndAvailability/ProductLineItem/productUnit/</span><span class="sxs-lookup"><span data-stu-id="998f8-129">ProductPriceAndAvailability/ProductLineItem/productUnit/</span></span>  
    >   
    >  <span data-ttu-id="998f8-130">ProductPackageDescription あります。</span><span class="sxs-lookup"><span data-stu-id="998f8-130">ProductPackageDescription/ProductIdentification.</span></span>  
  
4.  <span data-ttu-id="998f8-131">**ファイル** メニューのをクリックして**すべて保存**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="998f8-131">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="998f8-132">参照</span><span class="sxs-lookup"><span data-stu-id="998f8-132">See Also</span></span>  
 [<span data-ttu-id="998f8-133">Contoso の BizTalk ポートの作成と構成</span><span class="sxs-lookup"><span data-stu-id="998f8-133">Creating and Configuring BizTalk Ports for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)