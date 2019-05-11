---
title: メッセージのメッセージの割り当て図形内の参照 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, code samples
- code samples, messages
- messages, objects
ms.assetid: 428f7eb8-001e-4147-b1c8-f9bb6f3a80f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d74aea98cb780ba8ef81e0329f12fbd7685878f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324998"
---
# <a name="message-references-in-message-assignment-shape"></a><span data-ttu-id="0f61f-102">メッセージの割り当て図形のメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="0f61f-102">Message References in Message Assignment Shape</span></span>
<span data-ttu-id="0f61f-103">割り当てるとき、します。NET ベースのオブジェクトをメッセージまたはメッセージ部分は、そのメッセージを保持し、オブジェクトへの参照を保持します。</span><span class="sxs-lookup"><span data-stu-id="0f61f-103">When you first assign a .NET-based object to a message or message part, that message holds and maintains a reference to the object.</span></span>  
  
 <span data-ttu-id="0f61f-104">効率性とスケーラビリティは、オーケストレーション エンジンは行いませんオブジェクトの「ディープ コピー」します。 つまり、その内容をコピーしません、全体オブジェクトのメッセージにします。</span><span class="sxs-lookup"><span data-stu-id="0f61f-104">For efficiency and scalability, the orchestration engine does not do a "deep copy" of the object: that is, it does not copy the entire contents of the object to the message.</span></span>  
  
 <span data-ttu-id="0f61f-105">その後、別のメッセージにオブジェクトを割り当てるまたはメッセージ部分場合、は、2 番目のメッセージまたはメッセージ部分への変更で元への変更が発生します。</span><span class="sxs-lookup"><span data-stu-id="0f61f-105">If you subsequently assign the object to another message or message part, any modifications to the original results in modifications to the second message or message part.</span></span> <span data-ttu-id="0f61f-106">結果は予測できませんので、この実習を避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f61f-106">You should avoid this practice, because results are unpredictable.</span></span>  
  
 <span data-ttu-id="0f61f-107">オブジェクトの個別のコピーが 2 番目のメッセージが必要な場合は、2 番目のメッセージまたはメッセージ部分を最初のメッセージまたはメッセージ部分を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f61f-107">If you need your second message to have a distinct copy of the object, you should assign the first message or message part to the second message or message part.</span></span>  
  
 <span data-ttu-id="0f61f-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0f61f-108">Consider the following example:</span></span>  
  
 <span data-ttu-id="0f61f-109">間違っています。</span><span class="sxs-lookup"><span data-stu-id="0f61f-109">Wrong way:</span></span>  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myObj; // assign the second message (wrong!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 <span data-ttu-id="0f61f-110">この場合は、myMsg2.myInt は上書きされてし、値 5 ようになりました。</span><span class="sxs-lookup"><span data-stu-id="0f61f-110">In this case, myMsg2.myInt has been overwritten, and now has the value 5.</span></span>  
  
 <span data-ttu-id="0f61f-111">正しい構文:</span><span class="sxs-lookup"><span data-stu-id="0f61f-111">Right way:</span></span>  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myMsg1; // assign the second message (right!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 <span data-ttu-id="0f61f-112">この場合は、mymsg2.myint の値は 100 期待どおりにします。</span><span class="sxs-lookup"><span data-stu-id="0f61f-112">In this case, myMsg2.myInt still has the value 100, as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f61f-113">参照</span><span class="sxs-lookup"><span data-stu-id="0f61f-113">See Also</span></span>  
 [<span data-ttu-id="0f61f-114">メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="0f61f-114">Constructing Messages</span></span>](../core/constructing-messages.md)