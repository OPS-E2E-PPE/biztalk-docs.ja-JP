---
title: メッセージの構築 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, messages
- multi-part message types
- messages, modifying
- multi-part message types, about multi-part message types
- modifying, messages
- messages, creating
ms.assetid: c9fc1e97-ff53-42e2-848c-6c8fae7c9122
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c2267863facd50af0f2c2c018d158fa6ee678cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354634"
---
# <a name="constructing-messages"></a>メッセージの構築
いつでもメッセージを受信するか、メッセージ変数に値を割り当てることで、オーケストレーションに導入すること、メッセージを作成します。 すべてのメッセージを構築することは、ランタイム エンジンがある操作しているオブジェクトの完全な説明できるように、メッセージの種類にすることが必要です。 マルチパート メッセージの種類は、ユーザー定義、おくと、.NET クラスまたはスキーマを指定できます。 さまざまな方法でメッセージを構築することができます。 メッセージを作成、間、1 つのメッセージを割り当てる、またはメッセージ内の特定の値を別のメッセージ内の値にマップする変換を使用する .NET クラスを呼び出すことができます。 メッセージは、受信アクションまたはオーケストレーションがパラメーターとしてメッセージを受け入れる場合にも作成されます。  
  
> [!NOTE]
>  必ずしも、マルチパート メッセージの種類に複数の部分が含まれていません。1 つだけを含めることがあります。  
  
> [!IMPORTANT]
>  メッセージは BizTalk; に変更できません。つまり、これを作成した後、元は変更できません。 変更する必要がある場合は、メッセージの新しいコピーを作成およびを適切に値を割り当てる必要があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [メッセージの構築図形を構成する方法](../core/how-to-configure-the-construct-message-shape.md)  
  
 [メッセージの割り当て図形を構成する方法](../core/how-to-configure-the-message-assignment-shape.md) 
  
 [変換図形を構成する方法](../core/how-to-configure-the-transform-shape.md) 
  
 [メッセージの割り当て図形のメッセージ参照](../core/message-references-in-message-assignment-shape.md)  
  
 [ユーザー コードでのメッセージ参照](../core/message-references-in-user-code.md)  
  
 [メッセージ割り当てにおける XPath の使用](../core/using-xpaths-in-message-assignments.md)  
  
 [メッセージ割り当てにおける非正規 XPath の使用](../core/using-non-canonical-xpaths-in-message-assignments.md)  
  
 [ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)  
  
 [ユーザー コードでのメッセージへのノードの追加](../core/appending-nodes-to-messages-in-user-code.md)  
  
## <a name="see-also"></a>参照  
 [オーケストレーションでのメッセージの使用](../core/using-messages-in-orchestrations.md)