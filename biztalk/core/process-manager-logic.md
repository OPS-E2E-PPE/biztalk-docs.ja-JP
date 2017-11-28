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
# <a name="process-manager-logic"></a><span data-ttu-id="30b54-102">プロセス マネージャのロジック</span><span class="sxs-lookup"><span data-stu-id="30b54-102">Process Manager Logic</span></span>
<span data-ttu-id="30b54-103">このセクションについて説明方法、プロセス マネージャ、 **OrderManager**オーケストレーションで、注文が処理されます。</span><span class="sxs-lookup"><span data-stu-id="30b54-103">This section describes how the process manager, the **OrderManager** orchestration, processes orders.</span></span> <span data-ttu-id="30b54-104">各種の注文メッセージに含まれる主要なフィールドや、オーケストレーションにおける新しい注文と更新された注文の処理について説明します。</span><span class="sxs-lookup"><span data-stu-id="30b54-104">It describes key fields in the various order messages and follows new and updated orders through the orchestration.</span></span>  
  
 <span data-ttu-id="30b54-105">**OrderManager**オーケストレーションが注文を処理する下位のオーケストレーションを調整します。</span><span class="sxs-lookup"><span data-stu-id="30b54-105">The **OrderManager** orchestration coordinates subordinate orchestrations to process the order.</span></span> <span data-ttu-id="30b54-106">追加、削除、または変更することがなくこれらのステージを変更することができます、 **OrderManager**です。</span><span class="sxs-lookup"><span data-stu-id="30b54-106">You can add, delete, or modify these stages without having to change the **OrderManager**.</span></span> <span data-ttu-id="30b54-107">**OrderManager** .NET クラスによって定義されたカスタム メッセージを介して調整のほとんどはします。</span><span class="sxs-lookup"><span data-stu-id="30b54-107">The **OrderManager** does much of the coordination through custom messages defined by .NET classes.</span></span> <span data-ttu-id="30b54-108">ソリューション内のすべてのメッセージの一覧は、次を参照してください。[ビジネス プロセス管理ソリューションのメッセージ リファレンス](../core/message-reference-for-the-business-process-management-solution.md)です。</span><span class="sxs-lookup"><span data-stu-id="30b54-108">For a list of all messages in the solution, see [Message Reference for the Business Process Management Solution](../core/message-reference-for-the-business-process-management-solution.md).</span></span> <span data-ttu-id="30b54-109">.NET クラスによるメッセージの種類の定義については、次を参照してください。[ユーザー コードでメッセージを構築する](../core/constructing-messages-in-user-code.md)です。</span><span class="sxs-lookup"><span data-stu-id="30b54-109">For information about defining message types with .NET classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30b54-110">規模のスコープであるため**OrderManager**、これらのセクションでは、特に 2 番目は、Microsoft Visual Studio でオーケストレーションを開いてを参照することがあります。</span><span class="sxs-lookup"><span data-stu-id="30b54-110">Because of the size and scope of **OrderManager**, you may want to read these sections, especially the second, with the orchestration open in Microsoft Visual Studio.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="30b54-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="30b54-111">In This Section</span></span>  
  
-   [<span data-ttu-id="30b54-112">キー メッセージおよびフィールド</span><span class="sxs-lookup"><span data-stu-id="30b54-112">Key Messages and Fields</span></span>](../core/key-messages-and-fields.md)  
  
-   [<span data-ttu-id="30b54-113">プロセス マネージャでの注文の流れ</span><span class="sxs-lookup"><span data-stu-id="30b54-113">Order Flow through the Process Manager</span></span>](../core/order-flow-through-the-process-manager.md)