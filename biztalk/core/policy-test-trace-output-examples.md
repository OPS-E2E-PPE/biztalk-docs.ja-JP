---
title: "ポリシー テストのトレース出力例 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, policies
- policies, testing
- testing, examples
ms.assetid: 92e1dc7f-1a8d-41a5-84b6-46d5ad9f2ef2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3678769dffa03bb77c3e86fef02998a354b1fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="policy-test-trace-output-examples"></a><span data-ttu-id="adda6-102">ポリシー テストのトレース出力例</span><span class="sxs-lookup"><span data-stu-id="adda6-102">Policy Test Trace Output Examples</span></span>
<span data-ttu-id="adda6-103">このセクションでは、さまざまな種類のファクトに関するポリシー テストの出力例について説明します。</span><span class="sxs-lookup"><span data-stu-id="adda6-103">This section contains examples of the policy test output for different types of facts.</span></span>  
  
## <a name="net-class"></a><span data-ttu-id="adda6-104">.Net クラス</span><span class="sxs-lookup"><span data-stu-id="adda6-104">.Net Class</span></span>  
 <span data-ttu-id="adda6-105">"LoanProcessing" ポリシーの "TestRule1" ルールの例:</span><span class="sxs-lookup"><span data-stu-id="adda6-105">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF test.get_ID > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="adda6-106">**出力:**</span><span class="sxs-lookup"><span data-stu-id="adda6-106">**Output:**</span></span>  
  
 <span data-ttu-id="adda6-107">ルール セットのルール エンジン トレース: LoanProcessing 2004/3/16 9時 50分: 28 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-107">RULE ENGINE TRACE for RULESET: LoanProcessing 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="adda6-108">ファクト アクティビティ 2004/3/16 9時 50分: 28 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-108">FACT ACTIVITY 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="adda6-109">ルール エンジン インスタンス識別子: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="adda6-109">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="adda6-110">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-110">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-111">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-111">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-112">オブジェクトの種類: MyTest.test</span><span class="sxs-lookup"><span data-stu-id="adda6-112">Object Type: MyTest.test</span></span>  
  
 <span data-ttu-id="adda6-113">オブジェクト インスタンス識別子: 872</span><span class="sxs-lookup"><span data-stu-id="adda6-113">Object Instance Identifier: 872</span></span>  
  
 <span data-ttu-id="adda6-114">条件の評価テスト (一致) 2004/3/16 9時 50分: 28 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-114">CONDITION EVALUATION TEST (MATCH) 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="adda6-115">ルール エンジン インスタンス識別子: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="adda6-115">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="adda6-116">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-116">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-117">テスト式: MyTest.test.get_ID > 0</span><span class="sxs-lookup"><span data-stu-id="adda6-117">Test Expression: MyTest.test.get_ID > 0</span></span>  
  
 <span data-ttu-id="adda6-118">左のオペランド値: 100</span><span class="sxs-lookup"><span data-stu-id="adda6-118">Left Operand Value: 100</span></span>  
  
 <span data-ttu-id="adda6-119">右のオペランド値: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-119">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="adda6-120">テスト結果: True</span><span class="sxs-lookup"><span data-stu-id="adda6-120">Test Result: True</span></span>  
  
 <span data-ttu-id="adda6-121">議題の更新 2004/3/16 9:50:28 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-121">AGENDA UPDATE 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="adda6-122">ルール エンジン インスタンス識別子: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="adda6-122">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="adda6-123">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-123">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-124">操作: 追加</span><span class="sxs-lookup"><span data-stu-id="adda6-124">Operation: Add</span></span>  
  
 <span data-ttu-id="adda6-125">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-125">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-126">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-126">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-127">実行されたルール 2004/3/16 9:50:28 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-127">RULE FIRED 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="adda6-128">ルール エンジン インスタンス識別子: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="adda6-128">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="adda6-129">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-129">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-130">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-130">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-131">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-131">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-132">ファクト アクティビティ 2004/3/16 9時 50分: 28 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-132">FACT ACTIVITY 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="adda6-133">ルール エンジン インスタンス識別子: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="adda6-133">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="adda6-134">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-134">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-135">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-135">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-136">オブジェクトの種類: MyTest.test</span><span class="sxs-lookup"><span data-stu-id="adda6-136">Object Type: MyTest.test</span></span>  
  
 <span data-ttu-id="adda6-137">オブジェクト インスタンス識別子: 872</span><span class="sxs-lookup"><span data-stu-id="adda6-137">Object Instance Identifier: 872</span></span>  
  
## <a name="dataconnectiontypeddatarow"></a><span data-ttu-id="adda6-138">DataConnection/TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="adda6-138">DataConnection/TypedDataRow</span></span>  
 <span data-ttu-id="adda6-139">"LoanProcessing" ポリシーの "TestRule1" ルールの例:</span><span class="sxs-lookup"><span data-stu-id="adda6-139">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="adda6-140">**出力:**</span><span class="sxs-lookup"><span data-stu-id="adda6-140">**Output:**</span></span>  
  
 <span data-ttu-id="adda6-141">ルール セットのルール エンジン トレース: LoanProcessing 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-141">RULE ENGINE TRACE for RULESET: LoanProcessing 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-142">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-142">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-143">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-143">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-144">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-144">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-145">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-145">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-146">オブジェクトの種類: DataConnection:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-146">Object Type: DataConnection:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-147">オブジェクト インスタンス識別子: 874</span><span class="sxs-lookup"><span data-stu-id="adda6-147">Object Instance Identifier: 874</span></span>  
  
 <span data-ttu-id="adda6-148">条件の評価テスト (一致) 2004/3/16 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-148">CONDITION EVALUATION TEST (MATCH) 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-149">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-149">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-150">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-150">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-151">テスト式: 選択 * [CustInfo] から、[CreditCardBalance] > 0</span><span class="sxs-lookup"><span data-stu-id="adda6-151">Test Expression: select * from [CustInfo] where [CreditCardBalance] > 0</span></span>  
  
 <span data-ttu-id="adda6-152">左側のオペランド値: </span><span class="sxs-lookup"><span data-stu-id="adda6-152">Left Operand Value:</span></span>  
  
 <span data-ttu-id="adda6-153">右側のオペランド値: </span><span class="sxs-lookup"><span data-stu-id="adda6-153">Right Operand Value:</span></span>  
  
 <span data-ttu-id="adda6-154">テスト結果: True</span><span class="sxs-lookup"><span data-stu-id="adda6-154">Test Result: True</span></span>  
  
 <span data-ttu-id="adda6-155">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-155">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-156">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-156">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-157">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-157">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-158">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-158">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-159">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-159">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-160">オブジェクト インスタンス識別子: 177556</span><span class="sxs-lookup"><span data-stu-id="adda6-160">Object Instance Identifier: 177556</span></span>  
  
 <span data-ttu-id="adda6-161">議題の更新 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-161">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-162">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-162">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-163">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-163">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-164">操作: 追加</span><span class="sxs-lookup"><span data-stu-id="adda6-164">Operation: Add</span></span>  
  
 <span data-ttu-id="adda6-165">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-165">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-166">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-166">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-167">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-167">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-168">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-168">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-169">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-169">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-170">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-170">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-171">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-171">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-172">オブジェクト インスタンス識別子: 177559</span><span class="sxs-lookup"><span data-stu-id="adda6-172">Object Instance Identifier: 177559</span></span>  
  
 <span data-ttu-id="adda6-173">議題の更新 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-173">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-174">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-174">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-175">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-175">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-176">操作: 追加</span><span class="sxs-lookup"><span data-stu-id="adda6-176">Operation: Add</span></span>  
  
 <span data-ttu-id="adda6-177">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-177">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-178">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-178">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-179">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-179">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-180">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-180">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-181">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-181">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-182">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-182">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-183">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-183">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-184">オブジェクト インスタンス識別子: 177558</span><span class="sxs-lookup"><span data-stu-id="adda6-184">Object Instance Identifier: 177558</span></span>  
  
 <span data-ttu-id="adda6-185">議題の更新 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-185">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-186">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-186">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-187">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-187">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-188">操作: 追加</span><span class="sxs-lookup"><span data-stu-id="adda6-188">Operation: Add</span></span>  
  
 <span data-ttu-id="adda6-189">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-189">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-190">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-190">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-191">2004/3/16 が実行されたルール 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-191">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-192">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-192">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-193">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-193">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-194">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-194">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-195">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-195">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-196">2004/3/16 が実行されたルール 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-196">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-197">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-197">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-198">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-198">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-199">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-199">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-200">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-200">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-201">2004/3/16 が実行されたルール 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-201">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-202">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-202">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-203">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-203">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-204">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-204">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-205">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-205">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-206">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-206">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-207">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-207">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-208">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-208">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-209">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-209">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-210">オブジェクトの種類: DataConnection:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-210">Object Type: DataConnection:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-211">オブジェクト インスタンス識別子: 874</span><span class="sxs-lookup"><span data-stu-id="adda6-211">Object Instance Identifier: 874</span></span>  
  
 <span data-ttu-id="adda6-212">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-212">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-213">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-213">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-214">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-214">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-215">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-215">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-216">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-216">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-217">オブジェクト インスタンス識別子: 177559</span><span class="sxs-lookup"><span data-stu-id="adda6-217">Object Instance Identifier: 177559</span></span>  
  
 <span data-ttu-id="adda6-218">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-218">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-219">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-219">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-220">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-220">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-221">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-221">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-222">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-222">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-223">オブジェクト インスタンス識別子: 177558</span><span class="sxs-lookup"><span data-stu-id="adda6-223">Object Instance Identifier: 177558</span></span>  
  
 <span data-ttu-id="adda6-224">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-224">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="adda6-225">ルール エンジン インスタンス識別子: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="adda6-225">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="adda6-226">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-226">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-227">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-227">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-228">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-228">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-229">オブジェクト インスタンス識別子: 177556</span><span class="sxs-lookup"><span data-stu-id="adda6-229">Object Instance Identifier: 177556</span></span>  
  
 <span data-ttu-id="adda6-230">上記の例は、CustInfo テーブルの 3 つの行がルールの条件を満たしていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="adda6-230">The example above indicates that three rows in the CustInfo table met the condition in the rule.</span></span>  <span data-ttu-id="adda6-231">この結果、エンジンに 3 つの一意の TypedDataRows がアサートされ、議題の更新およびルール実行が各インスタンスで発生します。</span><span class="sxs-lookup"><span data-stu-id="adda6-231">This caused three unique TypedDataRows to be asserted into the engine and an agenda update and rule firing to occur for each instance.</span></span>  
  
## <a name="typedatatabletypeddatarow"></a><span data-ttu-id="adda6-232">TypeDataTable/TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="adda6-232">TypeDataTable/TypedDataRow</span></span>  
 <span data-ttu-id="adda6-233">"LoanProcessing" ポリシーの "TestRule1" ルールの例:</span><span class="sxs-lookup"><span data-stu-id="adda6-233">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="adda6-234">**出力:**</span><span class="sxs-lookup"><span data-stu-id="adda6-234">**Output:**</span></span>  
  
 <span data-ttu-id="adda6-235">ルール セットのルール エンジン トレース: LoanProcessing 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-235">RULE ENGINE TRACE for RULESET: LoanProcessing 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-236">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-236">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-237">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-237">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-238">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-238">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-239">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-239">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-240">オブジェクトの種類: TypedDataTable:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-240">Object Type: TypedDataTable:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-241">オブジェクト インスタンス識別子: 377</span><span class="sxs-lookup"><span data-stu-id="adda6-241">Object Instance Identifier: 377</span></span>  
  
 <span data-ttu-id="adda6-242">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-242">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-243">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-243">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-244">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-244">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-245">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-245">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-246">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-246">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-247">オブジェクト インスタンス識別子: 376</span><span class="sxs-lookup"><span data-stu-id="adda6-247">Object Instance Identifier: 376</span></span>  
  
 <span data-ttu-id="adda6-248">条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-248">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-249">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-249">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-250">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-250">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-251">テスト式: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="adda6-251">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="adda6-252">左のオペランド値: 500</span><span class="sxs-lookup"><span data-stu-id="adda6-252">Left Operand Value: 500</span></span>  
  
 <span data-ttu-id="adda6-253">右のオペランド値: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-253">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="adda6-254">テスト結果: True</span><span class="sxs-lookup"><span data-stu-id="adda6-254">Test Result: True</span></span>  
  
 <span data-ttu-id="adda6-255">議題の更新 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-255">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-256">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-256">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-257">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-257">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-258">操作: 追加</span><span class="sxs-lookup"><span data-stu-id="adda6-258">Operation: Add</span></span>  
  
 <span data-ttu-id="adda6-259">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-259">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-260">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-260">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-261">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-261">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-262">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-262">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-263">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-263">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-264">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-264">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-265">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-265">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-266">オブジェクト インスタンス識別子: 375</span><span class="sxs-lookup"><span data-stu-id="adda6-266">Object Instance Identifier: 375</span></span>  
  
 <span data-ttu-id="adda6-267">条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-267">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-268">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-268">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-269">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-269">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-270">テスト式: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="adda6-270">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="adda6-271">左のオペランド値: 1000</span><span class="sxs-lookup"><span data-stu-id="adda6-271">Left Operand Value: 1000</span></span>  
  
 <span data-ttu-id="adda6-272">右のオペランド値: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-272">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="adda6-273">テスト結果: True</span><span class="sxs-lookup"><span data-stu-id="adda6-273">Test Result: True</span></span>  
  
 <span data-ttu-id="adda6-274">議題の更新 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-274">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-275">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-275">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-276">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-276">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-277">操作: 追加</span><span class="sxs-lookup"><span data-stu-id="adda6-277">Operation: Add</span></span>  
  
 <span data-ttu-id="adda6-278">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-278">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-279">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-279">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-280">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-280">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-281">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-281">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-282">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-282">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-283">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-283">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-284">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-284">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-285">オブジェクト インスタンス識別子: 374</span><span class="sxs-lookup"><span data-stu-id="adda6-285">Object Instance Identifier: 374</span></span>  
  
 <span data-ttu-id="adda6-286">条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-286">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-287">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-287">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-288">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-288">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-289">テスト式: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="adda6-289">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="adda6-290">左のオペランド値: 35000</span><span class="sxs-lookup"><span data-stu-id="adda6-290">Left Operand Value: 35000</span></span>  
  
 <span data-ttu-id="adda6-291">右のオペランド値: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-291">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="adda6-292">テスト結果: True</span><span class="sxs-lookup"><span data-stu-id="adda6-292">Test Result: True</span></span>  
  
 <span data-ttu-id="adda6-293">議題の更新 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-293">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-294">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-294">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-295">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-295">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-296">操作: 追加</span><span class="sxs-lookup"><span data-stu-id="adda6-296">Operation: Add</span></span>  
  
 <span data-ttu-id="adda6-297">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-297">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-298">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-298">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-299">2004/3/17 が実行されたルール午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-299">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-300">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-300">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-301">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-301">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-302">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-302">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-303">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-303">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-304">2004/3/17 が実行されたルール午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-304">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-305">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-305">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-306">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-306">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-307">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-307">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-308">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-308">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-309">2004/3/17 が実行されたルール午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-309">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-310">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-310">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-311">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-311">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-312">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-312">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-313">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-313">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-314">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-314">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-315">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-315">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-316">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-316">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-317">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-317">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-318">オブジェクトの種類: TypedDataTable:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-318">Object Type: TypedDataTable:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-319">オブジェクト インスタンス識別子: 377</span><span class="sxs-lookup"><span data-stu-id="adda6-319">Object Instance Identifier: 377</span></span>  
  
 <span data-ttu-id="adda6-320">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-320">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-321">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-321">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-322">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-322">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-323">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-323">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-324">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-324">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-325">オブジェクト インスタンス識別子: 375</span><span class="sxs-lookup"><span data-stu-id="adda6-325">Object Instance Identifier: 375</span></span>  
  
 <span data-ttu-id="adda6-326">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-326">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-327">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-327">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-328">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-328">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-329">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-329">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-330">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-330">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-331">オブジェクト インスタンス識別子: 374</span><span class="sxs-lookup"><span data-stu-id="adda6-331">Object Instance Identifier: 374</span></span>  
  
 <span data-ttu-id="adda6-332">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="adda6-332">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="adda6-333">ルール エンジン インスタンス識別子: 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="adda6-333">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="adda6-334">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-334">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-335">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-335">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-336">オブジェクトの種類: TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="adda6-336">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="adda6-337">オブジェクト インスタンス識別子: 376</span><span class="sxs-lookup"><span data-stu-id="adda6-337">Object Instance Identifier: 376</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adda6-338">上記の例は、TypedDataTable に 3 つの行が含まれていることを示しています。各行は、TypedDataRow としてアサートされています。</span><span class="sxs-lookup"><span data-stu-id="adda6-338">The example above shows that the TypedDataTable contained three rows, and each was asserted as a TypedDataRow.</span></span>  <span data-ttu-id="adda6-339">各行は、条件で True として評価され、ルールが議題に追加されて実行されます。</span><span class="sxs-lookup"><span data-stu-id="adda6-339">Each evaluated to True in the condition and caused the rule to be added to the agenda and fired.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="adda6-340">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="adda6-340">TypedXmlDocument</span></span>  
 <span data-ttu-id="adda6-341">"LoanProcessing" ポリシーの "TestRule1" ルールの例:</span><span class="sxs-lookup"><span data-stu-id="adda6-341">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
THEN <do something>  
```  
  
 <span data-ttu-id="adda6-342">**出力:**</span><span class="sxs-lookup"><span data-stu-id="adda6-342">**Output:**</span></span>  
  
 <span data-ttu-id="adda6-343">ルール セットのルール エンジン トレース: LoanProcessing 2004/3/17 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-343">RULE ENGINE TRACE for RULESET: LoanProcessing 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="adda6-344">ファクト アクティビティ 2004/3/17 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-344">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="adda6-345">ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="adda6-345">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="adda6-346">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-346">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-347">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-347">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-348">オブジェクトの種類: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span><span class="sxs-lookup"><span data-stu-id="adda6-348">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span></span>  
  
 <span data-ttu-id="adda6-349">オブジェクト インスタンス識別子: 858</span><span class="sxs-lookup"><span data-stu-id="adda6-349">Object Instance Identifier: 858</span></span>  
  
 <span data-ttu-id="adda6-350">ファクト アクティビティ 2004/3/17 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-350">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="adda6-351">ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="adda6-351">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="adda6-352">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-352">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-353">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-353">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-354">オブジェクトの種類: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span><span class="sxs-lookup"><span data-stu-id="adda6-354">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span></span>  
  
 <span data-ttu-id="adda6-355">オブジェクト インスタンス識別子: 853</span><span class="sxs-lookup"><span data-stu-id="adda6-355">Object Instance Identifier: 853</span></span>  
  
 <span data-ttu-id="adda6-356">条件の評価テスト (一致) 2004/3/17 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-356">CONDITION EVALUATION TEST (MATCH) 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="adda6-357">ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="adda6-357">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="adda6-358">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-358">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-359">テスト式: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths > 4 を =</span><span class="sxs-lookup"><span data-stu-id="adda6-359">Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4</span></span>  
  
 <span data-ttu-id="adda6-360">左のオペランド値: 6</span><span class="sxs-lookup"><span data-stu-id="adda6-360">Left Operand Value: 6</span></span>  
  
 <span data-ttu-id="adda6-361">右のオペランド値: 4</span><span class="sxs-lookup"><span data-stu-id="adda6-361">Right Operand Value: 4</span></span>  
  
 <span data-ttu-id="adda6-362">テスト結果: True</span><span class="sxs-lookup"><span data-stu-id="adda6-362">Test Result: True</span></span>  
  
 <span data-ttu-id="adda6-363">議題の更新 2004/3/17 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-363">AGENDA UPDATE 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="adda6-364">ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="adda6-364">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="adda6-365">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-365">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-366">操作: 追加</span><span class="sxs-lookup"><span data-stu-id="adda6-366">Operation: Add</span></span>  
  
 <span data-ttu-id="adda6-367">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-367">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-368">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-368">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-369">2004/3/17 が実行されたルール 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-369">RULE FIRED 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="adda6-370">ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="adda6-370">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="adda6-371">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-371">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-372">ルール名: TestRule1</span><span class="sxs-lookup"><span data-stu-id="adda6-372">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="adda6-373">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-373">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-374">ファクト アクティビティ 2004/3/17 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-374">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="adda6-375">ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="adda6-375">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="adda6-376">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-376">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-377">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-377">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-378">オブジェクトの種類: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span><span class="sxs-lookup"><span data-stu-id="adda6-378">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span></span>  
  
 <span data-ttu-id="adda6-379">オブジェクト インスタンス識別子: 858</span><span class="sxs-lookup"><span data-stu-id="adda6-379">Object Instance Identifier: 858</span></span>  
  
 <span data-ttu-id="adda6-380">ファクト アクティビティ 2004/3/17 9:23:05 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-380">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="adda6-381">ルール エンジン インスタンス識別子: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="adda6-381">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="adda6-382">ルール セット名: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="adda6-382">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="adda6-383">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-383">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-384">オブジェクトの種類: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span><span class="sxs-lookup"><span data-stu-id="adda6-384">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span></span>  
  
 <span data-ttu-id="adda6-385">オブジェクト インスタンス識別子: 853</span><span class="sxs-lookup"><span data-stu-id="adda6-385">Object Instance Identifier: 853</span></span>  
  
 <span data-ttu-id="adda6-386">次の例、 **TypedXmlDocument** "microsoft.samples.biztalk.loansprocessor.case"というのドキュメントの種類を使用してエンジンにアサートされました。</span><span class="sxs-lookup"><span data-stu-id="adda6-386">This example shows that a **TypedXmlDocument** was asserted into the engine with a document type of "Microsoft.Samples.BizTalk.LoansProcessor.Case".</span></span>  <span data-ttu-id="adda6-387">次に、ルールで定義された XPath セレクターに応じて、エンジンは、ドキュメントの種類とセレクターの文字列に基づいた "Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType" の子 TypedXmlDocument を作成してアサートします。</span><span class="sxs-lookup"><span data-stu-id="adda6-387">Based on the XPath selector defined in the rule, the engine then created and asserted a child TypedXmlDocument with type  "Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType" based on the document type and selector string.</span></span>  
  
 <span data-ttu-id="adda6-388">この子 TypedXmlDocument は、条件で True に評価されたため、議題の更新やルールの実行が行われます。</span><span class="sxs-lookup"><span data-stu-id="adda6-388">This child TypedXmlDocument evaluated to True in the condition, causing an agenda update and rule firing.</span></span>  <span data-ttu-id="adda6-389">親と子**TypedXmlDocument**が取り消されます。</span><span class="sxs-lookup"><span data-stu-id="adda6-389">The parent and child **TypedXmlDocument**'s were then retracted.</span></span>  
  
## <a name="update-function"></a><span data-ttu-id="adda6-390">Update 関数</span><span class="sxs-lookup"><span data-stu-id="adda6-390">Update Function</span></span>  
 <span data-ttu-id="adda6-391">"Order" ポリシーの例</span><span class="sxs-lookup"><span data-stu-id="adda6-391">Example policy "Order"</span></span>  
  
 <span data-ttu-id="adda6-392">**"InventoryCheck"ルール**</span><span class="sxs-lookup"><span data-stu-id="adda6-392">**"InventoryCheck" Rule**</span></span>  
  
```  
IF Inventory.AllocateInventory == True  
THEN Order.inventoryAvailable == True  
   Update(Order)  
```  
  
 <span data-ttu-id="adda6-393">**"Ship"ルール**</span><span class="sxs-lookup"><span data-stu-id="adda6-393">**"Ship" Rule**</span></span>  
  
```  
IF Order.inventoryAvailable == True  
THEN Shipment.ShipOrder  
```  
  
 <span data-ttu-id="adda6-394">**出力:**</span><span class="sxs-lookup"><span data-stu-id="adda6-394">**Output:**</span></span>  
  
 <span data-ttu-id="adda6-395">ルール セットのルール エンジン トレース: Order 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-395">RULE ENGINE TRACE for RULESET: Order 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-396">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-396">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-397">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-397">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-398">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-398">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-399">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-399">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-400">オブジェクトの種類: TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="adda6-400">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="adda6-401">オブジェクト インスタンス識別子: 448</span><span class="sxs-lookup"><span data-stu-id="adda6-401">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="adda6-402">条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-402">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-403">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-403">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-404">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-404">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-405">テスト式: TestClasses.Order.inventoryAvailable = = True</span><span class="sxs-lookup"><span data-stu-id="adda6-405">Test Expression: TestClasses.Order.inventoryAvailable == True</span></span>  
  
 <span data-ttu-id="adda6-406">左のオペランド値: null</span><span class="sxs-lookup"><span data-stu-id="adda6-406">Left Operand Value: null</span></span>  
  
 <span data-ttu-id="adda6-407">右のオペランド値: True</span><span class="sxs-lookup"><span data-stu-id="adda6-407">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="adda6-408">テスト結果: False</span><span class="sxs-lookup"><span data-stu-id="adda6-408">Test Result: False</span></span>  
  
 <span data-ttu-id="adda6-409">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-409">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-410">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-410">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-411">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-411">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-412">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-412">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-413">オブジェクトの種類: TestClasses.Shipment</span><span class="sxs-lookup"><span data-stu-id="adda6-413">Object Type: TestClasses.Shipment</span></span>  
  
 <span data-ttu-id="adda6-414">オブジェクト インスタンス識別子: 447</span><span class="sxs-lookup"><span data-stu-id="adda6-414">Object Instance Identifier: 447</span></span>  
  
 <span data-ttu-id="adda6-415">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-415">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-416">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-416">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-417">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-417">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-418">操作: アサート</span><span class="sxs-lookup"><span data-stu-id="adda6-418">Operation: Assert</span></span>  
  
 <span data-ttu-id="adda6-419">オブジェクトの種類: TestClasses.Inventory</span><span class="sxs-lookup"><span data-stu-id="adda6-419">Object Type: TestClasses.Inventory</span></span>  
  
 <span data-ttu-id="adda6-420">オブジェクト インスタンス識別子: 446</span><span class="sxs-lookup"><span data-stu-id="adda6-420">Object Instance Identifier: 446</span></span>  
  
 <span data-ttu-id="adda6-421">条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-421">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-422">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-422">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-423">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-423">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-424">テスト式: TestClasses.Inventory.AllocateInventory = = True</span><span class="sxs-lookup"><span data-stu-id="adda6-424">Test Expression: TestClasses.Inventory.AllocateInventory == True</span></span>  
  
 <span data-ttu-id="adda6-425">左のオペランド値: True</span><span class="sxs-lookup"><span data-stu-id="adda6-425">Left Operand Value: True</span></span>  
  
 <span data-ttu-id="adda6-426">右のオペランド値: True</span><span class="sxs-lookup"><span data-stu-id="adda6-426">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="adda6-427">テスト結果: True</span><span class="sxs-lookup"><span data-stu-id="adda6-427">Test Result: True</span></span>  
  
 <span data-ttu-id="adda6-428">議題の更新 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-428">AGENDA UPDATE 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-429">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-429">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-430">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-430">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-431">操作: 追加</span><span class="sxs-lookup"><span data-stu-id="adda6-431">Operation: Add</span></span>  
  
 <span data-ttu-id="adda6-432">ルール名: InventoryCheck</span><span class="sxs-lookup"><span data-stu-id="adda6-432">Rule Name: InventoryCheck</span></span>  
  
 <span data-ttu-id="adda6-433">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-433">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-434">2004/3/17 が実行されたルール 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-434">RULE FIRED 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-435">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-435">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-436">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-436">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-437">ルール名: InventoryCheck</span><span class="sxs-lookup"><span data-stu-id="adda6-437">Rule Name: InventoryCheck</span></span>  
  
 <span data-ttu-id="adda6-438">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-438">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-439">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-439">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-440">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-440">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-441">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-441">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-442">操作: 更新プログラム</span><span class="sxs-lookup"><span data-stu-id="adda6-442">Operation: Update</span></span>  
  
 <span data-ttu-id="adda6-443">オブジェクトの種類: TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="adda6-443">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="adda6-444">オブジェクト インスタンス識別子: 448</span><span class="sxs-lookup"><span data-stu-id="adda6-444">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="adda6-445">条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-445">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-446">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-446">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-447">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-447">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-448">テスト式: TestClasses.Order.inventoryAvailable = = True</span><span class="sxs-lookup"><span data-stu-id="adda6-448">Test Expression: TestClasses.Order.inventoryAvailable == True</span></span>  
  
 <span data-ttu-id="adda6-449">左のオペランド値: True</span><span class="sxs-lookup"><span data-stu-id="adda6-449">Left Operand Value: True</span></span>  
  
 <span data-ttu-id="adda6-450">右のオペランド値: True</span><span class="sxs-lookup"><span data-stu-id="adda6-450">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="adda6-451">テスト結果: True</span><span class="sxs-lookup"><span data-stu-id="adda6-451">Test Result: True</span></span>  
  
 <span data-ttu-id="adda6-452">議題の更新 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-452">AGENDA UPDATE 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-453">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-453">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-454">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-454">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-455">操作: 追加</span><span class="sxs-lookup"><span data-stu-id="adda6-455">Operation: Add</span></span>  
  
 <span data-ttu-id="adda6-456">ルール名: 出荷</span><span class="sxs-lookup"><span data-stu-id="adda6-456">Rule Name: Ship</span></span>  
  
 <span data-ttu-id="adda6-457">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-457">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-458">2004/3/17 が実行されたルール 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-458">RULE FIRED 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-459">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-459">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-460">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-460">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-461">ルール名: 出荷</span><span class="sxs-lookup"><span data-stu-id="adda6-461">Rule Name: Ship</span></span>  
  
 <span data-ttu-id="adda6-462">競合解決条件: 0</span><span class="sxs-lookup"><span data-stu-id="adda6-462">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="adda6-463">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-463">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-464">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-464">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-465">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-465">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-466">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-466">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-467">オブジェクトの種類: TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="adda6-467">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="adda6-468">オブジェクト インスタンス識別子: 448</span><span class="sxs-lookup"><span data-stu-id="adda6-468">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="adda6-469">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-469">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-470">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-470">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-471">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-471">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-472">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-472">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-473">オブジェクトの種類: TestClasses.Shipment</span><span class="sxs-lookup"><span data-stu-id="adda6-473">Object Type: TestClasses.Shipment</span></span>  
  
 <span data-ttu-id="adda6-474">オブジェクト インスタンス識別子: 447</span><span class="sxs-lookup"><span data-stu-id="adda6-474">Object Instance Identifier: 447</span></span>  
  
 <span data-ttu-id="adda6-475">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="adda6-475">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="adda6-476">ルール エンジン インスタンス識別子: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="adda6-476">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="adda6-477">ルール セット名: 順序</span><span class="sxs-lookup"><span data-stu-id="adda6-477">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="adda6-478">操作: 取り消し</span><span class="sxs-lookup"><span data-stu-id="adda6-478">Operation: Retract</span></span>  
  
 <span data-ttu-id="adda6-479">オブジェクトの種類: TestClasses.Inventory</span><span class="sxs-lookup"><span data-stu-id="adda6-479">Object Type: TestClasses.Inventory</span></span>  
  
 <span data-ttu-id="adda6-480">オブジェクト インスタンス識別子: 446</span><span class="sxs-lookup"><span data-stu-id="adda6-480">Object Instance Identifier: 446</span></span>  
  
 <span data-ttu-id="adda6-481">この例では、Ship ルールに関連付けられている条件が最初に確認されるときに False と評価されます。</span><span class="sxs-lookup"><span data-stu-id="adda6-481">In this example, the condition associated with the Ship rule evaluates to False the first time it is checked.</span></span>  <span data-ttu-id="adda6-482">ただし、InventoryCheck ルールが実行されると、Order オブジェクトの inventoryAvailable フィールドが変更され、Update コマンドが Order オブジェクトのエンジンで発行されます。</span><span class="sxs-lookup"><span data-stu-id="adda6-482">However, when the InventoryCheck rule fires, the inventoryAvailable field on the Order is changed and an Update command is issued on the engine for the Order object.</span></span>  <span data-ttu-id="adda6-483">このため、Ship ルールが再評価されます。</span><span class="sxs-lookup"><span data-stu-id="adda6-483">This causes the Ship rule to be reevaluated.</span></span>  <span data-ttu-id="adda6-484">今回の条件は True に評価され、Ship ルールが実行されます。</span><span class="sxs-lookup"><span data-stu-id="adda6-484">This time the condition evaluates to true and the Ship rule fires.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adda6-485">ルールが不正確に書き込まれると、Update 関数の前向き連鎖で、無限ループに陥る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="adda6-485">If your rules are written incorrectly, forward chaining with the Update function may cause an infinite loop.</span></span>  <span data-ttu-id="adda6-486">無限ループが発生すると、ビジネス ルール作成ツールのポリシーをテストするときに、"ルール エンジンが実行ループを検出しました。" というエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="adda6-486">If this occurs, you will receive an error message when testing the policy in the Business Rule Composer with the text "The rule engine detected an execution loop."</span></span>