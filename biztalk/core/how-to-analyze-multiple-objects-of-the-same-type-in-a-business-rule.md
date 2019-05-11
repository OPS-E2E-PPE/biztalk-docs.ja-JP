---
title: ビジネス ルールで同じ種類の複数のオブジェクトを分析する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, multiple types
- Business Rules Framework, programming
ms.assetid: ff9790c1-13b0-4eee-8cac-d4f25ef5f0b7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1060de077a8b526db6c226786b23781da1f7421
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342938"
---
# <a name="how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule"></a><span data-ttu-id="fc9a1-102">ビジネス ルールで同じ種類の複数のオブジェクトを分析する方法</span><span class="sxs-lookup"><span data-stu-id="fc9a1-102">How to Analyze Multiple Objects of the Same Type in a Business Rule</span></span>
<span data-ttu-id="fc9a1-103">多くのシナリオでは、型に対してビジネス ルールを作成し、個別に分析され、ルールによって処理するエンジンにアサートされる型の各インスタンスします。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-103">In many scenarios, you will write a business rule against a type and expect each instance of the type that is asserted into the engine to be separately analyzed and acted upon by the rule.</span></span> <span data-ttu-id="fc9a1-104">一部のシナリオでただし、することをルールで同時に指定された型の複数のインスタンスを分析します。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-104">In some scenarios, however, you will want to analyze multiple instances of a given type simultaneously in a rule.</span></span>  
  
 <span data-ttu-id="fc9a1-105">インスタンスを使用するルールを例にとってみましょう、 **FamilyMember**クラス。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-105">Take for example a rule that uses instances of the **FamilyMember** class.</span></span>  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember.Role == Son  
AND FamilyMember.Surname == FamilyMember.Surname  
THEN FamilyMember.AddChild(FamilyMember)  
```  
  
 <span data-ttu-id="fc9a1-106">ルールを識別、 **FamilyMember**インスタンス化されている、**父親**とは別のインスタンスを**Son**します。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-106">The rule identifies a **FamilyMember** instance that is a **Father** and another instance that is a **Son**.</span></span> <span data-ttu-id="fc9a1-107">インスタンスが姓で関連付けられている場合、 **Son**インスタンスが Father インスタンス上の子オブジェクトのコレクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-107">If the instances are related by surname, the **Son** instance is added to a collection of children on the Father instance.</span></span> <span data-ttu-id="fc9a1-108">各**FamilyMember**インスタンスがルールで個別に分析された、ため、このルールは起動しませんこのシナリオで、 **FamilyMember**は 1 つのロール:**父親**または**Son**します。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-108">If each **FamilyMember** instance were analyzed separately in the rule, the rule would never fire, because in this scenario, the **FamilyMember** only has one role—**Father** or **Son**.</span></span>  
  
 <span data-ttu-id="fc9a1-109">そのため、複数のインスタンスは、ルールでまとめて分析される必要がありますをルール内の各インスタンスの id を区別する手段が必要、エンジンに示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-109">Therefore, you must indicate to the engine that multiple instances should be analyzed together in the rule, and you need a way to differentiate the identity of each instance in the rule.</span></span> <span data-ttu-id="fc9a1-110">**インスタンス ID**プロパティを使用して、この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-110">The **Instance ID** property is used to provide this functionality.</span></span> <span data-ttu-id="fc9a1-111">このフィールドはファクトをファクト エクスプ ローラーで選択した場合、[プロパティ] ウィンドウで使用します。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-111">This field is available in the Properties window when a fact is selected in Facts Explorer.</span></span> <span data-ttu-id="fc9a1-112">ルールにファクトまたはメンバーをドラッグする前に、フィールドの値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-112">You should change the value of the field prior to dragging a fact or member into a rule.</span></span>  
  
 <span data-ttu-id="fc9a1-113">使用して、**インスタンス ID**プロパティ、ルールが再構築されます。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-113">Using the **Instance ID** property, the rule would be rebuilt.</span></span> <span data-ttu-id="fc9a1-114">使用して、それらのルールの引数の**Son**のインスタンス**FamilyMember**、**インスタンス ID**フィールドが 0 ~ 1 の既定値から変更します。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-114">For those rule arguments that use the **Son** instance of **FamilyMember**, the **Instance ID** field is changed from the default of 0 to 1.</span></span> <span data-ttu-id="fc9a1-115">インスタンス ID が 0 から変更された、ファクトまたはメンバーがルール エディターにドラッグされると、インスタンス ID の値に表示、ルール、クラスを。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-115">When the Instance ID is changed from 0 and the fact or member is dragged into the rule editor, the value of Instance ID will show up in the rule after the class.</span></span>  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember(1).Role== Son  
AND FamilyMember.Surname == FamilyMember(1).Surname  
THEN FamilyMember.AddChild(FamilyMember(1))  
```  
  
 <span data-ttu-id="fc9a1-116">ここで、ある、**父親**インスタンスと**Son**インスタンスはエンジンにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-116">Now, assume that a **Father** instance and a **Son** instance are asserted into the engine.</span></span> <span data-ttu-id="fc9a1-117">エンジンのインスタンスのさまざまな組み合わせに対して、ルールが評価されます。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-117">The engine will evaluate the rule against the various combinations of the instances.</span></span> <span data-ttu-id="fc9a1-118">仮定すると、**父親**と**Son**インスタンスがある同じ姓で、 **Son**インスタンスに追加されます、**父親**インスタンスとして対象としています。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-118">Assuming that the **Father** and **Son** instance have the same surname, the **Son** instance will be added to the **Father** instance as intended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fc9a1-119">**インスタンス ID**は特定の規則の評価のコンテキスト内でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-119">The **Instance ID** is only used within the context of a given rule evaluation.</span></span> <span data-ttu-id="fc9a1-120">ポリシーの実行の間でオブジェクトのインスタンスにいない貼付されているし、オブジェクトがアサートされる順序は無関係です。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-120">It is not affixed to an object instance across the policy execution and is not related to the order in which objects are asserted.</span></span> <span data-ttu-id="fc9a1-121">各オブジェクトのインスタンスは、その型のすべてのルールの引数で評価されます。</span><span class="sxs-lookup"><span data-stu-id="fc9a1-121">Each object instance will be evaluated in all rule arguments for that type.</span></span>