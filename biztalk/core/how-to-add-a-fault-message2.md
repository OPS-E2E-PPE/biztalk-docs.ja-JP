---
title: フォールト メッセージ 2 を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fault messages, adding
- messages, fault messages
ms.assetid: 8f1b40af-2c75-4167-8b62-a86b791907c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8835098f95c34b506714306afd4c5e7fc42d1b63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387360"
---
# <a name="how-to-add-a-fault-message"></a><span data-ttu-id="a5bb1-102">エラー メッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="a5bb1-102">How to Add a Fault Message</span></span>
<span data-ttu-id="a5bb1-103">バックエンド システムへのポートを作成するときに、要求と応答が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-103">When you create a port to the back-end system, it contains a request and a response.</span></span> <span data-ttu-id="a5bb1-104">エラーに割り当てることができますようにメッセージを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-104">You must add a message so that you can assign it to the fault.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="a5bb1-105">エラー メッセージを追加するには</span><span class="sxs-lookup"><span data-stu-id="a5bb1-105">To add a fault message</span></span>  
  
1.  <span data-ttu-id="a5bb1-106">**オーケストレーション**ウィンドウで、右クリック**メッセージ**を選択し、**新しいメッセージ**。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-106">In the **Orchestration View** window, right-click **Messages**, and select **New Message**.</span></span>  
  
     <span data-ttu-id="a5bb1-107">これには、エラーに割り当てることができる Message_3 が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-107">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="a5bb1-108">Message_3 を右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-108">Right-click Message_3, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="a5bb1-109">**プロパティ**ダイアログ ボックスで、セット、**メッセージの種類**します。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-109">In the **Properties** dialog box, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="a5bb1-110">選択 **.NET クラス**選び **[systemstring]** します。</span><span class="sxs-lookup"><span data-stu-id="a5bb1-110">Select **.NET Classes** and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5bb1-111">参照</span><span class="sxs-lookup"><span data-stu-id="a5bb1-111">See Also</span></span>  
 [<span data-ttu-id="a5bb1-112">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="a5bb1-112">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)