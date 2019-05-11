---
title: 手順 2:定義と Contoso のボキャブラリを公開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- vocabularies, creating
- vocabularies, publishing
- private process tutorial, creating vocabularies
ms.assetid: e23880c0-772c-48c6-a6b5-32eb951527c8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e30d20064f322b88abc27f6adb1a59d4825c56a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281141"
---
# <a name="step-2-defining-and-publishing-the-vocabulary-for-contoso"></a><span data-ttu-id="5d021-102">手順 2:定義と Contoso のボキャブラリを公開</span><span class="sxs-lookup"><span data-stu-id="5d021-102">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>
<span data-ttu-id="5d021-103">このシナリオでは、Contoso は、そのインベントリは手の形で常に、緊急事態が発生した場合ことを確認するビジネス ポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="5d021-103">In this scenario, Contoso implements a business policy that makes sure that inventory is always on hand if an emergency occurs.</span></span> <span data-ttu-id="5d021-104">ビジネス ルール作成ツールを使用してビジネス ポリシーを作成する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="5d021-104">You create business policies using the Business Rule Composer in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5d021-105">この手順では、ビジネス ポリシーを定義するときに使用するボキャブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d021-105">In this step, you create the vocabulary to use when you define the business policy.</span></span>  
  
### <a name="to-add-a-new-vocabulary"></a><span data-ttu-id="5d021-106">新しいボキャブラリを追加するには</span><span class="sxs-lookup"><span data-stu-id="5d021-106">To add a new vocabulary</span></span>  
  
1. <span data-ttu-id="5d021-107">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**ビジネス ルール作成ツール**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-107">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
2. <span data-ttu-id="5d021-108">[ルール ストアを開く] ダイアログ ボックスで、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-108">In the Open Rule Store dialog box, click **OK**.</span></span>  
  
3. <span data-ttu-id="5d021-109">ファクト エクスプローラ ペインでの**ボキャブラリ** タブで、右クリック**ボキャブラリ**、 をクリックし、**新しいボキャブラリの追加**。</span><span class="sxs-lookup"><span data-stu-id="5d021-109">In the Facts Explorer pane, on the **Vocabularies** tab, right-click **Vocabularies**, and then click **Add New Vocabulary**.</span></span>  
  
4. <span data-ttu-id="5d021-110">ボキャブラリの名前**3 a2priceavailabilityvocabulary**、およびキーを押します**Enter**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-110">Name the vocabulary **3A2PriceAvailabilityVocabulary**, and then press **Enter**.</span></span>  
  
### <a name="to-define-a-constant-vocabulary-value"></a><span data-ttu-id="5d021-111">ボキャブラリの定数値を定義するには</span><span class="sxs-lookup"><span data-stu-id="5d021-111">To define a constant vocabulary value</span></span>  
  
1.  <span data-ttu-id="5d021-112">ビジネス ルール作成ツール をクリックして**3 a2priceavailabilityvocabulary**、右クリック**バージョン 1.0 (未保存)**、 をクリックし、**新しい定義の追加**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-112">In Business Rule Composer, click **3A2PriceAvailabilityVocabulary**, right-click **Version 1.0(not saved)**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="5d021-113">**ボキャブラリの定義ウィザード**] ページで、[**定数値、値の範囲、または値セットの**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-113">On the **Vocabulary Definition Wizard** page, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="5d021-114">**定数値、値の範囲、または値セットの** ページの 、**定義名**ボックスに「 **Emergency Quantity Needed**、 をクリックし、 **次へ**.</span><span class="sxs-lookup"><span data-stu-id="5d021-114">On the **Constant Value, Range of Values, or Set of Values** page, in the **Definition name** box, type **Emergency Quantity Needed**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="5d021-115">**定数値の定義**] ページの [、**値**ボックスに「 **800**、順にクリックします**完了**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-115">On the **Define a Constant Value** page, in the **Value** box, type **800**, and then click **Finish**.</span></span>  
  
### <a name="to-define-an-xml-document-get-element"></a><span data-ttu-id="5d021-116">XML ドキュメントの 'Get' 要素を定義するには</span><span class="sxs-lookup"><span data-stu-id="5d021-116">To define an XML document 'Get' element</span></span>  
  
1.  <span data-ttu-id="5d021-117">ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)** [ **3 a2priceavailabilityvocabulary**、] をクリックし、**新しい定義の追加**.</span><span class="sxs-lookup"><span data-stu-id="5d021-117">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="5d021-118">**VocabularyDefinition ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-118">On the **VocabularyDefinition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="5d021-119">**XML ドキュメントの要素または属性**ページで、**定義名**ボックスに「 **Quantity Available**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-119">On the **XML Document Element or Attribute** page, in the **Definition Name** box, type **Quantity Available**.</span></span>  
  
4.  <span data-ttu-id="5d021-120">をクリックして**参照**(横に、**スキーマ**フィールド)、移動、 **[contosopriceandavailability]** 選択、ソリューション フォルダー内のプロジェクト、 **ContosoPriceAndAvailability.xsd**スキーマ、およびクリック**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-120">Click **Browse** (next to the **Schema** field), move to the **ContosoPriceAndAvailability** project in your solution folder, select the **ContosoPriceAndAvailability.xsd** schema, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="5d021-121">バインドの選択 ダイアログ ボックスで、 **rootPriceResponse**、展開**製品**を選択、 **NumberAvailable**要素、およびクリック**ok**.</span><span class="sxs-lookup"><span data-stu-id="5d021-121">In the Select Binding dialog box, expand **rootPriceResponse**, expand **Products**, select the **NumberAvailable** element, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="5d021-122">**XML ドキュメントの要素または属性**ページで、**ドキュメントの種類**ボックスに、値があることを確認**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span><span class="sxs-lookup"><span data-stu-id="5d021-122">On the **XML Document Element or Attribute** page, in the **Document Type** box, ensure that the value is **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span></span>  
  
7.  <span data-ttu-id="5d021-123">**操作を選択して**セクションで、選択 **「取得」操作の実行**、順にクリックします**完了**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-123">In the **Select operation** section, select **Perform "Get" Operation**, and then click **Finish**.</span></span>  
  
### <a name="to-define-an-xml-document-set-element"></a><span data-ttu-id="5d021-124">XML ドキュメントの 'Set' 要素を定義するには</span><span class="sxs-lookup"><span data-stu-id="5d021-124">To define an XML document 'Set' element</span></span>  
  
1.  <span data-ttu-id="5d021-125">ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)** [ **3 a2priceavailabilityvocabulary**、] をクリックし、**新しい定義の追加**.</span><span class="sxs-lookup"><span data-stu-id="5d021-125">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="5d021-126">**VocabularyDefinition ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリックします**次**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-126">On the **VocabularyDefinition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="5d021-127">**XML ドキュメントの要素または属性**ページで、**定義名**ボックスに「 **Final Quantity Available**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-127">On the **XML Document Element or Attribute** page, in the **Definition Name** box, type **Final Quantity Available**.</span></span>  
  
4.  <span data-ttu-id="5d021-128">をクリックして**参照**(横に、**スキーマ**フィールド)、移動、 **[contosopriceandavailability]** 選択、ソリューション フォルダー内のプロジェクト、 **ContosoPriceAndAvailability.xsd**スキーマ、およびクリック**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-128">Click **Browse** (next to the **Schema** field), move to the **ContosoPriceAndAvailability** project in your solution folder, select the **ContosoPriceAndAvailability.xsd** schema, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="5d021-129">**バインドの選択** ダイアログ ボックスで、展開**rootPriceResponse**、展開**製品**を選び、 **NumberAvailable**要素。</span><span class="sxs-lookup"><span data-stu-id="5d021-129">In the **Select Binding** dialog box, expand **rootPriceResponse**, expand **Products**, and then select the **NumberAvailable** element.</span></span> <span data-ttu-id="5d021-130">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d021-130">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="5d021-131">**XML ドキュメントの要素または属性**ページで、**ドキュメントの種類**ボックスに、値があることを確認**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span><span class="sxs-lookup"><span data-stu-id="5d021-131">On the **XML Document Element or Attribute** page, in the **Document Type** box, ensure that the value is **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span></span>  
  
7.  <span data-ttu-id="5d021-132">**操作を選択して**セクションで、選択 **「設定」操作を実行する**、順にクリックします **[次へ]** します。</span><span class="sxs-lookup"><span data-stu-id="5d021-132">In the **Select operation** section, select **Perform "Set" Operation**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="5d021-133">**表示名を指定**] ページで [**完了**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-133">In the **Specify the Display Name** page, click **Finish**.</span></span>  
  
### <a name="to-save-and-publish-the-vocabulary"></a><span data-ttu-id="5d021-134">ボキャブラリを保存および公開するには</span><span class="sxs-lookup"><span data-stu-id="5d021-134">To save and publish the vocabulary</span></span>  
  
1.  <span data-ttu-id="5d021-135">ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)** [ **3 a2priceavailabilityvocabulary**、] をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-135">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="5d021-136">右クリックしてその同じ**バージョン 1.0**ノードをクリック**発行**します。</span><span class="sxs-lookup"><span data-stu-id="5d021-136">Right-click that same **Version 1.0** node and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5d021-137">ビジネス ルール作成ツールを開いたままに、次の手順、チュートリアルでは。</span><span class="sxs-lookup"><span data-stu-id="5d021-137">Leave the Business Rule Composer open for the next step in the tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d021-138">参照</span><span class="sxs-lookup"><span data-stu-id="5d021-138">See Also</span></span>  
 [<span data-ttu-id="5d021-139">ステップ 3:Contoso のビジネス ポリシーの定義、公開、展開</span><span class="sxs-lookup"><span data-stu-id="5d021-139">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)