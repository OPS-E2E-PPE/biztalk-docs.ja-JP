---
title: "ビジネス ルールで同じ種類の複数のオブジェクトを分析する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- business rules, multiple types
- Business Rules Framework, programming
ms.assetid: ff9790c1-13b0-4eee-8cac-d4f25ef5f0b7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a1e4d2fb01513b1d4d314264ab74b84d3a0223a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-analyze-multiple-objects-of-the-same-type-in-a-business-rule"></a><span data-ttu-id="181ea-102">ビジネス ルールで同じ種類の複数のオブジェクトを分析する方法</span><span class="sxs-lookup"><span data-stu-id="181ea-102">How to Analyze Multiple Objects of the Same Type in a Business Rule</span></span>
<span data-ttu-id="181ea-103">多くのシナリオでは、さまざまな種類のビジネス ルールが作成されます。また、エンジンにアサートされる各インスタンスの種類が個別に分析され、ルールに従って処理されることが期待されます。</span><span class="sxs-lookup"><span data-stu-id="181ea-103">In many scenarios, you will write a business rule against a type and expect each instance of the type that is asserted into the engine to be separately analyzed and acted upon by the rule.</span></span> <span data-ttu-id="181ea-104">ただし、場合によっては、特定の種類の複数のインスタンスをルールで同時に分析することがあります。</span><span class="sxs-lookup"><span data-stu-id="181ea-104">In some scenarios, however, you will want to analyze multiple instances of a given type simultaneously in a rule.</span></span>  
  
 <span data-ttu-id="181ea-105">インスタンスを使用するルールがかかるなど、 **FamilyMember**クラスです。</span><span class="sxs-lookup"><span data-stu-id="181ea-105">Take for example a rule that uses instances of the **FamilyMember** class.</span></span>  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember.Role == Son  
AND FamilyMember.Surname == FamilyMember.Surname  
THEN FamilyMember.AddChild(FamilyMember)  
```  
  
 <span data-ttu-id="181ea-106">ルールを識別、 **FamilyMember**インスタンス化されている、 **Father**とは別のインスタンス、 **Son**です。</span><span class="sxs-lookup"><span data-stu-id="181ea-106">The rule identifies a **FamilyMember** instance that is a **Father** and another instance that is a **Son**.</span></span> <span data-ttu-id="181ea-107">インスタンスが姓で関連付けられている場合、 **Son**インスタンスが Father インスタンス上の子のコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="181ea-107">If the instances are related by surname, the **Son** instance is added to a collection of children on the Father instance.</span></span> <span data-ttu-id="181ea-108">各**FamilyMember**インスタンスがルールで個別に分析された、ため、このルールは起動しませんこのシナリオでは、 **FamilyMember**のみが 1 つのロール:**Father**または**Son**です。</span><span class="sxs-lookup"><span data-stu-id="181ea-108">If each **FamilyMember** instance were analyzed separately in the rule, the rule would never fire, because in this scenario, the **FamilyMember** only has one role—**Father** or **Son**.</span></span>  
  
 <span data-ttu-id="181ea-109">このため、複数のインスタンスがルールでまとめて分析されることをエンジンに示す必要があります。また、ルールの各インスタンスの ID を区別する手段が必要です。</span><span class="sxs-lookup"><span data-stu-id="181ea-109">Therefore, you must indicate to the engine that multiple instances should be analyzed together in the rule, and you need a way to differentiate the identity of each instance in the rule.</span></span> <span data-ttu-id="181ea-110">**インスタンス ID**プロパティを使用して、この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="181ea-110">The **Instance ID** property is used to provide this functionality.</span></span> <span data-ttu-id="181ea-111">このフィールドは、ファクト エクスプローラーでファクトを選択する際のプロパティ ウィンドウで使用できます。</span><span class="sxs-lookup"><span data-stu-id="181ea-111">This field is available in the Properties window when a fact is selected in Facts Explorer.</span></span> <span data-ttu-id="181ea-112">ファクトまたはメンバーをルールにドラッグする前に、フィールドの値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="181ea-112">You should change the value of the field prior to dragging a fact or member into a rule.</span></span>  
  
 <span data-ttu-id="181ea-113">使用して、**インスタンス ID**プロパティ、ルールが再構築されます。</span><span class="sxs-lookup"><span data-stu-id="181ea-113">Using the **Instance ID** property, the rule would be rebuilt.</span></span> <span data-ttu-id="181ea-114">これらのルールの引数を使用するため、 **Son**のインスタンス**FamilyMember**、**インスタンス ID**フィールドが 0 ~ 1 の既定値から変更します。</span><span class="sxs-lookup"><span data-stu-id="181ea-114">For those rule arguments that use the **Son** instance of **FamilyMember**, the **Instance ID** field is changed from the default of 0 to 1.</span></span> <span data-ttu-id="181ea-115">インスタンス ID は 0 から変更し、ファクトまたはメンバーがルール エディターにドラッグされるときにインスタンス ID の値に表示されます、ルール、クラスの後にします。</span><span class="sxs-lookup"><span data-stu-id="181ea-115">When the Instance ID is changed from 0 and the fact or member is dragged into the rule editor, the value of Instance ID will show up in the rule after the class.</span></span>  
  
```  
IF FamilyMember.Role == Father  
AND FamilyMember(1).Role== Son  
AND FamilyMember.Surname == FamilyMember(1).Surname  
THEN FamilyMember.AddChild(FamilyMember(1))  
```  
  
 <span data-ttu-id="181ea-116">ここで、あると想定、 **Father**インスタンスおよび**Son**インスタンスはエンジンにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="181ea-116">Now, assume that a **Father** instance and a **Son** instance are asserted into the engine.</span></span> <span data-ttu-id="181ea-117">エンジンは、インスタンスのさまざまな組み合わせに対して、ルールを評価します。</span><span class="sxs-lookup"><span data-stu-id="181ea-117">The engine will evaluate the rule against the various combinations of the instances.</span></span> <span data-ttu-id="181ea-118">想定されるので、 **Father**と**Son**インスタンスがある同じ姓で、 **Son**インスタンスに追加されます、 **Father**インスタンスとして対象としています。</span><span class="sxs-lookup"><span data-stu-id="181ea-118">Assuming that the **Father** and **Son** instance have the same surname, the **Son** instance will be added to the **Father** instance as intended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="181ea-119">**インスタンス ID**は、特定の規則の評価のコンテキスト内でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="181ea-119">The **Instance ID** is only used within the context of a given rule evaluation.</span></span> <span data-ttu-id="181ea-120">インスタンス ID は、ポリシーの実行中にオブジェクトのインスタンスに添付されません。また、オブジェクトがアサートされる順番との関連性はありません。</span><span class="sxs-lookup"><span data-stu-id="181ea-120">It is not affixed to an object instance across the policy execution and is not related to the order in which objects are asserted.</span></span> <span data-ttu-id="181ea-121">各オブジェクト インスタンスは、この種類に対するすべてのルールの引数で評価されます。</span><span class="sxs-lookup"><span data-stu-id="181ea-121">Each object instance will be evaluated in all rule arguments for that type.</span></span>