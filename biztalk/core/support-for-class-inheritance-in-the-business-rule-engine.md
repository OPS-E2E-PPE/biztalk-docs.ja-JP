---
title: "ビジネス ルール エンジンにおけるクラス継承のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code samples, Business Rules Engine
- Business Rules Engine, inheritance
- Business Rules Engine, code samples
- Business Rules Engine, examples
- examples, Business Rules Engine
ms.assetid: 50871f34-ccbe-4f77-8feb-5694e1b14837
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 930fc5591ce55f1a2ec988b307203a4154e85c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-class-inheritance-in-the-business-rule-engine"></a><span data-ttu-id="d0cb8-102">ビジネス ルール エンジンにおけるクラス継承のサポート</span><span class="sxs-lookup"><span data-stu-id="d0cb8-102">Support for Class Inheritance in the Business Rule Engine</span></span>
<span data-ttu-id="d0cb8-103">オブジェクト指向プログラミング (OOP) 言語の主要な機能の 1 つが、継承です。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-103">One of the key features of Object Oriented Programming (OOP) languages is inheritance.</span></span> <span data-ttu-id="d0cb8-104">継承では、既存のクラスの機能をすべて使用して、元のクラスを書き直すことなく、その機能を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-104">Inheritance is the ability to use all of the functionality of an existing class, and extend those capabilities without rewriting the original class.</span></span>  
  
 <span data-ttu-id="d0cb8-105">ビジネス ルール フレームワークは、2 種類のクラスの継承をサポートしています: 実装とインターフェイスします。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-105">The Business Rules Framework supports two types of class inheritance: implementation and interface.</span></span> <span data-ttu-id="d0cb8-106">実装の継承は、追加のコーディングなしで、基本クラスのプロパティおよびメソッドを使用する機能です。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-106">Implementation inheritance refers to the ability to use a base class's properties and methods with no additional coding.</span></span> <span data-ttu-id="d0cb8-107">インターフェイスの継承は、プロパティおよびメソッドの名前だけを使用しますが、子クラスは実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-107">Interface inheritance refers to the ability to use just the names of the properties and methods, but the child class must provide the implementation.</span></span>  
  
 <span data-ttu-id="d0cb8-108">ルールは共通の基本クラスで記述できますが、エンジンにアサートされるオブジェクトはクラスから派生させることができます。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-108">The rules can be written in terms of a common base class, but the objects asserted into the engine can be from derived classes.</span></span> <span data-ttu-id="d0cb8-109">次の例では、 **RegularEmployee**と**ContractEmployee**基底クラスの派生クラスは、**従業員**です。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-109">In the following example, **RegularEmployee** and **ContractEmployee** are derived classes of the base class **Employee**.</span></span>  
  
```  
class Employee  
   {  
      public string Status()  
      {   
         // member definition  
      }  
      public string TimeInMonths()        
      {   
         // member definition  
      }  
   }  
  
class ContractEmployee : Employee  
{  
   // class definition  
}  
class RegularEmployee : Employee  
{  
   // class definition  
}  
```  
  
 <span data-ttu-id="d0cb8-110">次の規則があると仮定します。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-110">Assume you have the following rule.</span></span>  
  
## <a name="rule-1"></a><span data-ttu-id="d0cb8-111">ルール 1</span><span class="sxs-lookup"><span data-stu-id="d0cb8-111">Rule 1</span></span>  
  
```  
IF Employee.TimeInMonths < 12  
THEN Employee.Status = "New"  
```  
  
 <span data-ttu-id="d0cb8-112">実行時に、ユーザーが 2 つのオブジェクトをアサートする場合、インスタンス 1 つの**ContractEmployee**と、その他のインスタンスの**RegularEmployee**、両方のオブジェクトのインスタンスが記述されたルールに対して評価されます先ほどの。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-112">At run time, if the user asserts two objects, one an instance of **ContractEmployee** and the other an instance of **RegularEmployee**, both the object instances are evaluated against the rule described earlier.</span></span>  
  
 <span data-ttu-id="d0cb8-113">ユーザーを使用してアクション内の派生クラス オブジェクトをアサートできますも、 **Assert**です。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-113">The user can also assert derived class objects in actions by using an **Assert**.</span></span> <span data-ttu-id="d0cb8-114">これにより、次の例に示すように、派生オブジェクトとその基本型を条件に含むルールは再評価されます。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-114">This causes the rules that contain the derived object and its base type in their conditions to be re-evaluated, as shown in the following example.</span></span>  
  
## <a name="rule-2"></a><span data-ttu-id="d0cb8-115">規則 2</span><span class="sxs-lookup"><span data-stu-id="d0cb8-115">Rule 2</span></span>  
  
```  
IF Employee.Status = "Contract"   
THEN Employee.Bonus = false  
Assert(new ContractEmployee())  
```  
  
 <span data-ttu-id="d0cb8-116">すべてのルールを含む、**従業員**型または**ContractEmployee**型を条件でアサーションの後に再評価されます。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-116">All rules containing the **Employee** type or the **ContractEmployee** type in their conditions get re-evaluated after the assertion.</span></span> <span data-ttu-id="d0cb8-117">この例では実装が継承されています。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-117">The type of inheritance in this example is implementation.</span></span> <span data-ttu-id="d0cb8-118">派生クラスのみがアサートされる場合でも、派生クラスではなく基本クラスのメソッドを使用してルールが記述されると基本クラスもアサートされます。</span><span class="sxs-lookup"><span data-stu-id="d0cb8-118">Even though only the derived class is asserted, the base class also gets asserted if rules are written using methods in the base instead of the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0cb8-119">参照</span><span class="sxs-lookup"><span data-stu-id="d0cb8-119">See Also</span></span>  
 [<span data-ttu-id="d0cb8-120">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="d0cb8-120">Rule Engine</span></span>](../core/rule-engine.md)