---
title: Exception2 のメッセージを追加する方法 |Microsoft Docs
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
- exception handling, adding messages
- fault messages, adding
ms.assetid: 9d8a3801-78cd-4c18-8deb-3fbe4a49a2f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57cd4e3e0cdcfe34dd172282ef83768eb63b93fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000801"
---
# <a name="how-to-add-a-message-for-an-exception"></a><span data-ttu-id="522eb-102">例外のメッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="522eb-102">How to Add a Message for an Exception</span></span>
<span data-ttu-id="522eb-103">最初に作成したバックエンド システムへのポートには、要求と応答が含まれています。</span><span class="sxs-lookup"><span data-stu-id="522eb-103">When you first create a port to the back-end system, it contains a request and a response.</span></span> <span data-ttu-id="522eb-104">エラーに割り当てることができるように、メッセージを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="522eb-104">You must add a message so that you can assign it to the fault.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="522eb-105">エラー メッセージを追加するには</span><span class="sxs-lookup"><span data-stu-id="522eb-105">To add a fault message</span></span>  
  
1. <span data-ttu-id="522eb-106">**オーケストレーション**ウィンドウで、右クリック**メッセージ**、し、**新しいメッセージ**。</span><span class="sxs-lookup"><span data-stu-id="522eb-106">In the **Orchestration View** window, right-click **Messages**, and then select **New Message**.</span></span>  
  
    <span data-ttu-id="522eb-107">これにより Message_3 が作成され、このエラーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="522eb-107">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2. <span data-ttu-id="522eb-108">右クリック**Message_3**、選び**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="522eb-108">Right-click **Message_3**, and select **Properties**.</span></span>  
  
3. <span data-ttu-id="522eb-109">設定、**メッセージの種類**よう: 選択 **.NET クラス**、し、 **System, String**</span><span class="sxs-lookup"><span data-stu-id="522eb-109">Set the **Message Type** as follows: select **.NET Classes**, and then select **System,String**</span></span>  
  
   <span data-ttu-id="522eb-110">![](../core/media/jdeoneworld-03-addscope.gif "JdeOneWorld_03_addscope")</span><span class="sxs-lookup"><span data-stu-id="522eb-110">![](../core/media/jdeoneworld-03-addscope.gif "JdeOneWorld_03_addscope")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="522eb-111">参照</span><span class="sxs-lookup"><span data-stu-id="522eb-111">See Also</span></span>  
 [<span data-ttu-id="522eb-112">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="522eb-112">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)