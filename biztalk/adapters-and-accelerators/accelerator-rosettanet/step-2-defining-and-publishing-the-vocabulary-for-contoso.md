---
title: '手順 2: の定義と Contoso のボキャブラリを公開 |Microsoft ドキュメント'
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
ms.openlocfilehash: 15937a1235cc1776be38fe2b0e5529c19d3f6fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211090"
---
# <a name="step-2-defining-and-publishing-the-vocabulary-for-contoso"></a><span data-ttu-id="d3d87-102">手順 2: の定義と Contoso のボキャブラリを公開</span><span class="sxs-lookup"><span data-stu-id="d3d87-102">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>
<span data-ttu-id="d3d87-103">このシナリオでは、緊急時でもインベントリが確実に利用できる状態にするビジネス ポリシーを Contoso で実装します。</span><span class="sxs-lookup"><span data-stu-id="d3d87-103">In this scenario, Contoso implements a business policy that makes sure that inventory is always on hand if an emergency occurs.</span></span> <span data-ttu-id="d3d87-104">ビジネス ポリシーは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] のビジネス ルール作成ツールを使用して作成します。</span><span class="sxs-lookup"><span data-stu-id="d3d87-104">You create business policies using the Business Rule Composer in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d3d87-105">ここでは、ビジネス ポリシーを定義する際に使用するボキャブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3d87-105">In this step, you create the vocabulary to use when you define the business policy.</span></span>  
  
### <a name="to-add-a-new-vocabulary"></a><span data-ttu-id="d3d87-106">新しいボキャブラリを追加するには</span><span class="sxs-lookup"><span data-stu-id="d3d87-106">To add a new vocabulary</span></span>  
  
1.  <span data-ttu-id="d3d87-107">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**ビジネス ルール作成ツール**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-107">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="d3d87-108">[ルール ストアを開く] ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-108">In the Open Rule Store dialog box, click **OK**.</span></span>  
  
3.  <span data-ttu-id="d3d87-109">ファクト エクスプ ローラー ウィンドウで、上、**ボキャブラリ** タブを右クリックして**ボキャブラリ**、順にクリック**新しいボキャブラリの追加**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-109">In the Facts Explorer pane, on the **Vocabularies** tab, right-click **Vocabularies**, and then click **Add New Vocabulary**.</span></span>  
  
4.  <span data-ttu-id="d3d87-110">ボキャブラリの名前**3 a2priceavailabilityvocabulary**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-110">Name the vocabulary **3A2PriceAvailabilityVocabulary**, and then press **Enter**.</span></span>  
  
### <a name="to-define-a-constant-vocabulary-value"></a><span data-ttu-id="d3d87-111">ボキャブラリの定数値を定義するには</span><span class="sxs-lookup"><span data-stu-id="d3d87-111">To define a constant vocabulary value</span></span>  
  
1.  <span data-ttu-id="d3d87-112">ビジネス ルール作成ツール をクリックして**3 a2priceavailabilityvocabulary**を右クリックして**バージョン 1.0 (未保存)**、クリックして**新しい定義の追加**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-112">In Business Rule Composer, click **3A2PriceAvailabilityVocabulary**, right-click **Version 1.0(not saved)**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="d3d87-113">**ボキャブラリの定義ウィザード**] ページで、[**定数値、値の範囲、または値セット**、クリックして **[次へ]** です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-113">On the **Vocabulary Definition Wizard** page, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="d3d87-114">**定数値、値の範囲、または値セット**] ページの [、**定義名**ボックスに、入力**Emergency Quantity Needed**、クリックして **[次へ]**.</span><span class="sxs-lookup"><span data-stu-id="d3d87-114">On the **Constant Value, Range of Values, or Set of Values** page, in the **Definition name** box, type **Emergency Quantity Needed**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="d3d87-115">**定数値の定義**] ページの [、**値**ボックスに、入力**800**、順にクリック**完了**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-115">On the **Define a Constant Value** page, in the **Value** box, type **800**, and then click **Finish**.</span></span>  
  
### <a name="to-define-an-xml-document-get-element"></a><span data-ttu-id="d3d87-116">XML ドキュメントの "取得" 要素を定義するには</span><span class="sxs-lookup"><span data-stu-id="d3d87-116">To define an XML document 'Get' element</span></span>  
  
1.  <span data-ttu-id="d3d87-117">ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilityvocabulary**、クリックして**新しい定義の追加**.</span><span class="sxs-lookup"><span data-stu-id="d3d87-117">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="d3d87-118">**VocabularyDefinition ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-118">On the **VocabularyDefinition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="d3d87-119">**XML ドキュメントの要素または属性**] ページの [、**定義名**ボックスに、入力**Quantity Available**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-119">On the **XML Document Element or Attribute** page, in the **Definition Name** box, type **Quantity Available**.</span></span>  
  
4.  <span data-ttu-id="d3d87-120">をクリックして**参照**(横に、**スキーマ**フィールド) に移動、 **[contosopriceandavailability]** プロジェクト、ソリューション フォルダーは、select、 **ContosoPriceAndAvailability.xsd**スキーマ、およびクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-120">Click **Browse** (next to the **Schema** field), move to the **ContosoPriceAndAvailability** project in your solution folder, select the **ContosoPriceAndAvailability.xsd** schema, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="d3d87-121">バインドの選択 ダイアログ ボックスで、展開**rootPriceResponse**、展開**製品**を選択、 **numberavailable**要素、およびクリック**ok**.</span><span class="sxs-lookup"><span data-stu-id="d3d87-121">In the Select Binding dialog box, expand **rootPriceResponse**, expand **Products**, select the **NumberAvailable** element, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="d3d87-122">**XML ドキュメントの要素または属性**] ページの [、**ドキュメントの種類**ボックスで、値があることを確認**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span><span class="sxs-lookup"><span data-stu-id="d3d87-122">On the **XML Document Element or Attribute** page, in the **Document Type** box, ensure that the value is **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span></span>  
  
7.  <span data-ttu-id="d3d87-123">**操作を選択して**セクションで、選択 **「取得」操作の実行**、順にクリック**完了**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-123">In the **Select operation** section, select **Perform "Get" Operation**, and then click **Finish**.</span></span>  
  
### <a name="to-define-an-xml-document-set-element"></a><span data-ttu-id="d3d87-124">XML ドキュメントの "設定" 要素を定義するには</span><span class="sxs-lookup"><span data-stu-id="d3d87-124">To define an XML document 'Set' element</span></span>  
  
1.  <span data-ttu-id="d3d87-125">ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilityvocabulary**、クリックして**新しい定義の追加**.</span><span class="sxs-lookup"><span data-stu-id="d3d87-125">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="d3d87-126">**VocabularyDefinition ウィザード**] ページで、[ **XML ドキュメントの要素または属性**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-126">On the **VocabularyDefinition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="d3d87-127">**XML ドキュメントの要素または属性**] ページの [、**定義名**ボックスに、入力**Final Quantity Available**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-127">On the **XML Document Element or Attribute** page, in the **Definition Name** box, type **Final Quantity Available**.</span></span>  
  
4.  <span data-ttu-id="d3d87-128">をクリックして**参照**(横に、**スキーマ**フィールド) に移動、 **[contosopriceandavailability]** プロジェクト、ソリューション フォルダーは、select、 **ContosoPriceAndAvailability.xsd**スキーマ、およびクリック**開く**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-128">Click **Browse** (next to the **Schema** field), move to the **ContosoPriceAndAvailability** project in your solution folder, select the **ContosoPriceAndAvailability.xsd** schema, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="d3d87-129">**バインドの選択** ダイアログ ボックスで、展開**rootpriceresponse**、展開**製品**、クリックして、 **numberavailable**要素。</span><span class="sxs-lookup"><span data-stu-id="d3d87-129">In the **Select Binding** dialog box, expand **rootPriceResponse**, expand **Products**, and then select the **NumberAvailable** element.</span></span> <span data-ttu-id="d3d87-130">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3d87-130">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="d3d87-131">**XML ドキュメントの要素または属性**] ページの [、**ドキュメントの種類**ボックスで、値があることを確認**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span><span class="sxs-lookup"><span data-stu-id="d3d87-131">On the **XML Document Element or Attribute** page, in the **Document Type** box, ensure that the value is **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span></span>  
  
7.  <span data-ttu-id="d3d87-132">**操作を選択**セクションで、選択 **「セット」操作を実行する**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-132">In the **Select operation** section, select **Perform "Set" Operation**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="d3d87-133">**表示名を指定**] ページで [**完了**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-133">In the **Specify the Display Name** page, click **Finish**.</span></span>  
  
### <a name="to-save-and-publish-the-vocabulary"></a><span data-ttu-id="d3d87-134">ボキャブラリを保存および公開するには</span><span class="sxs-lookup"><span data-stu-id="d3d87-134">To save and publish the vocabulary</span></span>  
  
1.  <span data-ttu-id="d3d87-135">ビジネス ルール作成ツールのファクト エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilityvocabulary**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-135">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="d3d87-136">その同じを右クリックして**バージョン 1.0**ノードをクリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="d3d87-136">Right-click that same **Version 1.0** node and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d3d87-137">チュートリアルの次の手順で使用するため、ビジネス ルール作成ツールは開いたままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="d3d87-137">Leave the Business Rule Composer open for the next step in the tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d87-138">参照</span><span class="sxs-lookup"><span data-stu-id="d3d87-138">See Also</span></span>  
 [<span data-ttu-id="d3d87-139">手順 3: を定義する、発行、および Contoso のビジネス ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="d3d87-139">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)