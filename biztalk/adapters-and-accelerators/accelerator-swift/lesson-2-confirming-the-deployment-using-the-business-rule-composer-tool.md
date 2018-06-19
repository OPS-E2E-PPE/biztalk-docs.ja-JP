---
title: 'レッスン 2: ビジネス ルール作成ツールを使用して、展開を確認する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, verifying
- verifying, business rules
- verifying, Business Rule Composer tool
- business rules, Business Rule Composer tool
- Business Rule Composer tool
ms.assetid: 337dc469-cf9e-406b-90ae-0f580b17d7c9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3115dc425fedca9019f0e5e5171f7234e6fbdbb2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210242"
---
# <a name="lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool"></a><span data-ttu-id="d124c-102">レッスン 2: ビジネス ルール作成ツールを使用して、展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="d124c-102">Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool</span></span>
<span data-ttu-id="d124c-103">このレッスンでは、ビジネス ルール作成ツールが、ボキャブラリを作成し、ポリシーを配置したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d124c-103">In this lesson, you confirm that the Business Rule Composer tool created your vocabularies and deployed your policies.</span></span> <span data-ttu-id="d124c-104">ボキャブラリは、ルールを作成で使用するボキャブラリ要素のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d124c-104">A vocabulary is a collection of vocabulary elements you use in rule composition.</span></span> <span data-ttu-id="d124c-105">ポリシーとはバージョン管理されたビジネス ルールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d124c-105">A policy is a versioned collection of business rules.</span></span>  
  
### <a name="to-confirm-the-deployment-using-the-business-rule-composer-tool"></a><span data-ttu-id="d124c-106">ビジネス ルール作成ツールを使用して、展開を確認するには</span><span class="sxs-lookup"><span data-stu-id="d124c-106">To confirm the deployment using the Business Rule Composer tool</span></span>  
  
1.  <span data-ttu-id="d124c-107">開始**ビジネス ルール作成ツール**BizTalk Server でします。</span><span class="sxs-lookup"><span data-stu-id="d124c-107">Start **Business Rule Composer** in BizTalk Server.</span></span>  
  
2.  <span data-ttu-id="d124c-108">[ルール ストアを開く] ダイアログ ボックスで、 **OK**です。</span><span class="sxs-lookup"><span data-stu-id="d124c-108">In the Open Rule Store dialog box, click **OK**.</span></span>  
  
3.  <span data-ttu-id="d124c-109">ファクト エクスプ ローラーのウィンドウで、ビジネス ルール作成ツール、確認、ファクト エクスプ ローラーに必要なボキャブラリが表示されている次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="d124c-109">In the Facts Explorer pane of the Business Rule Composer tool, confirm that the vocabularies you want appear in the Facts Explorer, as shown in the following figure.</span></span>  
  
     ![](../../adapters-and-accelerators/accelerator-swift/media/tut2-scrn2.gif "Tut2_scrn2")  
  
4.  <span data-ttu-id="d124c-110">ポリシー エクスプ ローラーで、ビジネス ルール作成ツールには次のポリシーが展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d124c-110">In the Policy Explorer, confirm that the Business Rule Composer tool deployed the following policies:</span></span>  
  
     <span data-ttu-id="d124c-111">MT103_Master_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-111">MT103_Master_Policy</span></span>  
  
     <span data-ttu-id="d124c-112">MT103_Validation_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-112">MT103_Validation_Policy</span></span>  
  
     <span data-ttu-id="d124c-113">SWIFT_NetworkRule149_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-113">SWIFT_NetworkRule149_Policy</span></span>  
  
     <span data-ttu-id="d124c-114">SWIFT_NetworkRule150_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-114">SWIFT_NetworkRule150_Policy</span></span>  
  
     <span data-ttu-id="d124c-115">SWIFT_NetworkRule151_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-115">SWIFT_NetworkRule151_Policy</span></span>  
  
     <span data-ttu-id="d124c-116">SWIFT_NetworkRule175_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-116">SWIFT_NetworkRule175_Policy</span></span>  
  
     <span data-ttu-id="d124c-117">SWIFT_NetworkRule2_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-117">SWIFT_NetworkRule2_Policy</span></span>  
  
     <span data-ttu-id="d124c-118">SWIFT_NetworkRule201_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-118">SWIFT_NetworkRule201_Policy</span></span>  
  
     <span data-ttu-id="d124c-119">SWIFT_NetworkRule202_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-119">SWIFT_NetworkRule202_Policy</span></span>  
  
     <span data-ttu-id="d124c-120">SWIFT_NetworkRule203_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-120">SWIFT_NetworkRule203_Policy</span></span>  
  
     <span data-ttu-id="d124c-121">SWIFT_NetworkRule204_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-121">SWIFT_NetworkRule204_Policy</span></span>  
  
     <span data-ttu-id="d124c-122">SWIFT_NetworkRule205_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-122">SWIFT_NetworkRule205_Policy</span></span>  
  
     <span data-ttu-id="d124c-123">SWIFT_NetworkRule206_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-123">SWIFT_NetworkRule206_Policy</span></span>  
  
     <span data-ttu-id="d124c-124">SWIFT_NetworkRule207_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-124">SWIFT_NetworkRule207_Policy</span></span>  
  
     <span data-ttu-id="d124c-125">SWIFT_NetworkRule209_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-125">SWIFT_NetworkRule209_Policy</span></span>  
  
     <span data-ttu-id="d124c-126">SWIFT_NetworkRule210_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-126">SWIFT_NetworkRule210_Policy</span></span>  
  
     <span data-ttu-id="d124c-127">SWIFT_NetworkRule212_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-127">SWIFT_NetworkRule212_Policy</span></span>  
  
     <span data-ttu-id="d124c-128">SWIFT_NetworkRule213_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-128">SWIFT_NetworkRule213_Policy</span></span>  
  
     <span data-ttu-id="d124c-129">SWIFT_NetworkRule215_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-129">SWIFT_NetworkRule215_Policy</span></span>  
  
     <span data-ttu-id="d124c-130">SWIFT_NetworkRule216_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-130">SWIFT_NetworkRule216_Policy</span></span>  
  
     <span data-ttu-id="d124c-131">SWIFT_NetworkRule217_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-131">SWIFT_NetworkRule217_Policy</span></span>  
  
     <span data-ttu-id="d124c-132">SWIFT_NetworkRule218_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-132">SWIFT_NetworkRule218_Policy</span></span>  
  
     <span data-ttu-id="d124c-133">SWIFT_NetworkRule244_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-133">SWIFT_NetworkRule244_Policy</span></span>  
  
     <span data-ttu-id="d124c-134">SWIFT_NetworkRule245_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-134">SWIFT_NetworkRule245_Policy</span></span>  
  
     <span data-ttu-id="d124c-135">SWIFT_NetworkRule81_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-135">SWIFT_NetworkRule81_Policy</span></span>  
  
     <span data-ttu-id="d124c-136">SWIFT_PartyIdentifier_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-136">SWIFT_PartyIdentifier_Policy</span></span>  
  
     <span data-ttu-id="d124c-137">SWIFT_Reference_Policy</span><span class="sxs-lookup"><span data-stu-id="d124c-137">SWIFT_Reference_Policy</span></span>  
  
### <a name="to-view-a-policy"></a><span data-ttu-id="d124c-138">ポリシーを表示するには</span><span class="sxs-lookup"><span data-stu-id="d124c-138">To view a policy</span></span>  
  
1.  <span data-ttu-id="d124c-139">ビジネス ルール作成ツールの [ポリシー エクスプ ローラー] ウィンドウでいることを確認、 **SWIFT_NetworkRule149_Policy**が展開され、順に展開、**バージョン 1.0-展開済み**ノード。</span><span class="sxs-lookup"><span data-stu-id="d124c-139">In the Policy Explorer pane of the Business Rules Composer, ensure that the **SWIFT_NetworkRule149_Policy** is expanded, and then expand the **Version 1.0 – Deployed** node.</span></span>  
  
2.  <span data-ttu-id="d124c-140">ダブルクリックして、 **Validate_MT103**ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="d124c-140">Double-click the **Validate_MT103** node to open it.</span></span>  
  
     <span data-ttu-id="d124c-141">ポリシーは、画面の右側にある、エディター ウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="d124c-141">The policy opens in the editor pane on the right side of the screen.</span></span>  
  
 <span data-ttu-id="d124c-142">進みます[第 7 章: テストの有効なフラット ファイル インスタンス](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md)です。</span><span class="sxs-lookup"><span data-stu-id="d124c-142">Proceed to [Module 7: Testing a Valid Flat File Instance](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md).</span></span>