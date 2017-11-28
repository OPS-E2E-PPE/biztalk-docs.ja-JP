---
title: "ビジネス ルールの ArrayList を反復処理する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, ArrayList
- business rules, arrays
- Business Rules Framework, programming
ms.assetid: 935e8648-72dc-4128-986c-72b0487bc074
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 95896b63e5bb982a4778b05970900c989ebc66b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-iterate-arraylist-in-business-rules"></a><span data-ttu-id="4a4c6-102">ビジネス ルールの ArrayList を反復処理する方法</span><span class="sxs-lookup"><span data-stu-id="4a4c6-102">How to Iterate ArrayList in Business Rules</span></span>
<span data-ttu-id="4a4c6-103">このセクションでは、メンバーを反復処理する、 **ArrayList**でビジネス ルール。</span><span class="sxs-lookup"><span data-stu-id="4a4c6-103">This section provides an example of iterating through members of an **ArrayList** in business rules.</span></span>  
  
 <span data-ttu-id="4a4c6-104">あると、 **ArrayList**の一連の**MyClass**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="4a4c6-104">Assume you have an **ArrayList** with a collection of **MyClass** objects.</span></span> <span data-ttu-id="4a4c6-105">ビジネス ルールは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="4a4c6-105">Your business rules would look like the following.</span></span>  
  
## <a name="rule-a"></a><span data-ttu-id="4a4c6-106">ルール A</span><span class="sxs-lookup"><span data-stu-id="4a4c6-106">Rule A</span></span>  
 <span data-ttu-id="4a4c6-107">IF 1==1</span><span class="sxs-lookup"><span data-stu-id="4a4c6-107">IF 1==1</span></span>  
  
 <span data-ttu-id="4a4c6-108">THEN Assert (ArrayList.GetEnumerator)</span><span class="sxs-lookup"><span data-stu-id="4a4c6-108">THEN Assert (ArrayList.GetEnumerator)</span></span>  
  
 <span data-ttu-id="4a4c6-109">**IEnumerator**ために、型が作業メモリにアサートされるルールの条件 (1 = = 1) 常に true に評価します。</span><span class="sxs-lookup"><span data-stu-id="4a4c6-109">An **IEnumerator** type is asserted into the working memory, because the rule condition (1==1) always evaluates to true.</span></span>  
  
## <a name="rule-b"></a><span data-ttu-id="4a4c6-110">ルール B</span><span class="sxs-lookup"><span data-stu-id="4a4c6-110">Rule B</span></span>  
 <span data-ttu-id="4a4c6-111">IF IEnumerator.MoveNext</span><span class="sxs-lookup"><span data-stu-id="4a4c6-111">IF IEnumerator.MoveNext</span></span>  
  
 <span data-ttu-id="4a4c6-112">THEN    Assert (IEnumerator.get_Current)</span><span class="sxs-lookup"><span data-stu-id="4a4c6-112">THEN    Assert (IEnumerator.get_Current)</span></span>  
  
 <span data-ttu-id="4a4c6-113">Update (IEnumerator)</span><span class="sxs-lookup"><span data-stu-id="4a4c6-113">Update (IEnumerator)</span></span>  
  
 <span data-ttu-id="4a4c6-114">反復処理ルールとして、 **ArrayList**、各**MyClass**コレクション内のオブジェクトが作業メモリにアサートします。</span><span class="sxs-lookup"><span data-stu-id="4a4c6-114">As the rule iterates through the **ArrayList**, each **MyClass** object in the collection is asserted into the working memory.</span></span>  
  
## <a name="rule-c"></a><span data-ttu-id="4a4c6-115">ルール C</span><span class="sxs-lookup"><span data-stu-id="4a4c6-115">Rule C</span></span>  
 <span data-ttu-id="4a4c6-116">IF MyClass.MyProperty==2</span><span class="sxs-lookup"><span data-stu-id="4a4c6-116">IF MyClass.MyProperty==2</span></span>  
  
 <span data-ttu-id="4a4c6-117">\<何らかの処理を行う ></span><span class="sxs-lookup"><span data-stu-id="4a4c6-117">THEN \<Do Something...></span></span>  
  
 <span data-ttu-id="4a4c6-118">オブジェクトのプロパティの値が条件に一致する場合に、このルールは、アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4a4c6-118">This rule executes action(s) when the property value of the object is matched in the condition.</span></span>