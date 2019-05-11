---
title: ビジネス ルール エンジンにおけるクラス継承のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- code samples, Business Rules Engine
- Business Rules Engine, inheritance
- Business Rules Engine, code samples
- Business Rules Engine, examples
- examples, Business Rules Engine
ms.assetid: 50871f34-ccbe-4f77-8feb-5694e1b14837
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a21d9d300bf01e2ab792ca86f8a52b9b5831695c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321908"
---
# <a name="support-for-class-inheritance-in-the-business-rule-engine"></a><span data-ttu-id="d9a9a-102">ビジネス ルール エンジンにおけるクラス継承のサポート</span><span class="sxs-lookup"><span data-stu-id="d9a9a-102">Support for Class Inheritance in the Business Rule Engine</span></span>
<span data-ttu-id="d9a9a-103">オブジェクト指向プログラミング (OOP) 言語の主な機能の 1 つは、継承です。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-103">One of the key features of Object Oriented Programming (OOP) languages is inheritance.</span></span> <span data-ttu-id="d9a9a-104">継承は、すべての既存のクラスの機能を使用し、元のクラスを書き直すことがなくそれらの機能を拡張する機能です。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-104">Inheritance is the ability to use all of the functionality of an existing class, and extend those capabilities without rewriting the original class.</span></span>  
  
 <span data-ttu-id="d9a9a-105">ビジネス ルール フレームワークは、2 種類のクラスの継承をサポートしています: 実装とインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-105">The Business Rules Framework supports two types of class inheritance: implementation and interface.</span></span> <span data-ttu-id="d9a9a-106">実装の継承は、追加のコーディングなしで基本クラスのプロパティとメソッドを使用する機能を指します。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-106">Implementation inheritance refers to the ability to use a base class's properties and methods with no additional coding.</span></span> <span data-ttu-id="d9a9a-107">インターフェイスの継承は、プロパティおよびメソッドの名前だけを使用する機能が、子クラスは、実装を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-107">Interface inheritance refers to the ability to use just the names of the properties and methods, but the child class must provide the implementation.</span></span>  
  
 <span data-ttu-id="d9a9a-108">共通の基本クラスでは、ルールを記述できますが、エンジンにアサートされるオブジェクトがクラスから派生させることができます。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-108">The rules can be written in terms of a common base class, but the objects asserted into the engine can be from derived classes.</span></span> <span data-ttu-id="d9a9a-109">次の例では、 **RegularEmployee**と**ContractEmployee**基底クラスの派生クラスは**従業員**します。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-109">In the following example, **RegularEmployee** and **ContractEmployee** are derived classes of the base class **Employee**.</span></span>  
  
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
  
 <span data-ttu-id="d9a9a-110">次の規則があると仮定します。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-110">Assume you have the following rule.</span></span>  
  
## <a name="rule-1"></a><span data-ttu-id="d9a9a-111">ルール 1</span><span class="sxs-lookup"><span data-stu-id="d9a9a-111">Rule 1</span></span>  
  
```  
IF Employee.TimeInMonths < 12  
THEN Employee.Status = "New"  
```  
  
 <span data-ttu-id="d9a9a-112">実行時に、ユーザーが 2 つのオブジェクトをアサートしている場合、インスタンス 1 つの**ContractEmployee**と、その他のインスタンスの**RegularEmployee**、両方のオブジェクトのインスタンスは、ルールに対して評価されます先ほどの。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-112">At run time, if the user asserts two objects, one an instance of **ContractEmployee** and the other an instance of **RegularEmployee**, both the object instances are evaluated against the rule described earlier.</span></span>  
  
 <span data-ttu-id="d9a9a-113">ユーザーを使用して派生クラス オブジェクトをアサートできますも、 **Assert**します。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-113">The user can also assert derived class objects in actions by using an **Assert**.</span></span> <span data-ttu-id="d9a9a-114">これにより、ルールと、次の例に示すように、派生オブジェクトとその基本型の条件の再評価されることが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-114">This causes the rules that contain the derived object and its base type in their conditions to be re-evaluated, as shown in the following example.</span></span>  
  
## <a name="rule-2"></a><span data-ttu-id="d9a9a-115">Rule 2</span><span class="sxs-lookup"><span data-stu-id="d9a9a-115">Rule 2</span></span>  
  
```  
IF Employee.Status = "Contract"   
THEN Employee.Bonus = false  
Assert(new ContractEmployee())  
```  
  
 <span data-ttu-id="d9a9a-116">含むすべてのルール、**従業員**型または**ContractEmployee**アサーション後型を条件で再評価されます。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-116">All rules containing the **Employee** type or the **ContractEmployee** type in their conditions get re-evaluated after the assertion.</span></span> <span data-ttu-id="d9a9a-117">この例では、継承の種類は、実装です。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-117">The type of inheritance in this example is implementation.</span></span> <span data-ttu-id="d9a9a-118">場合でも、派生クラスのみがアサートされると、基本クラスも取得アサート メソッドを使用して、派生クラスではなく、基本ルールが記述されている場合。</span><span class="sxs-lookup"><span data-stu-id="d9a9a-118">Even though only the derived class is asserted, the base class also gets asserted if rules are written using methods in the base instead of the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9a9a-119">参照</span><span class="sxs-lookup"><span data-stu-id="d9a9a-119">See Also</span></span>  
 [<span data-ttu-id="d9a9a-120">ルール エンジン</span><span class="sxs-lookup"><span data-stu-id="d9a9a-120">Rule Engine</span></span>](../core/rule-engine.md)