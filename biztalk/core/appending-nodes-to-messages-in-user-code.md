---
title: ユーザー コードでのメッセージへのノードの追加 |Microsoft Docs
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
ms.openlocfilehash: 6dacbe06634748590be17ca8cd668e0825de1880
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359652"
---
# <a name="appending-nodes-to-messages-in-user-code"></a><span data-ttu-id="f9451-102">ユーザー コード内のメッセージにノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f9451-102">Appending Nodes to Messages in User Code</span></span>
<span data-ttu-id="f9451-103">BizTalk Server がメッセージを処理する方法、により、既存のメッセージに直接新しいノードを追加することだけだことはできません。</span><span class="sxs-lookup"><span data-stu-id="f9451-103">Because of the way BizTalk Server handles messages, you cannot simply append a new node directly to an existing message.</span></span> <span data-ttu-id="f9451-104">代わりに、次のように既存のメッセージを複製する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9451-104">Instead, you must clone the existing message, as follows:</span></span>  
  
```  
myXMLDoc = myExistingMsg; // just holding a reference  
// use CloneNode to make a fresh copy of myModifiedMsg  
myXMLDoc = (XMLDocument)myXMLDoc.CloneNode;  
myXMLDoc.append myNode; // here is the node we want to append  
//update temp message   
myModifiedMsg = myXMLDoc;  
```  
  
 <span data-ttu-id="f9451-105">現在、新しいノードを含む myModifiedMsg を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9451-105">Now you can use myModifiedMsg, which includes the new node.</span></span> <span data-ttu-id="f9451-106">何らかの理由で myExistingMsg を再利用をする場合は、新しい (空) のコピーを作成し、myModifiedMsg を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f9451-106">If for some reason you want to reuse myExistingMsg, you can construct a new (empty) copy and assign myModifiedMsg to it.</span></span>  
  
```  
myExistingMsg = myModifiedMsg;  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9451-107">参照</span><span class="sxs-lookup"><span data-stu-id="f9451-107">See Also</span></span>  
 <span data-ttu-id="f9451-108">[ユーザー コードでメッセージの構築](../core/constructing-messages-in-user-code.md) </span><span class="sxs-lookup"><span data-stu-id="f9451-108">[Constructing Messages in User Code](../core/constructing-messages-in-user-code.md) </span></span>  
 [<span data-ttu-id="f9451-109">メッセージの構築</span><span class="sxs-lookup"><span data-stu-id="f9451-109">Constructing Messages</span></span>](../core/constructing-messages.md)