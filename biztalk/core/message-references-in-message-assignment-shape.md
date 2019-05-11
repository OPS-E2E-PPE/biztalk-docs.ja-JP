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
# <a name="message-references-in-message-assignment-shape"></a>メッセージの割り当て図形のメッセージ参照
割り当てるとき、します。NET ベースのオブジェクトをメッセージまたはメッセージ部分は、そのメッセージを保持し、オブジェクトへの参照を保持します。  
  
 効率性とスケーラビリティは、オーケストレーション エンジンは行いませんオブジェクトの「ディープ コピー」します。 つまり、その内容をコピーしません、全体オブジェクトのメッセージにします。  
  
 その後、別のメッセージにオブジェクトを割り当てるまたはメッセージ部分場合、は、2 番目のメッセージまたはメッセージ部分への変更で元への変更が発生します。 結果は予測できませんので、この実習を避ける必要があります。  
  
 オブジェクトの個別のコピーが 2 番目のメッセージが必要な場合は、2 番目のメッセージまたはメッセージ部分を最初のメッセージまたはメッセージ部分を割り当てる必要があります。  
  
 次に例を示します。  
  
 間違っています。  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myObj; // assign the second message (wrong!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 この場合は、myMsg2.myInt は上書きされてし、値 5 ようになりました。  
  
 正しい構文:  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myMsg1; // assign the second message (right!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 この場合は、mymsg2.myint の値は 100 期待どおりにします。  
  
## <a name="see-also"></a>参照  
 [メッセージの構築](../core/constructing-messages.md)