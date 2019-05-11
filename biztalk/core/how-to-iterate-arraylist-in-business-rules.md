---
title: ビジネス ルールの ArrayList の繰り返し処理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, ArrayList
- business rules, arrays
- Business Rules Framework, programming
ms.assetid: 935e8648-72dc-4128-986c-72b0487bc074
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9753ce1208312ade51950cd36a1df4210d763268
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384883"
---
# <a name="how-to-iterate-arraylist-in-business-rules"></a><span data-ttu-id="230b2-102">ビジネス ルールの ArrayList の繰り返し処理する方法</span><span class="sxs-lookup"><span data-stu-id="230b2-102">How to Iterate ArrayList in Business Rules</span></span>
<span data-ttu-id="230b2-103">このセクションがのメンバーを反復処理の例では、 **ArrayList**でビジネス ルール。</span><span class="sxs-lookup"><span data-stu-id="230b2-103">This section provides an example of iterating through members of an **ArrayList** in business rules.</span></span>  
  
 <span data-ttu-id="230b2-104">あると、 **ArrayList**のコレクションを持つ**MyClass**オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="230b2-104">Assume you have an **ArrayList** with a collection of **MyClass** objects.</span></span> <span data-ttu-id="230b2-105">ビジネス ルールは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="230b2-105">Your business rules would look like the following.</span></span>  
  
## <a name="rule-a"></a><span data-ttu-id="230b2-106">ルール A</span><span class="sxs-lookup"><span data-stu-id="230b2-106">Rule A</span></span>  
 <span data-ttu-id="230b2-107">場合 1 1 = =</span><span class="sxs-lookup"><span data-stu-id="230b2-107">IF 1==1</span></span>  
  
 <span data-ttu-id="230b2-108">(ArrayList.GetEnumerator) ことをアサートします。</span><span class="sxs-lookup"><span data-stu-id="230b2-108">THEN Assert (ArrayList.GetEnumerator)</span></span>  
  
 <span data-ttu-id="230b2-109">**IEnumerator**のため、型が、作業メモリにアサートされるルールの条件 (1 1 = =) 常に true に評価されます。</span><span class="sxs-lookup"><span data-stu-id="230b2-109">An **IEnumerator** type is asserted into the working memory, because the rule condition (1==1) always evaluates to true.</span></span>  
  
## <a name="rule-b"></a><span data-ttu-id="230b2-110">ルール B</span><span class="sxs-lookup"><span data-stu-id="230b2-110">Rule B</span></span>  
 <span data-ttu-id="230b2-111">IF IEnumerator.MoveNext</span><span class="sxs-lookup"><span data-stu-id="230b2-111">IF IEnumerator.MoveNext</span></span>  
  
 <span data-ttu-id="230b2-112">THEN    Assert (IEnumerator.get_Current)</span><span class="sxs-lookup"><span data-stu-id="230b2-112">THEN    Assert (IEnumerator.get_Current)</span></span>  
  
 <span data-ttu-id="230b2-113">更新プログラム (IEnumerator)</span><span class="sxs-lookup"><span data-stu-id="230b2-113">Update (IEnumerator)</span></span>  
  
 <span data-ttu-id="230b2-114">反復処理ルールとして、 **ArrayList**、それぞれ**MyClass**コレクション内のオブジェクトが作業メモリにアサートされます。</span><span class="sxs-lookup"><span data-stu-id="230b2-114">As the rule iterates through the **ArrayList**, each **MyClass** object in the collection is asserted into the working memory.</span></span>  
  
## <a name="rule-c"></a><span data-ttu-id="230b2-115">ルール C</span><span class="sxs-lookup"><span data-stu-id="230b2-115">Rule C</span></span>  
 <span data-ttu-id="230b2-116">IF MyClass.MyProperty==2</span><span class="sxs-lookup"><span data-stu-id="230b2-116">IF MyClass.MyProperty==2</span></span>  
  
 <span data-ttu-id="230b2-117">\<処理を実行しています.\></span><span class="sxs-lookup"><span data-stu-id="230b2-117">THEN \<Do Something...\></span></span>  
  
 <span data-ttu-id="230b2-118">このルールは、オブジェクトのプロパティの値が条件に一致したときにアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="230b2-118">This rule executes action(s) when the property value of the object is matched in the condition.</span></span>