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
# <a name="appending-nodes-to-messages-in-user-code"></a>ユーザー コード内のメッセージにノードを追加します。
BizTalk Server でのメッセージの処理方法により、新しいノードを既存のメッセージに直接追加することは単純にはできません。 代わりに、次のように既存のメッセージを複製する必要があります。  
  
```  
myXMLDoc = myExistingMsg; // just holding a reference  
// use CloneNode to make a fresh copy of myModifiedMsg  
myXMLDoc = (XMLDocument)myXMLDoc.CloneNode;  
myXMLDoc.append myNode; // here is the node we want to append  
//update temp message   
myModifiedMsg = myXMLDoc;  
```  
  
 これで新しいノードを含む myModifiedMsg を使用することができます。 何らかの理由で myExistingMsg を再利用する場合は、新しい (空の) コピーを作成して myModifiedMsg をそのコピーに割り当てることができます。  
  
```  
myExistingMsg = myModifiedMsg;  
```  
  
## <a name="see-also"></a>参照  
 [ユーザー コードでメッセージの構築](../core/constructing-messages-in-user-code.md)   
 [メッセージの構築](../core/constructing-messages.md)