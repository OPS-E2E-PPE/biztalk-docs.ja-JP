---
title: レッスン 2:ビジネス ルールの作成ツールを使用して、展開の確認 |Microsoft Docs
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
ms.openlocfilehash: eee5d380c47d429f5a09343b6157cdeab8e5fba6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530368"
---
# <a name="lesson-2-confirming-the-deployment-using-the-business-rule-composer-tool"></a><span data-ttu-id="0da23-102">レッスン 2:展開をビジネス ルール作成ツールを使用して確認します。</span><span class="sxs-lookup"><span data-stu-id="0da23-102">Lesson 2: Confirming the Deployment Using the Business Rule Composer Tool</span></span>
<span data-ttu-id="0da23-103">このレッスンでは、ビジネス ルール作成ツールは、ボキャブラリを作成し、ポリシーの展開を確認します。</span><span class="sxs-lookup"><span data-stu-id="0da23-103">In this lesson, you confirm that the Business Rule Composer tool created your vocabularies and deployed your policies.</span></span> <span data-ttu-id="0da23-104">ボキャブラリは、ルールの合成で使用するボキャブラリ要素のコレクションです。</span><span class="sxs-lookup"><span data-stu-id="0da23-104">A vocabulary is a collection of vocabulary elements you use in rule composition.</span></span> <span data-ttu-id="0da23-105">ポリシーとはバージョン管理されたビジネス ルールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="0da23-105">A policy is a versioned collection of business rules.</span></span>  
  
### <a name="to-confirm-the-deployment-using-the-business-rule-composer-tool"></a><span data-ttu-id="0da23-106">ビジネス ルール作成ツールを使用して、展開を確認するには</span><span class="sxs-lookup"><span data-stu-id="0da23-106">To confirm the deployment using the Business Rule Composer tool</span></span>  
  
1.  <span data-ttu-id="0da23-107">開始**ビジネス ルール作成ツール**BizTalk Server でします。</span><span class="sxs-lookup"><span data-stu-id="0da23-107">Start **Business Rule Composer** in BizTalk Server.</span></span>  
  
2.  <span data-ttu-id="0da23-108">[ルール ストアを開く] ダイアログ ボックスで、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="0da23-108">In the Open Rule Store dialog box, click **OK**.</span></span>  
  
3.  <span data-ttu-id="0da23-109">ビジネス ルール作成ツールのファクト エクスプローラ ペインでを確認、ファクト エクスプ ローラーに必要なボキャブラリが表示されること、次の図に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="0da23-109">In the Facts Explorer pane of the Business Rule Composer tool, confirm that the vocabularies you want appear in the Facts Explorer, as shown in the following figure.</span></span>  
  
     <span data-ttu-id="0da23-110">![](../../adapters-and-accelerators/accelerator-swift/media/tut2-scrn2.gif "Tut2_scrn2")</span><span class="sxs-lookup"><span data-stu-id="0da23-110">![](../../adapters-and-accelerators/accelerator-swift/media/tut2-scrn2.gif "Tut2_scrn2")</span></span>  
  
4.  <span data-ttu-id="0da23-111">ポリシー エクスプ ローラーでは、ビジネス ルール作成ツールで、次のポリシーが展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0da23-111">In the Policy Explorer, confirm that the Business Rule Composer tool deployed the following policies:</span></span>  
  
     <span data-ttu-id="0da23-112">MT103_Master_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-112">MT103_Master_Policy</span></span>  
  
     <span data-ttu-id="0da23-113">MT103_Validation_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-113">MT103_Validation_Policy</span></span>  
  
     <span data-ttu-id="0da23-114">SWIFT_NetworkRule149_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-114">SWIFT_NetworkRule149_Policy</span></span>  
  
     <span data-ttu-id="0da23-115">SWIFT_NetworkRule150_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-115">SWIFT_NetworkRule150_Policy</span></span>  
  
     <span data-ttu-id="0da23-116">SWIFT_NetworkRule151_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-116">SWIFT_NetworkRule151_Policy</span></span>  
  
     <span data-ttu-id="0da23-117">SWIFT_NetworkRule175_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-117">SWIFT_NetworkRule175_Policy</span></span>  
  
     <span data-ttu-id="0da23-118">SWIFT_NetworkRule2_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-118">SWIFT_NetworkRule2_Policy</span></span>  
  
     <span data-ttu-id="0da23-119">SWIFT_NetworkRule201_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-119">SWIFT_NetworkRule201_Policy</span></span>  
  
     <span data-ttu-id="0da23-120">SWIFT_NetworkRule202_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-120">SWIFT_NetworkRule202_Policy</span></span>  
  
     <span data-ttu-id="0da23-121">SWIFT_NetworkRule203_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-121">SWIFT_NetworkRule203_Policy</span></span>  
  
     <span data-ttu-id="0da23-122">SWIFT_NetworkRule204_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-122">SWIFT_NetworkRule204_Policy</span></span>  
  
     <span data-ttu-id="0da23-123">SWIFT_NetworkRule205_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-123">SWIFT_NetworkRule205_Policy</span></span>  
  
     <span data-ttu-id="0da23-124">SWIFT_NetworkRule206_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-124">SWIFT_NetworkRule206_Policy</span></span>  
  
     <span data-ttu-id="0da23-125">SWIFT_NetworkRule207_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-125">SWIFT_NetworkRule207_Policy</span></span>  
  
     <span data-ttu-id="0da23-126">SWIFT_NetworkRule209_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-126">SWIFT_NetworkRule209_Policy</span></span>  
  
     <span data-ttu-id="0da23-127">SWIFT_NetworkRule210_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-127">SWIFT_NetworkRule210_Policy</span></span>  
  
     <span data-ttu-id="0da23-128">SWIFT_NetworkRule212_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-128">SWIFT_NetworkRule212_Policy</span></span>  
  
     <span data-ttu-id="0da23-129">SWIFT_NetworkRule213_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-129">SWIFT_NetworkRule213_Policy</span></span>  
  
     <span data-ttu-id="0da23-130">SWIFT_NetworkRule215_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-130">SWIFT_NetworkRule215_Policy</span></span>  
  
     <span data-ttu-id="0da23-131">SWIFT_NetworkRule216_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-131">SWIFT_NetworkRule216_Policy</span></span>  
  
     <span data-ttu-id="0da23-132">SWIFT_NetworkRule217_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-132">SWIFT_NetworkRule217_Policy</span></span>  
  
     <span data-ttu-id="0da23-133">SWIFT_NetworkRule218_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-133">SWIFT_NetworkRule218_Policy</span></span>  
  
     <span data-ttu-id="0da23-134">SWIFT_NetworkRule244_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-134">SWIFT_NetworkRule244_Policy</span></span>  
  
     <span data-ttu-id="0da23-135">SWIFT_NetworkRule245_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-135">SWIFT_NetworkRule245_Policy</span></span>  
  
     <span data-ttu-id="0da23-136">SWIFT_NetworkRule81_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-136">SWIFT_NetworkRule81_Policy</span></span>  
  
     <span data-ttu-id="0da23-137">SWIFT_PartyIdentifier_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-137">SWIFT_PartyIdentifier_Policy</span></span>  
  
     <span data-ttu-id="0da23-138">SWIFT_Reference_Policy</span><span class="sxs-lookup"><span data-stu-id="0da23-138">SWIFT_Reference_Policy</span></span>  
  
### <a name="to-view-a-policy"></a><span data-ttu-id="0da23-139">ポリシーを表示するには</span><span class="sxs-lookup"><span data-stu-id="0da23-139">To view a policy</span></span>  
  
1. <span data-ttu-id="0da23-140">ビジネス ルール作成ツールの [ポリシー エクスプ ローラー] ウィンドウで、 **SWIFT_NetworkRule149_Policy**を展開し、展開、**バージョン 1.0-展開済み**ノード。</span><span class="sxs-lookup"><span data-stu-id="0da23-140">In the Policy Explorer pane of the Business Rules Composer, ensure that the **SWIFT_NetworkRule149_Policy** is expanded, and then expand the **Version 1.0 – Deployed** node.</span></span>  
  
2. <span data-ttu-id="0da23-141">ダブルクリックして、 **Validate_MT103**ノードを開きます。</span><span class="sxs-lookup"><span data-stu-id="0da23-141">Double-click the **Validate_MT103** node to open it.</span></span>  
  
    <span data-ttu-id="0da23-142">ポリシーは、画面の右側にあるエディター ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="0da23-142">The policy opens in the editor pane on the right side of the screen.</span></span>  
  
   <span data-ttu-id="0da23-143">続行する[モジュール 7。有効なフラット ファイル インスタンスをテスト](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md)します。</span><span class="sxs-lookup"><span data-stu-id="0da23-143">Proceed to [Module 7: Testing a Valid Flat File Instance](../../adapters-and-accelerators/accelerator-swift/module-7-testing-a-valid-flat-file-instance.md).</span></span>