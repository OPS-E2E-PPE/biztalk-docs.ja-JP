---
title: プリミティブ .NET 型から Web メッセージ部分を構築する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, Web messages
- Web messages, Message Assignment shape [Orchestration Designer]
- Web messages, creating
- Message Assignment shape [Orchestration Designer], Web messages
- Web messages, parts
- Web messages, .NET types
ms.assetid: 1fe52412-d2bc-484c-8925-c7ff3ca7704b
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ab2390ea0e053fadcd275d8be7c1eea6ea6e903
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340194"
---
# <a name="how-to-construct-a-web-message-part-from-a-primitive-net-type"></a>プリミティブ .NET 型から Web メッセージ部分を構築する方法
使用して、プリミティブ .NET 型から Web メッセージ部分を作成する、**メッセージの割り当て**図形。 または、部分を設定する .NET ヘルパー クラスを使用して、プリミティブ .NET 型から Web メッセージ部分を作成できます。 .NET クラスを使用してメッセージの種類を作成する方法の詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。  
  
### <a name="to-construct-a-web-message-part-from-a-primitive-net-type"></a>プリミティブ .NET 型から Web メッセージ部分を構築するには  
  
1.  オーケストレーションを開きを開き、**ツールボックス** をクリックし、 **BizTalk オーケストレーション**タブ。  
  
2.  ドラッグ、**メッセージの構築**オーケストレーションへの図形。  
  
3.  編集、**メッセージ構築**プロパティを Web メッセージの種類用に作成されたメッセージ インスタンスが含まれます。  
  
4.  ドラッグ、**メッセージの割り当て**図形の上に、**メッセージの構築**図形。  
  
5.  ダブルクリックして、**メッセージの割り当て**図形、BizTalk 式エディターを開きます。  
  
6.  BizTalk 式エディターの Web メッセージの種類の部分を必要な値に設定します。  
  
     たとえば、次のコードでは、文字列に式を設定します。  
  
    ```  
    ItemAvailRequestInstance.Item_ID = "This is Item_ID.";  
    ```  
  
## <a name="see-also"></a>参照  
 [Web メッセージの構築](../core/constructing-web-messages.md)