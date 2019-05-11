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
# <a name="process-manager-logic"></a><span data-ttu-id="e294d-102">プロセス マネージャのロジック</span><span class="sxs-lookup"><span data-stu-id="e294d-102">Process Manager Logic</span></span>
<span data-ttu-id="e294d-103">このセクションの説明方法、プロセス マネージャの**OrderManager**オーケストレーションで、注文が処理します。</span><span class="sxs-lookup"><span data-stu-id="e294d-103">This section describes how the process manager, the **OrderManager** orchestration, processes orders.</span></span> <span data-ttu-id="e294d-104">各種の注文メッセージ内のキー フィールドについて説明し、オーケストレーションで注文を新規および更新に依存します。</span><span class="sxs-lookup"><span data-stu-id="e294d-104">It describes key fields in the various order messages and follows new and updated orders through the orchestration.</span></span>  
  
 <span data-ttu-id="e294d-105">**OrderManager**オーケストレーションが注文を処理する下位のオーケストレーションを調整します。</span><span class="sxs-lookup"><span data-stu-id="e294d-105">The **OrderManager** orchestration coordinates subordinate orchestrations to process the order.</span></span> <span data-ttu-id="e294d-106">追加、削除、または変更することがなくこれらのステージを変更することができます、 **OrderManager**します。</span><span class="sxs-lookup"><span data-stu-id="e294d-106">You can add, delete, or modify these stages without having to change the **OrderManager**.</span></span> <span data-ttu-id="e294d-107">**OrderManager**は .NET クラスによって定義されたカスタム メッセージを介して調整を行います。</span><span class="sxs-lookup"><span data-stu-id="e294d-107">The **OrderManager** does much of the coordination through custom messages defined by .NET classes.</span></span> <span data-ttu-id="e294d-108">ソリューション内のすべてのメッセージの一覧は、次を参照してください。 [、ビジネス プロセス管理ソリューションのメッセージ リファレンス](../core/message-reference-for-the-business-process-management-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="e294d-108">For a list of all messages in the solution, see [Message Reference for the Business Process Management Solution](../core/message-reference-for-the-business-process-management-solution.md).</span></span> <span data-ttu-id="e294d-109">.NET クラスによるメッセージの種類を定義する方法の詳細については、次を参照してください。[ユーザー コードでのメッセージの構築](../core/constructing-messages-in-user-code.md)します。</span><span class="sxs-lookup"><span data-stu-id="e294d-109">For information about defining message types with .NET classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e294d-110">サイズとスコープの**OrderManager**、特に、秒であり、Microsoft Visual Studio でオーケストレーションを開いて、これらのセクションを読みたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="e294d-110">Because of the size and scope of **OrderManager**, you may want to read these sections, especially the second, with the orchestration open in Microsoft Visual Studio.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e294d-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e294d-111">In This Section</span></span>  
  
-   [<span data-ttu-id="e294d-112">主要メッセージとフィールド</span><span class="sxs-lookup"><span data-stu-id="e294d-112">Key Messages and Fields</span></span>](../core/key-messages-and-fields.md)  
  
-   [<span data-ttu-id="e294d-113">プロセス マネージャーでの注文の流れ</span><span class="sxs-lookup"><span data-stu-id="e294d-113">Order Flow through the Process Manager</span></span>](../core/order-flow-through-the-process-manager.md)