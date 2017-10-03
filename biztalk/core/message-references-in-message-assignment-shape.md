---
title: "メッセージの割り当て図形内の参照をメッセージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, code samples
- code samples, messages
- messages, objects
ms.assetid: 428f7eb8-001e-4147-b1c8-f9bb6f3a80f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b834eefa991b6cad89a04a836f63d1b9af73fc04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="message-references-in-message-assignment-shape"></a>メッセージの割り当て図形でメッセージ参照
最初に .NET ベースのオブジェクトをメッセージまたはメッセージ部分に割り当てたときに、メッセージでオブジェクトへの参照が保持および維持されます。  
  
 効率性とスケーラビリティは、オーケストレーション エンジンで実行しないオブジェクトの「ディープ コピー」: は、その内容をコピーしません、全体のオブジェクトのメッセージにします。  
  
 その後、オブジェクトを別のメッセージまたはメッセージ部分に割り当てる場合、元のオブジェクトに変更があると、2 番目のメッセージまたはメッセージ部分を変更することになります。 この操作は結果を予測できないため、使用しないでください。  
  
 2 番目のメッセージでオブジェクトの明確なコピーが必要な場合は、最初のメッセージまたはメッセージ部分を 2 番目のメッセージまたはメッセージ部分に割り当てる必要があります。  
  
 次の例を参照してください。  
  
 間違っている構文 :   
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myObj; // assign the second message (wrong!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 この場合は、myMsg2.myInt は上書きされていて、値 5 が設定されます。  
  
 正しい構文 :   
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myMsg1; // assign the second message (right!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 この場合は、想定どおり、myMsg2.myInt の値は 100 のままです。  
  
## <a name="see-also"></a>参照  
 [メッセージの構築](../core/constructing-messages.md)