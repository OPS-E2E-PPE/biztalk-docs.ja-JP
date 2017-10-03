---
title: "プロセス マネージャのロジック |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: 6b69fc71-0f01-4513-9361-d7787d0cde6d
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e562362fec8e13589f1860e74024ffe70dad1c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="process-manager-logic"></a>プロセス マネージャのロジック
このセクションについて説明方法、プロセス マネージャ、 **OrderManager**オーケストレーションで、注文が処理されます。 各種の注文メッセージに含まれる主要なフィールドや、オーケストレーションにおける新しい注文と更新された注文の処理について説明します。  
  
 **OrderManager**オーケストレーションが注文を処理する下位のオーケストレーションを調整します。 追加、削除、または変更することがなくこれらのステージを変更することができます、 **OrderManager**です。 **OrderManager** .NET クラスによって定義されたカスタム メッセージを介して調整のほとんどはします。 ソリューション内のすべてのメッセージの一覧は、次を参照してください。[ビジネス プロセス管理ソリューションのメッセージ リファレンス](../core/message-reference-for-the-business-process-management-solution.md)です。 .NET クラスによるメッセージの種類の定義については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。  
  
> [!NOTE]
>  規模のスコープであるため**OrderManager**、これらのセクションでは、特に 2 番目は、Microsoft Visual Studio でオーケストレーションを開いてを参照することがあります。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [キー メッセージおよびフィールド](../core/key-messages-and-fields.md)  
  
-   [プロセス マネージャでの注文の流れ](../core/order-flow-through-the-process-manager.md)