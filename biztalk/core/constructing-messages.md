---
title: "メッセージの構築 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, messages
- multi-part message types
- messages, modifying
- multi-part message types, about multi-part message types
- modifying, messages
- messages, creating
ms.assetid: c9fc1e97-ff53-42e2-848c-6c8fae7c9122
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923fa87c4f3400a80ce83df132747d0004232323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="constructing-messages"></a>メッセージの構築
オーケストレーションにメッセージを導入する場合は常に、メッセージを受信するか、メッセージ変数に値を割り当てることによって、メッセージを構築します。 使用するオブジェクトの詳細な説明がランタイム エンジンによって認識されるように、構築するメッセージにはメッセージの種類を指定する必要があります。 マルチパート メッセージの種類には、ユーザー定義、.NET クラス、またはスキーマを指定できます。 さまざまな方法でメッセージを構築することができます。 メッセージを作成、間、1 つのメッセージを割り当てる、またはメッセージ内の特定の値を別のメッセージ内の値にマップする変換を使用する .NET クラスを呼び出すことができます。 また、メッセージは、受信アクションによって構築されたり、オーケストレーションがパラメーターとしてメッセージを受け取るときに構築されたりします。  
  
> [!NOTE]
>  マルチパート メッセージの種類に含める部分は、複数とは限りません。1 つだけの場合もあります。  
  
> [!IMPORTANT]
>  BizTalk 内ではメッセージは不変です。つまり、作成した後に元のメッセージに変更を加えることはできません。 変更する必要がある場合は、メッセージの新しいコピーを構築して、適切な値を割り当てる必要があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [メッセージの構築図形を構成する方法](../core/how-to-configure-the-construct-message-shape.md)  
  
 [メッセージの割り当て図形を構成する方法](../core/how-to-configure-the-message-assignment-shape.md) 
  
 [変換図形を構成する方法](../core/how-to-configure-the-transform-shape.md) 
  
 [メッセージの割り当て図形でメッセージ参照](../core/message-references-in-message-assignment-shape.md)  
  
 [ユーザー コードでのメッセージ参照](../core/message-references-in-user-code.md)  
  
 [メッセージ割り当てにおける Xpath の使用](../core/using-xpaths-in-message-assignments.md)  
  
 [メッセージ割り当てにおける非正規 Xpath の使用](../core/using-non-canonical-xpaths-in-message-assignments.md)  
  
 [ユーザー コードでメッセージの構築](../core/constructing-messages-in-user-code.md)  
  
 [ユーザー コード内のメッセージにノードを追加します。](../core/appending-nodes-to-messages-in-user-code.md)  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでメッセージの使用](../core/using-messages-in-orchestrations.md)