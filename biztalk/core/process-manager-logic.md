---
title: プロセス マネージャのロジック |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 6b69fc71-0f01-4513-9361-d7787d0cde6d
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9894c2201ab9a96559188fd102ec585fafd5afd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396673"
---
# <a name="process-manager-logic"></a>プロセス マネージャのロジック
このセクションの説明方法、プロセス マネージャの**OrderManager**オーケストレーションで、注文が処理します。 各種の注文メッセージ内のキー フィールドについて説明し、オーケストレーションで注文を新規および更新に依存します。  
  
 **OrderManager**オーケストレーションが注文を処理する下位のオーケストレーションを調整します。 追加、削除、または変更することがなくこれらのステージを変更することができます、 **OrderManager**します。 **OrderManager**は .NET クラスによって定義されたカスタム メッセージを介して調整を行います。 ソリューション内のすべてのメッセージの一覧は、次を参照してください。 [、ビジネス プロセス管理ソリューションのメッセージ リファレンス](../core/message-reference-for-the-business-process-management-solution.md)します。 .NET クラスによるメッセージの種類を定義する方法の詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。  
  
> [!NOTE]
>  サイズとスコープの**OrderManager**、特に、秒であり、Microsoft Visual Studio でオーケストレーションを開いて、これらのセクションを読みたい場合があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [主要メッセージとフィールド](../core/key-messages-and-fields.md)  
  
-   [プロセス マネージャーでの注文の流れ](../core/order-flow-through-the-process-manager.md)