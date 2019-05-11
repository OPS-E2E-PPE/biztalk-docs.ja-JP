---
title: Exception1 のメッセージを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- messages, exceptions
- faults, adding messages
ms.assetid: e087db39-e745-47d4-a888-0b82a9f855c8
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf7064b77beebdbfdb0fdfc54cf3ba2daa769e08
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343779"
---
# <a name="how-to-add-a-message-for-an-exception"></a><span data-ttu-id="48a5a-102">例外のメッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="48a5a-102">How to Add a Message for an Exception</span></span>
<span data-ttu-id="48a5a-103">次のトピックでは、例外のメッセージを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48a5a-103">The following topic describes how to add a message for an exception.</span></span>  
  
### <a name="to-add-a-message-for-an-exception"></a><span data-ttu-id="48a5a-104">例外のメッセージを追加するには</span><span class="sxs-lookup"><span data-stu-id="48a5a-104">To add a message for an exception</span></span>  
  
1.  <span data-ttu-id="48a5a-105">**オーケストレーション**ウィンドウを右クリックして**メッセージ**選択と**新しいメッセージ**。</span><span class="sxs-lookup"><span data-stu-id="48a5a-105">In the **Orchestration View** window, right-click **Messages** and select **New Message**.</span></span>  
  
     <span data-ttu-id="48a5a-106">これには、エラーに割り当てることができる Message_3 が作成されます。</span><span class="sxs-lookup"><span data-stu-id="48a5a-106">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="48a5a-107">右クリック**Message_3**選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="48a5a-107">Right-click **Message_3** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="48a5a-108">**プロパティ**ウィンドウで、設定、**メッセージの種類**します。</span><span class="sxs-lookup"><span data-stu-id="48a5a-108">In the **Properties** window, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="48a5a-109">選択 **.Net クラス**、し、 **systemstring**します。</span><span class="sxs-lookup"><span data-stu-id="48a5a-109">Select **.Net Classes**, and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48a5a-110">参照</span><span class="sxs-lookup"><span data-stu-id="48a5a-110">See Also</span></span>  
 [<span data-ttu-id="48a5a-111">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="48a5a-111">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)