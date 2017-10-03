---
title: "プリミティブ .NET 型から Web メッセージ部分を構築する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, Message Assignment shape [Orchestration Designer]
- Web messages, creating
- Message Assignment shape [Orchestration Designer], Web messages
- Web messages, parts
- Web messages, .NET types
ms.assetid: 1fe52412-d2bc-484c-8925-c7ff3ca7704b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991970d5b0d40da1ec00b54919d2742cfd48353c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-construct-a-web-message-part-from-a-primitive-net-type"></a>プリミティブ .NET 型から Web メッセージ部分を構築する方法
使用して、プリミティブ .NET 型から Web メッセージ部分を作成する、**メッセージの割り当て**図形です。 Web メッセージ部分を設定する .NET ヘルパー クラスを使用して、プリミティブ .NET 型からその部分を作成することもできます。 .NET クラスを使用してメッセージの種類を作成する方法の詳細については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。  
  
### <a name="to-construct-a-web-message-part-from-a-primitive-net-type"></a>プリミティブ .NET 型から Web メッセージ部分を構築するには  
  
1.  オーケストレーションを開き、開き、**ツールボックス** をクリックし、 **BizTalk オーケストレーション**タブです。  
  
2.  ドラッグ、**メッセージの構築**オーケストレーションへの図形です。  
  
3.  編集、**メッセージ構築**プロパティを Web メッセージの種類用に作成したメッセージ インスタンスが含まれます。  
  
4.  ドラッグ、**メッセージの割り当て**図形の上に、**メッセージの構築**図形です。  
  
5.  ダブルクリックして、**メッセージの割り当て**図形を BizTalk 式エディタを開きます。  
  
6.  [BizTalk 式エディタ] ボックスで、Web メッセージの種類の部分を必要な値に設定します。  
  
     たとえば、次のコードは式を文字列に設定します。  
  
    ```  
    ItemAvailRequestInstance.Item_ID = "This is Item_ID.";  
    ```  
  
## <a name="see-also"></a>参照  
 [Web メッセージの構築](../core/constructing-web-messages.md)