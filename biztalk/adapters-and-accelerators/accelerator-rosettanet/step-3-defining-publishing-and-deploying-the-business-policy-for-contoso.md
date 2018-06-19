---
title: '手順 3: 定義する、発行、および Contoso のビジネス ポリシーを展開する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deploying
- policies, publishing
- private process tutorial, creating policies
- policies, creating
ms.assetid: 529b16d8-226b-4046-a95d-64162ebd59a3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbdd1133145aada8b1a1abf0ccdde25547b7fed3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210666"
---
# <a name="step-3-defining-publishing-and-deploying-the-business-policy-for-contoso"></a><span data-ttu-id="99c59-102">手順 3: を定義する、発行、および Contoso のビジネス ポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="99c59-102">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>
<span data-ttu-id="99c59-103">ここでは、緊急時に使用するために、Contoso が製造する各製品を決められた数量だけ取っておくビジネス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="99c59-103">In this step, you create a business policy that reserves a set quantity of units for each product that Contoso manufactures to be used in case of an emergency.</span></span>  
  
### <a name="to-add-a-new-policy"></a><span data-ttu-id="99c59-104">新しいポリシーを追加するには</span><span class="sxs-lookup"><span data-stu-id="99c59-104">To add a new policy</span></span>  
  
1.  <span data-ttu-id="99c59-105">ポリシー エクスプローラ ペインで、ビジネス ルール作成ツールで右クリック**ポリシー**、クリックして**新しいポリシーの追加**です。</span><span class="sxs-lookup"><span data-stu-id="99c59-105">In the Business Rule Composer, in the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
2.  <span data-ttu-id="99c59-106">新しいポリシーの名前**3 a2priceavailabilitypolicy**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="99c59-106">Name the new policy **3A2PriceAvailabilityPolicy**, and then press **Enter**.</span></span>  
  
### <a name="to-add-a-policy-rule-to-enforce-the-emergency-quantity-needs"></a><span data-ttu-id="99c59-107">緊急時の必要数量を決定するポリシー ルールを追加するには</span><span class="sxs-lookup"><span data-stu-id="99c59-107">To add a policy rule to enforce the emergency quantity needs</span></span>  
  
1.  <span data-ttu-id="99c59-108">右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilitypolicy**、クリックして**新しいルールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="99c59-108">Right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityPolicy**, and then click **Add New Rule**.</span></span>  
  
2.  <span data-ttu-id="99c59-109">ルールの名前として**Quantity Exhausted Emergency Supply Rule -**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="99c59-109">Name the rule **Emergency Supply Rule - Quantity Exhausted**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="99c59-110">右側のウィンドウで、ビジネス ルール作成ツールで右クリック**条件**IF ペインで、をポイント**述語**、をクリックし、**以下**述語。</span><span class="sxs-lookup"><span data-stu-id="99c59-110">In the Business Rule Composer, in the right pane, right-click **Conditions** under the IF pane, point to **Predicates**, and then click the **Less than equal** predicate.</span></span>  
  
4.  <span data-ttu-id="99c59-111">ファクト エクスプ ローラー ウィンドウで **ボキャブラリ**、展開**3 a2priceavailabilityvocabulary**、展開**バージョン 1.0 - 公開済み****数量使用可能な**、上にドラッグし、`argument1`作成ツール画面上のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="99c59-111">In the Facts Explorer pane, expand **Vocabularies**, expand **3A2PriceAvailabilityVocabulary**, expand **Version 1.0 - Published**, select **Quantity Available**, and drag it onto the `argument1` placeholder on the composer surface.</span></span>  
  
5.  <span data-ttu-id="99c59-112">手順 4 をドラッグして**Emergency Quantity Needed**上に、`argument2`プレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="99c59-112">Repeat step 4 by dragging **Emergency Quantity Needed** onto the `argument2` placeholder.</span></span>  
  
6.  <span data-ttu-id="99c59-113">選択**Final Quantity Available**にドラッグ**アクション**[THEN] ペインでします。</span><span class="sxs-lookup"><span data-stu-id="99c59-113">Select **Final Quantity Available**, and then drag it onto **Actions** in the THEN pane.</span></span>  
  
### <a name="to-add-a-policy-to-revise-the-number-available-field-in-the-response"></a><span data-ttu-id="99c59-114">必要に応じて [Number Available] フィールドを修正するポリシーを追加するには</span><span class="sxs-lookup"><span data-stu-id="99c59-114">To add a policy to revise the Number Available field in the response</span></span>  
  
1.  <span data-ttu-id="99c59-115">右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilitypolicy**、クリックして**新しいルールの追加**です。</span><span class="sxs-lookup"><span data-stu-id="99c59-115">Right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityPolicy**, and then click **Add New Rule**.</span></span>  
  
2.  <span data-ttu-id="99c59-116">ルールの名前として**Emergency Supply Rule - Quantity Available**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="99c59-116">Name the new rule **Emergency Supply Rule - Quantity Available**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="99c59-117">右側のウィンドウで、ビジネス ルール作成ツールで右クリック**条件**IF ペインで、をポイント**述語**、をクリックし、**より大きい**述語。</span><span class="sxs-lookup"><span data-stu-id="99c59-117">In the Business Rule Composer, in the right pane, right click **Conditions** under the IF pane, point to **Predicates**, and then click the **Greater than** predicate.</span></span>  
  
4.  <span data-ttu-id="99c59-118">ファクト エクスプ ローラー ウィンドウで **ボキャブラリ**、展開**3 a2priceavailabilityvocabulary**、展開**バージョン 1.0 - 公開済み****数量使用可能な**、上にドラッグし、`argument1`作成ツール画面上のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="99c59-118">In the Facts Explorer pane, expand **Vocabularies**, expand **3A2PriceAvailabilityVocabulary**, expand **Version 1.0 - Published**, select **Quantity Available**, and then drag it onto the `argument1` placeholder on the composer surface.</span></span>  
  
5.  <span data-ttu-id="99c59-119">ドラッグして、その同じ手順を繰り返します**Emergency Quantity Needed**上に、`argument2`プレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="99c59-119">Repeat that same step by dragging **Emergency Quantity Needed** onto the `argument2` placeholder.</span></span>  
  
6.  <span data-ttu-id="99c59-120">選択**Final Quantity Available**にドラッグ**アクション**[THEN] ペインでします。</span><span class="sxs-lookup"><span data-stu-id="99c59-120">Select **Final Quantity Available**, and then drag it onto **Actions** in the THEN pane.</span></span>  
  
7.  <span data-ttu-id="99c59-121">ファクト エクスプ ローラー ウィンドウで **バージョン 1.0 - 公開済み****関数**、ドラッグ、`Subtract`関数、 **0**隣にある引数**Final Quantity Available** THEN ペインでします。</span><span class="sxs-lookup"><span data-stu-id="99c59-121">In the Facts Explorer pane, expand **Version 1.0 - Published** under **Functions**, and drag the `Subtract` function onto the **0** argument next to **Final Quantity Available** in the THEN pane.</span></span>  
  
8.  <span data-ttu-id="99c59-122">ドラッグ**Quantity Available** ( **3 a2priceavailabilityvocabulary**) にドロップし、 `value1` THEN ペイン内のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="99c59-122">Drag **Quantity Available** (under **3A2PriceAvailabilityVocabulary**) and drop it on the `value1` placeholder in the THEN pane.</span></span>  
  
9. <span data-ttu-id="99c59-123">ドラッグ**Emergency Quantity Needed**、上にドロップし、 `value2` [THEN] ペイン内のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="99c59-123">Drag **Emergency Quantity Needed**, and drop it on the `value2` placeholder in the THEN pane.</span></span>  
  
### <a name="to-save-publish-and-deploy-the-business-policy"></a><span data-ttu-id="99c59-124">ビジネス ポリシーの保存、公開、展開を行うには</span><span class="sxs-lookup"><span data-stu-id="99c59-124">To save, publish, and deploy the business policy</span></span>  
  
1.  <span data-ttu-id="99c59-125">ポリシー エクスプローラ ペインで右クリック**バージョン 1.0 (未保存)**  **3 a2priceavailabilitypolicy**をクリックし、**保存**です。</span><span class="sxs-lookup"><span data-stu-id="99c59-125">In the Policy Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityPolicy**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="99c59-126">その同じノードを右クリックし、をクリックして**発行**です。</span><span class="sxs-lookup"><span data-stu-id="99c59-126">Right-click that same node, and then click **Publish**.</span></span>  
  
3.  <span data-ttu-id="99c59-127">その同じノードを右クリックし、をクリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="99c59-127">Right-click that same node, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c59-128">参照</span><span class="sxs-lookup"><span data-stu-id="99c59-128">See Also</span></span>  
 [<span data-ttu-id="99c59-129">手順 4: HeaderHelper プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="99c59-129">Step 4: Creating the HeaderHelper Project</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)