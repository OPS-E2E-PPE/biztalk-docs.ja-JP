---
title: ポリシー テストのトレース出力の例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- policies, testing
- testing, examples
ms.assetid: 92e1dc7f-1a8d-41a5-84b6-46d5ad9f2ef2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 365d962c7a21721e75eb3c0c5abd6e2d93bfd5aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394948"
---
# <a name="policy-test-trace-output-examples"></a><span data-ttu-id="b8575-102">ポリシー テストのトレース出力例</span><span class="sxs-lookup"><span data-stu-id="b8575-102">Policy Test Trace Output Examples</span></span>
<span data-ttu-id="b8575-103">このセクションでは、さまざまな種類のファクトをポリシーのテストの出力の例を示します。</span><span class="sxs-lookup"><span data-stu-id="b8575-103">This section contains examples of the policy test output for different types of facts.</span></span>  
  
## <a name="net-class"></a><span data-ttu-id="b8575-104">.Net クラス</span><span class="sxs-lookup"><span data-stu-id="b8575-104">.Net Class</span></span>  
 <span data-ttu-id="b8575-105">"LoanProcessing"ポリシーの例のルール"TestRule1":</span><span class="sxs-lookup"><span data-stu-id="b8575-105">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF test.get_ID > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="b8575-106">**出力:**</span><span class="sxs-lookup"><span data-stu-id="b8575-106">**Output:**</span></span>  
  
 <span data-ttu-id="b8575-107">セットのルール エンジン トレース:LoanProcessing 2004/3/16 9時 50分: 28 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-107">RULE ENGINE TRACE for RULESET: LoanProcessing 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="b8575-108">ファクト アクティビティ 2004/3/16 9時 50分: 28 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-108">FACT ACTIVITY 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="b8575-109">ルール エンジン インスタンス識別子:9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="b8575-109">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="b8575-110">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-110">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-111">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-111">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-112">オブジェクトの種類:MyTest.test</span><span class="sxs-lookup"><span data-stu-id="b8575-112">Object Type: MyTest.test</span></span>  
  
 <span data-ttu-id="b8575-113">オブジェクト インスタンス識別子:872</span><span class="sxs-lookup"><span data-stu-id="b8575-113">Object Instance Identifier: 872</span></span>  
  
 <span data-ttu-id="b8575-114">条件の評価テスト (一致) 2004/3/16 9時 50分: 28 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-114">CONDITION EVALUATION TEST (MATCH) 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="b8575-115">ルール エンジン インスタンス識別子:9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="b8575-115">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="b8575-116">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-116">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-117">テスト式。MyTest.test.get_ID > 0</span><span class="sxs-lookup"><span data-stu-id="b8575-117">Test Expression: MyTest.test.get_ID > 0</span></span>  
  
 <span data-ttu-id="b8575-118">左側のオペランド値:100</span><span class="sxs-lookup"><span data-stu-id="b8575-118">Left Operand Value: 100</span></span>  
  
 <span data-ttu-id="b8575-119">右側のオペランド値:0</span><span class="sxs-lookup"><span data-stu-id="b8575-119">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="b8575-120">テスト結果。True</span><span class="sxs-lookup"><span data-stu-id="b8575-120">Test Result: True</span></span>  
  
 <span data-ttu-id="b8575-121">議題の更新 2004/3/16 9時 50分: 28 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-121">AGENDA UPDATE 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="b8575-122">ルール エンジン インスタンス識別子:9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="b8575-122">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="b8575-123">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-123">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-124">操作:[追加]</span><span class="sxs-lookup"><span data-stu-id="b8575-124">Operation: Add</span></span>  
  
 <span data-ttu-id="b8575-125">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-125">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-126">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-126">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-127">2004/3/16 が実行されたルール 9時 50分: 28 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-127">RULE FIRED 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="b8575-128">ルール エンジン インスタンス識別子:9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="b8575-128">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="b8575-129">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-129">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-130">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-130">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-131">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-131">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-132">ファクト アクティビティ 2004/3/16 9時 50分: 28 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-132">FACT ACTIVITY 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="b8575-133">ルール エンジン インスタンス識別子:9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="b8575-133">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="b8575-134">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-134">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-135">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-135">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-136">オブジェクトの種類:MyTest.test</span><span class="sxs-lookup"><span data-stu-id="b8575-136">Object Type: MyTest.test</span></span>  
  
 <span data-ttu-id="b8575-137">オブジェクト インスタンス識別子:872</span><span class="sxs-lookup"><span data-stu-id="b8575-137">Object Instance Identifier: 872</span></span>  
  
## <a name="dataconnectiontypeddatarow"></a><span data-ttu-id="b8575-138">DataConnection/TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="b8575-138">DataConnection/TypedDataRow</span></span>  
 <span data-ttu-id="b8575-139">"LoanProcessing"ポリシーの例のルール"TestRule1":</span><span class="sxs-lookup"><span data-stu-id="b8575-139">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="b8575-140">**出力:**</span><span class="sxs-lookup"><span data-stu-id="b8575-140">**Output:**</span></span>  
  
 <span data-ttu-id="b8575-141">セットのルール エンジン トレース:LoanProcessing 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-141">RULE ENGINE TRACE for RULESET: LoanProcessing 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-142">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-142">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-143">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-143">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-144">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-144">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-145">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-145">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-146">オブジェクトの種類:DataConnection:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-146">Object Type: DataConnection:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-147">オブジェクト インスタンス識別子:874</span><span class="sxs-lookup"><span data-stu-id="b8575-147">Object Instance Identifier: 874</span></span>  
  
 <span data-ttu-id="b8575-148">条件の評価テスト (一致) 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-148">CONDITION EVALUATION TEST (MATCH) 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-149">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-149">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-150">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-150">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-151">Test Expression: select \* from [CustInfo] where [CreditCardBalance] > 0</span><span class="sxs-lookup"><span data-stu-id="b8575-151">Test Expression: select \* from [CustInfo] where [CreditCardBalance] > 0</span></span>  
  
 <span data-ttu-id="b8575-152">左側のオペランド値:</span><span class="sxs-lookup"><span data-stu-id="b8575-152">Left Operand Value:</span></span>  
  
 <span data-ttu-id="b8575-153">右側のオペランド値:</span><span class="sxs-lookup"><span data-stu-id="b8575-153">Right Operand Value:</span></span>  
  
 <span data-ttu-id="b8575-154">テスト結果。True</span><span class="sxs-lookup"><span data-stu-id="b8575-154">Test Result: True</span></span>  
  
 <span data-ttu-id="b8575-155">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-155">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-156">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-156">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-157">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-157">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-158">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-158">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-159">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-159">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-160">オブジェクト インスタンス識別子:177556</span><span class="sxs-lookup"><span data-stu-id="b8575-160">Object Instance Identifier: 177556</span></span>  
  
 <span data-ttu-id="b8575-161">議題の更新 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-161">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-162">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-162">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-163">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-163">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-164">操作:[追加]</span><span class="sxs-lookup"><span data-stu-id="b8575-164">Operation: Add</span></span>  
  
 <span data-ttu-id="b8575-165">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-165">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-166">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-166">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-167">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-167">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-168">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-168">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-169">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-169">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-170">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-170">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-171">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-171">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-172">オブジェクト インスタンス識別子:177559</span><span class="sxs-lookup"><span data-stu-id="b8575-172">Object Instance Identifier: 177559</span></span>  
  
 <span data-ttu-id="b8575-173">議題の更新 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-173">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-174">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-174">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-175">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-175">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-176">操作:[追加]</span><span class="sxs-lookup"><span data-stu-id="b8575-176">Operation: Add</span></span>  
  
 <span data-ttu-id="b8575-177">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-177">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-178">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-178">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-179">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-179">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-180">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-180">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-181">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-181">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-182">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-182">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-183">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-183">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-184">オブジェクト インスタンス識別子:177558</span><span class="sxs-lookup"><span data-stu-id="b8575-184">Object Instance Identifier: 177558</span></span>  
  
 <span data-ttu-id="b8575-185">議題の更新 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-185">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-186">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-186">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-187">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-187">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-188">操作:[追加]</span><span class="sxs-lookup"><span data-stu-id="b8575-188">Operation: Add</span></span>  
  
 <span data-ttu-id="b8575-189">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-189">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-190">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-190">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-191">2004/3/16 が実行されたルール 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-191">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-192">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-192">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-193">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-193">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-194">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-194">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-195">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-195">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-196">2004/3/16 が実行されたルール 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-196">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-197">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-197">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-198">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-198">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-199">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-199">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-200">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-200">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-201">2004/3/16 が実行されたルール 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-201">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-202">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-202">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-203">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-203">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-204">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-204">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-205">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-205">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-206">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-206">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-207">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-207">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-208">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-208">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-209">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-209">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-210">オブジェクトの種類:DataConnection:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-210">Object Type: DataConnection:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-211">オブジェクト インスタンス識別子:874</span><span class="sxs-lookup"><span data-stu-id="b8575-211">Object Instance Identifier: 874</span></span>  
  
 <span data-ttu-id="b8575-212">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-212">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-213">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-213">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-214">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-214">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-215">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-215">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-216">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-216">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-217">オブジェクト インスタンス識別子:177559</span><span class="sxs-lookup"><span data-stu-id="b8575-217">Object Instance Identifier: 177559</span></span>  
  
 <span data-ttu-id="b8575-218">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-218">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-219">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-219">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-220">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-220">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-221">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-221">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-222">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-222">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-223">オブジェクト インスタンス識別子:177558</span><span class="sxs-lookup"><span data-stu-id="b8575-223">Object Instance Identifier: 177558</span></span>  
  
 <span data-ttu-id="b8575-224">ファクト アクティビティ 2004/3/16 8時 30分: 16 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-224">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="b8575-225">ルール エンジン インスタンス識別子:1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="b8575-225">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="b8575-226">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-226">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-227">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-227">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-228">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-228">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-229">オブジェクト インスタンス識別子:177556</span><span class="sxs-lookup"><span data-stu-id="b8575-229">Object Instance Identifier: 177556</span></span>  
  
 <span data-ttu-id="b8575-230">上記の例では、CustInfo テーブルの 3 つの行に、ルールの条件が満たされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b8575-230">The example above indicates that three rows in the CustInfo table met the condition in the rule.</span></span>  <span data-ttu-id="b8575-231">これにより、エンジンと、議題の更新と各インスタンスに対して発生するルールの実行がアサートする 3 つの一意な TypedDataRows が発生します。</span><span class="sxs-lookup"><span data-stu-id="b8575-231">This caused three unique TypedDataRows to be asserted into the engine and an agenda update and rule firing to occur for each instance.</span></span>  
  
## <a name="typedatatabletypeddatarow"></a><span data-ttu-id="b8575-232">TypeDataTable/TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="b8575-232">TypeDataTable/TypedDataRow</span></span>  
 <span data-ttu-id="b8575-233">"LoanProcessing"ポリシーの例のルール"TestRule1":</span><span class="sxs-lookup"><span data-stu-id="b8575-233">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="b8575-234">**出力:**</span><span class="sxs-lookup"><span data-stu-id="b8575-234">**Output:**</span></span>  
  
 <span data-ttu-id="b8575-235">セットのルール エンジン トレース:LoanProcessing 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-235">RULE ENGINE TRACE for RULESET: LoanProcessing 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-236">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-236">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-237">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-237">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-238">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-238">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-239">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-239">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-240">オブジェクトの種類:TypedDataTable:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-240">Object Type: TypedDataTable:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-241">オブジェクト インスタンス識別子:377</span><span class="sxs-lookup"><span data-stu-id="b8575-241">Object Instance Identifier: 377</span></span>  
  
 <span data-ttu-id="b8575-242">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-242">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-243">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-243">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-244">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-244">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-245">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-245">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-246">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-246">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-247">オブジェクト インスタンス識別子:376</span><span class="sxs-lookup"><span data-stu-id="b8575-247">Object Instance Identifier: 376</span></span>  
  
 <span data-ttu-id="b8575-248">条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-248">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-249">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-249">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-250">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-250">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-251">テスト式。TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="b8575-251">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="b8575-252">左側のオペランド値:500</span><span class="sxs-lookup"><span data-stu-id="b8575-252">Left Operand Value: 500</span></span>  
  
 <span data-ttu-id="b8575-253">右側のオペランド値:0</span><span class="sxs-lookup"><span data-stu-id="b8575-253">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="b8575-254">テスト結果。True</span><span class="sxs-lookup"><span data-stu-id="b8575-254">Test Result: True</span></span>  
  
 <span data-ttu-id="b8575-255">議題の更新 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-255">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-256">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-256">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-257">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-257">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-258">操作:[追加]</span><span class="sxs-lookup"><span data-stu-id="b8575-258">Operation: Add</span></span>  
  
 <span data-ttu-id="b8575-259">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-259">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-260">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-260">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-261">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-261">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-262">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-262">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-263">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-263">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-264">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-264">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-265">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-265">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-266">オブジェクト インスタンス識別子:375</span><span class="sxs-lookup"><span data-stu-id="b8575-266">Object Instance Identifier: 375</span></span>  
  
 <span data-ttu-id="b8575-267">条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-267">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-268">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-268">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-269">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-269">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-270">テスト式。TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="b8575-270">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="b8575-271">左側のオペランド値:1000</span><span class="sxs-lookup"><span data-stu-id="b8575-271">Left Operand Value: 1000</span></span>  
  
 <span data-ttu-id="b8575-272">右側のオペランド値:0</span><span class="sxs-lookup"><span data-stu-id="b8575-272">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="b8575-273">テスト結果。True</span><span class="sxs-lookup"><span data-stu-id="b8575-273">Test Result: True</span></span>  
  
 <span data-ttu-id="b8575-274">議題の更新 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-274">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-275">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-275">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-276">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-276">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-277">操作:[追加]</span><span class="sxs-lookup"><span data-stu-id="b8575-277">Operation: Add</span></span>  
  
 <span data-ttu-id="b8575-278">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-278">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-279">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-279">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-280">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-280">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-281">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-281">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-282">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-282">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-283">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-283">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-284">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-284">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-285">オブジェクト インスタンス識別子:374</span><span class="sxs-lookup"><span data-stu-id="b8575-285">Object Instance Identifier: 374</span></span>  
  
 <span data-ttu-id="b8575-286">条件の評価テスト (一致) 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-286">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-287">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-287">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-288">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-288">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-289">テスト式。TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="b8575-289">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="b8575-290">左側のオペランド値:35000</span><span class="sxs-lookup"><span data-stu-id="b8575-290">Left Operand Value: 35000</span></span>  
  
 <span data-ttu-id="b8575-291">右側のオペランド値:0</span><span class="sxs-lookup"><span data-stu-id="b8575-291">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="b8575-292">テスト結果。True</span><span class="sxs-lookup"><span data-stu-id="b8575-292">Test Result: True</span></span>  
  
 <span data-ttu-id="b8575-293">議題の更新 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-293">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-294">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-294">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-295">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-295">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-296">操作:[追加]</span><span class="sxs-lookup"><span data-stu-id="b8575-296">Operation: Add</span></span>  
  
 <span data-ttu-id="b8575-297">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-297">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-298">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-298">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-299">2004/3/17 が実行されたルール午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-299">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-300">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-300">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-301">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-301">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-302">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-302">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-303">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-303">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-304">2004/3/17 が実行されたルール午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-304">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-305">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-305">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-306">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-306">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-307">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-307">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-308">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-308">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-309">2004/3/17 が実行されたルール午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-309">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-310">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-310">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-311">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-311">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-312">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-312">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-313">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-313">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-314">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-314">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-315">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-315">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-316">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-316">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-317">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-317">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-318">オブジェクトの種類:TypedDataTable:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-318">Object Type: TypedDataTable:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-319">オブジェクト インスタンス識別子:377</span><span class="sxs-lookup"><span data-stu-id="b8575-319">Object Instance Identifier: 377</span></span>  
  
 <span data-ttu-id="b8575-320">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-320">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-321">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-321">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-322">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-322">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-323">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-323">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-324">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-324">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-325">オブジェクト インスタンス識別子:375</span><span class="sxs-lookup"><span data-stu-id="b8575-325">Object Instance Identifier: 375</span></span>  
  
 <span data-ttu-id="b8575-326">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-326">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-327">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-327">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-328">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-328">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-329">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-329">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-330">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-330">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-331">オブジェクト インスタンス識別子:374</span><span class="sxs-lookup"><span data-stu-id="b8575-331">Object Instance Identifier: 374</span></span>  
  
 <span data-ttu-id="b8575-332">ファクト アクティビティ 2004/3/17 午前 11時 27分: 35</span><span class="sxs-lookup"><span data-stu-id="b8575-332">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="b8575-333">ルール エンジン インスタンス識別子:0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="b8575-333">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="b8575-334">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-334">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-335">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-335">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-336">オブジェクトの種類:TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="b8575-336">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="b8575-337">オブジェクト インスタンス識別子:376</span><span class="sxs-lookup"><span data-stu-id="b8575-337">Object Instance Identifier: 376</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8575-338">上記の例は、TypedDataTable に 3 つの行が含まれているし、それぞれが、TypedDataRow としてアサートされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="b8575-338">The example above shows that the TypedDataTable contained three rows, and each was asserted as a TypedDataRow.</span></span>  <span data-ttu-id="b8575-339">ルールが議題に追加して、発生した各条件で True に評価します。</span><span class="sxs-lookup"><span data-stu-id="b8575-339">Each evaluated to True in the condition and caused the rule to be added to the agenda and fired.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="b8575-340">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="b8575-340">TypedXmlDocument</span></span>  
 <span data-ttu-id="b8575-341">"LoanProcessing"ポリシーの例のルール"TestRule1":</span><span class="sxs-lookup"><span data-stu-id="b8575-341">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
THEN <do something>  
```  
  
 <span data-ttu-id="b8575-342">**出力:**</span><span class="sxs-lookup"><span data-stu-id="b8575-342">**Output:**</span></span>  
  
 <span data-ttu-id="b8575-343">セットのルール エンジン トレース:LoanProcessing 2004/3/17 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-343">RULE ENGINE TRACE for RULESET: LoanProcessing 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="b8575-344">ファクト アクティビティ 2004/3/17 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-344">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="b8575-345">ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="b8575-345">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="b8575-346">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-346">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-347">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-347">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-348">オブジェクトの種類:TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span><span class="sxs-lookup"><span data-stu-id="b8575-348">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span></span>  
  
 <span data-ttu-id="b8575-349">オブジェクト インスタンス識別子:858</span><span class="sxs-lookup"><span data-stu-id="b8575-349">Object Instance Identifier: 858</span></span>  
  
 <span data-ttu-id="b8575-350">ファクト アクティビティ 2004/3/17 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-350">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="b8575-351">ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="b8575-351">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="b8575-352">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-352">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-353">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-353">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-354">オブジェクトの種類:TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span><span class="sxs-lookup"><span data-stu-id="b8575-354">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span></span>  
  
 <span data-ttu-id="b8575-355">オブジェクト インスタンス識別子:853</span><span class="sxs-lookup"><span data-stu-id="b8575-355">Object Instance Identifier: 853</span></span>  
  
 <span data-ttu-id="b8575-356">条件の評価テスト (一致) 2004/3/17 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-356">CONDITION EVALUATION TEST (MATCH) 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="b8575-357">ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="b8575-357">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="b8575-358">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-358">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-359">テスト式。TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4</span><span class="sxs-lookup"><span data-stu-id="b8575-359">Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4</span></span>  
  
 <span data-ttu-id="b8575-360">左側のオペランド値:6</span><span class="sxs-lookup"><span data-stu-id="b8575-360">Left Operand Value: 6</span></span>  
  
 <span data-ttu-id="b8575-361">右側のオペランド値:4</span><span class="sxs-lookup"><span data-stu-id="b8575-361">Right Operand Value: 4</span></span>  
  
 <span data-ttu-id="b8575-362">テスト結果。True</span><span class="sxs-lookup"><span data-stu-id="b8575-362">Test Result: True</span></span>  
  
 <span data-ttu-id="b8575-363">議題の更新 2004/3/17 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-363">AGENDA UPDATE 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="b8575-364">ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="b8575-364">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="b8575-365">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-365">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-366">操作:[追加]</span><span class="sxs-lookup"><span data-stu-id="b8575-366">Operation: Add</span></span>  
  
 <span data-ttu-id="b8575-367">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-367">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-368">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-368">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-369">2004/3/17 が実行されたルール 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-369">RULE FIRED 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="b8575-370">ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="b8575-370">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="b8575-371">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-371">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-372">ルール名:TestRule1</span><span class="sxs-lookup"><span data-stu-id="b8575-372">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="b8575-373">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-373">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-374">ファクト アクティビティ 2004/3/17 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-374">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="b8575-375">ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="b8575-375">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="b8575-376">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-376">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-377">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-377">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-378">オブジェクトの種類:TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span><span class="sxs-lookup"><span data-stu-id="b8575-378">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span></span>  
  
 <span data-ttu-id="b8575-379">オブジェクト インスタンス識別子:858</span><span class="sxs-lookup"><span data-stu-id="b8575-379">Object Instance Identifier: 858</span></span>  
  
 <span data-ttu-id="b8575-380">ファクト アクティビティ 2004/3/17 9時 23分: 05 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-380">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="b8575-381">ルール エンジン インスタンス識別子:51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="b8575-381">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="b8575-382">ルール セット名:LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="b8575-382">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="b8575-383">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-383">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-384">オブジェクトの種類:TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span><span class="sxs-lookup"><span data-stu-id="b8575-384">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span></span>  
  
 <span data-ttu-id="b8575-385">オブジェクト インスタンス識別子:853</span><span class="sxs-lookup"><span data-stu-id="b8575-385">Object Instance Identifier: 853</span></span>  
  
 <span data-ttu-id="b8575-386">この例では、 **TypedXmlDocument** "microsoft.samples.biztalk.loansprocessor.case"というのドキュメントの種類を使用してエンジンにアサートされました。</span><span class="sxs-lookup"><span data-stu-id="b8575-386">This example shows that a **TypedXmlDocument** was asserted into the engine with a document type of "Microsoft.Samples.BizTalk.LoansProcessor.Case".</span></span>  <span data-ttu-id="b8575-387">ルールで定義された XPath セレクターに基づいて、エンジンを作成し、ドキュメントの種類とセレクターの文字列に基づいて"Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType"の種類と子 TypedXmlDocument をアサートします。</span><span class="sxs-lookup"><span data-stu-id="b8575-387">Based on the XPath selector defined in the rule, the engine then created and asserted a child TypedXmlDocument with type  "Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType" based on the document type and selector string.</span></span>  
  
 <span data-ttu-id="b8575-388">この子 TypedXmlDocument 条件で True に評価された、議題の更新とルールの実行が原因です。</span><span class="sxs-lookup"><span data-stu-id="b8575-388">This child TypedXmlDocument evaluated to True in the condition, causing an agenda update and rule firing.</span></span>  <span data-ttu-id="b8575-389">親と子**TypedXmlDocument**の取り消されたします。</span><span class="sxs-lookup"><span data-stu-id="b8575-389">The parent and child **TypedXmlDocument**'s were then retracted.</span></span>  
  
## <a name="update-function"></a><span data-ttu-id="b8575-390">Update 関数</span><span class="sxs-lookup"><span data-stu-id="b8575-390">Update Function</span></span>  
 <span data-ttu-id="b8575-391">"Order"のポリシーの例</span><span class="sxs-lookup"><span data-stu-id="b8575-391">Example policy "Order"</span></span>  
  
 <span data-ttu-id="b8575-392">**"InventoryCheck"ルール**</span><span class="sxs-lookup"><span data-stu-id="b8575-392">**"InventoryCheck" Rule**</span></span>  
  
```  
IF Inventory.AllocateInventory == True  
THEN Order.inventoryAvailable == True  
   Update(Order)  
```  
  
 <span data-ttu-id="b8575-393">**"Ship"ルール**</span><span class="sxs-lookup"><span data-stu-id="b8575-393">**"Ship" Rule**</span></span>  
  
```  
IF Order.inventoryAvailable == True  
THEN Shipment.ShipOrder  
```  
  
 <span data-ttu-id="b8575-394">**出力:**</span><span class="sxs-lookup"><span data-stu-id="b8575-394">**Output:**</span></span>  
  
 <span data-ttu-id="b8575-395">セットのルール エンジン トレース:2004/3/17 の注文 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-395">RULE ENGINE TRACE for RULESET: Order 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-396">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-396">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-397">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-397">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-398">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-398">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-399">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-399">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-400">オブジェクトの種類:TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="b8575-400">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="b8575-401">オブジェクト インスタンス識別子:448</span><span class="sxs-lookup"><span data-stu-id="b8575-401">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="b8575-402">条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-402">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-403">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-403">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-404">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-404">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-405">テスト式。TestClasses.Order.inventoryAvailable == True</span><span class="sxs-lookup"><span data-stu-id="b8575-405">Test Expression: TestClasses.Order.inventoryAvailable == True</span></span>  
  
 <span data-ttu-id="b8575-406">左のオペランド値: null</span><span class="sxs-lookup"><span data-stu-id="b8575-406">Left Operand Value: null</span></span>  
  
 <span data-ttu-id="b8575-407">右側のオペランド値:True</span><span class="sxs-lookup"><span data-stu-id="b8575-407">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="b8575-408">テスト結果。False</span><span class="sxs-lookup"><span data-stu-id="b8575-408">Test Result: False</span></span>  
  
 <span data-ttu-id="b8575-409">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-409">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-410">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-410">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-411">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-411">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-412">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-412">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-413">オブジェクトの種類:TestClasses.Shipment</span><span class="sxs-lookup"><span data-stu-id="b8575-413">Object Type: TestClasses.Shipment</span></span>  
  
 <span data-ttu-id="b8575-414">オブジェクト インスタンス識別子:447</span><span class="sxs-lookup"><span data-stu-id="b8575-414">Object Instance Identifier: 447</span></span>  
  
 <span data-ttu-id="b8575-415">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-415">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-416">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-416">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-417">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-417">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-418">操作:Filter</span><span class="sxs-lookup"><span data-stu-id="b8575-418">Operation: Assert</span></span>  
  
 <span data-ttu-id="b8575-419">オブジェクトの種類:TestClasses.Inventory</span><span class="sxs-lookup"><span data-stu-id="b8575-419">Object Type: TestClasses.Inventory</span></span>  
  
 <span data-ttu-id="b8575-420">オブジェクト インスタンス識別子:446</span><span class="sxs-lookup"><span data-stu-id="b8575-420">Object Instance Identifier: 446</span></span>  
  
 <span data-ttu-id="b8575-421">条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-421">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-422">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-422">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-423">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-423">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-424">テスト式。TestClasses.Inventory.AllocateInventory == True</span><span class="sxs-lookup"><span data-stu-id="b8575-424">Test Expression: TestClasses.Inventory.AllocateInventory == True</span></span>  
  
 <span data-ttu-id="b8575-425">左側のオペランド値:True</span><span class="sxs-lookup"><span data-stu-id="b8575-425">Left Operand Value: True</span></span>  
  
 <span data-ttu-id="b8575-426">右側のオペランド値:True</span><span class="sxs-lookup"><span data-stu-id="b8575-426">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="b8575-427">テスト結果。True</span><span class="sxs-lookup"><span data-stu-id="b8575-427">Test Result: True</span></span>  
  
 <span data-ttu-id="b8575-428">議題の更新 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-428">AGENDA UPDATE 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-429">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-429">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-430">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-430">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-431">操作:[追加]</span><span class="sxs-lookup"><span data-stu-id="b8575-431">Operation: Add</span></span>  
  
 <span data-ttu-id="b8575-432">ルール名:InventoryCheck</span><span class="sxs-lookup"><span data-stu-id="b8575-432">Rule Name: InventoryCheck</span></span>  
  
 <span data-ttu-id="b8575-433">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-433">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-434">2004/3/17 が実行されたルール 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-434">RULE FIRED 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-435">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-435">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-436">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-436">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-437">ルール名:InventoryCheck</span><span class="sxs-lookup"><span data-stu-id="b8575-437">Rule Name: InventoryCheck</span></span>  
  
 <span data-ttu-id="b8575-438">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-438">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-439">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-439">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-440">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-440">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-441">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-441">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-442">操作:更新</span><span class="sxs-lookup"><span data-stu-id="b8575-442">Operation: Update</span></span>  
  
 <span data-ttu-id="b8575-443">オブジェクトの種類:TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="b8575-443">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="b8575-444">オブジェクト インスタンス識別子:448</span><span class="sxs-lookup"><span data-stu-id="b8575-444">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="b8575-445">条件の評価テスト (一致) 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-445">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-446">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-446">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-447">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-447">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-448">テスト式。TestClasses.Order.inventoryAvailable == True</span><span class="sxs-lookup"><span data-stu-id="b8575-448">Test Expression: TestClasses.Order.inventoryAvailable == True</span></span>  
  
 <span data-ttu-id="b8575-449">左側のオペランド値:True</span><span class="sxs-lookup"><span data-stu-id="b8575-449">Left Operand Value: True</span></span>  
  
 <span data-ttu-id="b8575-450">右側のオペランド値:True</span><span class="sxs-lookup"><span data-stu-id="b8575-450">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="b8575-451">テスト結果。True</span><span class="sxs-lookup"><span data-stu-id="b8575-451">Test Result: True</span></span>  
  
 <span data-ttu-id="b8575-452">議題の更新 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-452">AGENDA UPDATE 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-453">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-453">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-454">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-454">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-455">操作:[追加]</span><span class="sxs-lookup"><span data-stu-id="b8575-455">Operation: Add</span></span>  
  
 <span data-ttu-id="b8575-456">ルール名:出荷</span><span class="sxs-lookup"><span data-stu-id="b8575-456">Rule Name: Ship</span></span>  
  
 <span data-ttu-id="b8575-457">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-457">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-458">2004/3/17 が実行されたルール 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-458">RULE FIRED 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-459">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-459">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-460">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-460">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-461">ルール名:出荷</span><span class="sxs-lookup"><span data-stu-id="b8575-461">Rule Name: Ship</span></span>  
  
 <span data-ttu-id="b8575-462">競合解決条件:0</span><span class="sxs-lookup"><span data-stu-id="b8575-462">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="b8575-463">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-463">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-464">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-464">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-465">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-465">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-466">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-466">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-467">オブジェクトの種類:TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="b8575-467">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="b8575-468">オブジェクト インスタンス識別子:448</span><span class="sxs-lookup"><span data-stu-id="b8575-468">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="b8575-469">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-469">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-470">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-470">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-471">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-471">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-472">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-472">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-473">オブジェクトの種類:TestClasses.Shipment</span><span class="sxs-lookup"><span data-stu-id="b8575-473">Object Type: TestClasses.Shipment</span></span>  
  
 <span data-ttu-id="b8575-474">オブジェクト インスタンス識別子:447</span><span class="sxs-lookup"><span data-stu-id="b8575-474">Object Instance Identifier: 447</span></span>  
  
 <span data-ttu-id="b8575-475">ファクト アクティビティ 2004/3/17 10時 31分: 17 AM</span><span class="sxs-lookup"><span data-stu-id="b8575-475">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="b8575-476">ルール エンジン インスタンス識別子:533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="b8575-476">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="b8575-477">ルール セット名:[オーダー]</span><span class="sxs-lookup"><span data-stu-id="b8575-477">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="b8575-478">操作:取り消し</span><span class="sxs-lookup"><span data-stu-id="b8575-478">Operation: Retract</span></span>  
  
 <span data-ttu-id="b8575-479">オブジェクトの種類:TestClasses.Inventory</span><span class="sxs-lookup"><span data-stu-id="b8575-479">Object Type: TestClasses.Inventory</span></span>  
  
 <span data-ttu-id="b8575-480">オブジェクト インスタンス識別子:446</span><span class="sxs-lookup"><span data-stu-id="b8575-480">Object Instance Identifier: 446</span></span>  
  
 <span data-ttu-id="b8575-481">この例では、Ship ルールに関連付けられている条件は、最初に確認されるときを False に評価されます。</span><span class="sxs-lookup"><span data-stu-id="b8575-481">In this example, the condition associated with the Ship rule evaluates to False the first time it is checked.</span></span>  <span data-ttu-id="b8575-482">ただし、InventoryCheck ルールが発生したときは、順序の inventoryAvailable フィールドが変更され、Order オブジェクトのエンジンに対して、Update コマンドが実行されました。</span><span class="sxs-lookup"><span data-stu-id="b8575-482">However, when the InventoryCheck rule fires, the inventoryAvailable field on the Order is changed and an Update command is issued on the engine for the Order object.</span></span>  <span data-ttu-id="b8575-483">これにより、Ship ルールが再評価されます。</span><span class="sxs-lookup"><span data-stu-id="b8575-483">This causes the Ship rule to be reevaluated.</span></span>  <span data-ttu-id="b8575-484">この時間条件を true と評価、Ship ルールが起動します。</span><span class="sxs-lookup"><span data-stu-id="b8575-484">This time the condition evaluates to true and the Ship rule fires.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8575-485">ルールが正しく書き込まれた、前向き連鎖更新関数で、無限ループことがあります。</span><span class="sxs-lookup"><span data-stu-id="b8575-485">If your rules are written incorrectly, forward chaining with the Update function may cause an infinite loop.</span></span>  <span data-ttu-id="b8575-486">この場合、メッセージが表示されます、エラー テキストを含むビジネス ルール作成ツールでポリシーをテストするときに「ルール エンジンの検出は実行ループを」</span><span class="sxs-lookup"><span data-stu-id="b8575-486">If this occurs, you will receive an error message when testing the policy in the Business Rule Composer with the text "The rule engine detected an execution loop."</span></span>