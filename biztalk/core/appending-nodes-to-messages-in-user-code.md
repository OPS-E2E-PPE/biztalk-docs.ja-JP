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
# <a name="appending-nodes-to-messages-in-user-code"></a>ユーザー コード内のメッセージにノードを追加します。
BizTalk Server がメッセージを処理する方法、により、既存のメッセージに直接新しいノードを追加することだけだことはできません。 代わりに、次のように既存のメッセージを複製する必要があります。  
  
```  
myXMLDoc = myExistingMsg; // just holding a reference  
// use CloneNode to make a fresh copy of myModifiedMsg  
myXMLDoc = (XMLDocument)myXMLDoc.CloneNode;  
myXMLDoc.append myNode; // here is the node we want to append  
//update temp message   
myModifiedMsg = myXMLDoc;  
```  
  
 現在、新しいノードを含む myModifiedMsg を使用できます。 何らかの理由で myExistingMsg を再利用をする場合は、新しい (空) のコピーを作成し、myModifiedMsg を割り当てます。  
  
```  
myExistingMsg = myModifiedMsg;  
```  
  
## <a name="see-also"></a>参照  
 [ユーザー コードでメッセージの構築](../core/constructing-messages-in-user-code.md)   
 [メッセージの構築](../core/constructing-messages.md)