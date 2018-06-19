---
title: ジェネリック型とジェネリック メソッドのサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc6b5b51-e084-4828-ad25-9209aa74dc6f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65d8a17a9ac1f055312f0f1cdf3bc1231319842d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972320"
---
# <a name="support-for-generic-types-and-generic-methods"></a><span data-ttu-id="0180d-102">ジェネリック型とジェネリック メソッドのサポート</span><span class="sxs-lookup"><span data-stu-id="0180d-102">Support for Generic Types and Generic Methods</span></span>
<span data-ttu-id="0180d-103">ルール エンジンは、特殊なジェネリック型と特殊なジェネリック メソッドについて、ルール内での使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0180d-103">The rule engine supports using specialized generic types and specialized generic methods in a rule.</span></span> <span data-ttu-id="0180d-104">ジェネリック型とジェネリック メソッド自体については、ルール内での使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0180d-104">It does not support using generic types and generic methods themselves in a rule.</span></span> <span data-ttu-id="0180d-105">たとえば、ビジネス ルールで行うこともできます**リスト**\<*int*\>、ではなく**リスト**\<T\> (、から**System.Collections.Generic** .NET クラス ライブラリの名前空間)。</span><span class="sxs-lookup"><span data-stu-id="0180d-105">For example, in a business rule you can use **List**\<*int*\>, but not **List**\<T\> (from the **System.Collections.Generic** namespace in the .NET class library).</span></span> <span data-ttu-id="0180d-106">現在、ビジネス ルール作成ツールは、特殊なジェネリック型と特殊なジェネリック メソッドを使用したルールの作成をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0180d-106">Currently, the Business Rule Composer tool does not support creating rules by using specialized generic types and specialized generic methods.</span></span> <span data-ttu-id="0180d-107">ルール エンジン オブジェクト モデルを使用し、プログラムによってルールを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0180d-107">You must create the rules programmatically by using the rule engine object model.</span></span> <span data-ttu-id="0180d-108">次のサンプル コードを使用する方法を示しています、**リスト**のビジネス ルールに汎用クラス。</span><span class="sxs-lookup"><span data-stu-id="0180d-108">The following sample code demonstrates how to use the **List** generic class in a business rule:</span></span>  
  
```  
  
// Create the condition list IF 1 == 1  
Equal eq = new Equal(new Constant(1), new Constant(1));  
  
// Create the action list List<int>.Add(3)  
ActionCollection ac = new ActionCollection();  
  
//Create class binding and class member bindings  
ClassBinding lstClass = new ClassBinding(typeof(System.Collections.Generic.List<int>));  
ArgumentCollection argc = new ArgumentCollection();  
argc.Add(new Constant(3));  
ClassMemberBinding add = new ClassMemberBinding("Add", lstClass, argc);  
  
// Wrapping the .NET binding as a user function  
UserFunction uf = new UserFunction(add);  
ac.Add(uf);  
  
// Create the rule  
Rule rl = new Rule("AddToList", eq, ac);  
  
// Create the policy  
RuleSet rs = new RuleSet("GenericTest");  
rs.Rules.Add(rl);  
  
// Create the .NET List object  
List<int> lst = new List<int>();  
lst.Add(1);  
lst.Add(2);  
  
// Print the list before executing the policy  
Console.WriteLine("Contents of the lists before executing the policy");  
foreach (int i in lst)  
    Console.WriteLine(i);  
  
PolicyTester pt = new PolicyTester(rs);  
pt.Execute(lst);  
  
// Print the list after executing the policy  
Console.WriteLine("Contents of the lists before executing the policy");  
foreach (int i in lst)  
    Console.WriteLine(i);  
```