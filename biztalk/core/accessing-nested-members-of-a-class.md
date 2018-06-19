---
title: クラスの入れ子になったメンバーへのアクセス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 358e1edf-ae0b-4916-b8db-7277f39e36f4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110244f9f007a417450b5bbfdce831d5f255cfe5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224522"
---
# <a name="accessing-nested-members-of-a-class"></a><span data-ttu-id="36912-102">クラスの入れ子メンバーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="36912-102">Accessing Nested Members of a Class</span></span>
<span data-ttu-id="36912-103">ルール エンジンでは、ルール内のオブジェクトの入れ子になったプロパティまたはメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="36912-103">The rule engine allows you to use a nested property or method of an object in a rule.</span></span> <span data-ttu-id="36912-104">たとえば、Aclass という名前のクラスに B という名前のプロパティがあり、そのプロパティに C という名前のフィールドが含まれているとします。ルール エンジンでは、A.B.C 構文を使用してフィールド C にアクセスするルールを構築することができます。</span><span class="sxs-lookup"><span data-stu-id="36912-104">For example, suppose you have a class named AClass, which has a property named B of type BClass, which has a field named C. The rule engine allows you to build rules accessing the field C by using the A.B.C syntax.</span></span> <span data-ttu-id="36912-105">ただし、この構文は、ルールをプログラムで構築する場合にだけ使用できます。ビジネス ルール作成ツールでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="36912-105">However, it is possible to use this syntax only when building the rules programmatically, not when using the Business Rule Composer tool.</span></span> <span data-ttu-id="36912-106">別のオブジェクトのプロパティであるオブジェクトのプロパティを使用する方法を次のサンプルコードに示します。</span><span class="sxs-lookup"><span data-stu-id="36912-106">The following sample code demonstrates how to use a property of an object, which is a property of another object:</span></span>  
  
```  
// Create the condition list IF 1 == 1  
Equal eq = new Equal(new Constant(1), new Constant(1));  
  
// Create the action collection  
ActionCollection ac = new ActionCollection();  
  
// Create class binding and class member binding to cField  
// Set the value of cField to "Changed"  
Constant chg = new Constant("Changed");  
ArgumentCollection argCol = new ArgumentCollection();  
argCol.Add(chg);  
ClassBinding lstClass = new ClassBinding(typeof(AClass));  
ClassMemberBinding bBinding = new ClassMemberBinding("bObj", lstClass);  
ClassMemberBinding CBinding = new ClassMemberBinding("cField", bBinding,argCol);  
UserFunction uf_C = new UserFunction(CBinding);  
ac.Add(uf_C);  
  
// Create the rule  
Rule rl = new Rule("ChangeCField", eq, ac);  
  
// Create the policy  
RuleSet rs = new RuleSet("NestedNodeTest");  
rs.Rules.Add(rl);  
  
//Create the facts  
AClass aObj = new AClass();  
Console.WriteLine("The value of aObj.bObj.cField BEFORE executing the policy");  
Console.WriteLine(aObj.bObj.cField);  
  
//Execute the policy  
PolicyTester tester = new PolicyTester(rs);  
tester.Execute(aObj);  
  
Console.WriteLine("The value of aObj.bObj.cField AFTER executing the policy");  
Console.WriteLine(aObj.bObj.cField);  
```