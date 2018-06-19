---
title: メッセージの割り当て図形内の参照をメッセージ |Microsoft ドキュメント
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
ms.openlocfilehash: b834eefa991b6cad89a04a836f63d1b9af73fc04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262810"
---
# <a name="message-references-in-message-assignment-shape"></a><span data-ttu-id="ab92d-102">メッセージの割り当て図形でメッセージ参照</span><span class="sxs-lookup"><span data-stu-id="ab92d-102">Message References in Message Assignment Shape</span></span>
<span data-ttu-id="ab92d-103">最初に .NET ベースのオブジェクトをメッセージまたはメッセージ部分に割り当てたときに、メッセージでオブジェクトへの参照が保持および維持されます。</span><span class="sxs-lookup"><span data-stu-id="ab92d-103">When you first assign a .NET-based object to a message or message part, that message holds and maintains a reference to the object.</span></span>  
  
 <span data-ttu-id="ab92d-104">効率性とスケーラビリティは、オーケストレーション エンジンで実行しないオブジェクトの「ディープ コピー」: は、その内容をコピーしません、全体のオブジェクトのメッセージにします。</span><span class="sxs-lookup"><span data-stu-id="ab92d-104">For efficiency and scalability, the orchestration engine does not do a "deep copy" of the object: that is, it does not copy the entire contents of the object to the message.</span></span>  
  
 <span data-ttu-id="ab92d-105">その後、オブジェクトを別のメッセージまたはメッセージ部分に割り当てる場合、元のオブジェクトに変更があると、2 番目のメッセージまたはメッセージ部分を変更することになります。</span><span class="sxs-lookup"><span data-stu-id="ab92d-105">If you subsequently assign the object to another message or message part, any modifications to the original results in modifications to the second message or message part.</span></span> <span data-ttu-id="ab92d-106">この操作は結果を予測できないため、使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ab92d-106">You should avoid this practice, because results are unpredictable.</span></span>  
  
 <span data-ttu-id="ab92d-107">2 番目のメッセージでオブジェクトの明確なコピーが必要な場合は、最初のメッセージまたはメッセージ部分を 2 番目のメッセージまたはメッセージ部分に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab92d-107">If you need your second message to have a distinct copy of the object, you should assign the first message or message part to the second message or message part.</span></span>  
  
 <span data-ttu-id="ab92d-108">次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab92d-108">Consider the following example:</span></span>  
  
 <span data-ttu-id="ab92d-109">間違っている構文 : </span><span class="sxs-lookup"><span data-stu-id="ab92d-109">Wrong way:</span></span>  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myObj; // assign the second message (wrong!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 <span data-ttu-id="ab92d-110">この場合は、myMsg2.myInt は上書きされていて、値 5 が設定されます。</span><span class="sxs-lookup"><span data-stu-id="ab92d-110">In this case, myMsg2.myInt has been overwritten, and now has the value 5.</span></span>  
  
 <span data-ttu-id="ab92d-111">正しい構文 : </span><span class="sxs-lookup"><span data-stu-id="ab92d-111">Right way:</span></span>  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myMsg1; // assign the second message (right!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 <span data-ttu-id="ab92d-112">この場合は、想定どおり、myMsg2.myInt の値は 100 のままです。</span><span class="sxs-lookup"><span data-stu-id="ab92d-112">In this case, myMsg2.myInt still has the value 100, as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab92d-113">参照</span><span class="sxs-lookup"><span data-stu-id="ab92d-113">See Also</span></span>  
 [<span data-ttu-id="ab92d-114">メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="ab92d-114">Constructing Messages</span></span>](../core/constructing-messages.md)