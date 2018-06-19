---
title: ユーザー コード内のメッセージにノードを追加する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, nodes
- messages, cloning
ms.assetid: 636e0064-095e-49d1-850f-eaee0f0ffe77
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0376094f31478c74a408eacab6c363ce22c9d2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229978"
---
# <a name="appending-nodes-to-messages-in-user-code"></a><span data-ttu-id="c01df-102">ユーザー コード内のメッセージにノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c01df-102">Appending Nodes to Messages in User Code</span></span>
<span data-ttu-id="c01df-103">BizTalk Server でのメッセージの処理方法により、新しいノードを既存のメッセージに直接追加することは単純にはできません。</span><span class="sxs-lookup"><span data-stu-id="c01df-103">Because of the way BizTalk Server handles messages, you cannot simply append a new node directly to an existing message.</span></span> <span data-ttu-id="c01df-104">代わりに、次のように既存のメッセージを複製する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c01df-104">Instead, you must clone the existing message, as follows:</span></span>  
  
```  
myXMLDoc = myExistingMsg; // just holding a reference  
// use CloneNode to make a fresh copy of myModifiedMsg  
myXMLDoc = (XMLDocument)myXMLDoc.CloneNode;  
myXMLDoc.append myNode; // here is the node we want to append  
//update temp message   
myModifiedMsg = myXMLDoc;  
```  
  
 <span data-ttu-id="c01df-105">これで新しいノードを含む myModifiedMsg を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="c01df-105">Now you can use myModifiedMsg, which includes the new node.</span></span> <span data-ttu-id="c01df-106">何らかの理由で myExistingMsg を再利用する場合は、新しい (空の) コピーを作成して myModifiedMsg をそのコピーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c01df-106">If for some reason you want to reuse myExistingMsg, you can construct a new (empty) copy and assign myModifiedMsg to it.</span></span>  
  
```  
myExistingMsg = myModifiedMsg;  
```  
  
## <a name="see-also"></a><span data-ttu-id="c01df-107">参照</span><span class="sxs-lookup"><span data-stu-id="c01df-107">See Also</span></span>  
 <span data-ttu-id="c01df-108">[ユーザー コードでメッセージの構築](../core/constructing-messages-in-user-code.md) </span><span class="sxs-lookup"><span data-stu-id="c01df-108">[Constructing Messages in User Code](../core/constructing-messages-in-user-code.md) </span></span>  
 [<span data-ttu-id="c01df-109">メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="c01df-109">Constructing Messages</span></span>](../core/constructing-messages.md)