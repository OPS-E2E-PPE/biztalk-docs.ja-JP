---
title: "フォールト メッセージ 2 を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fault messages, adding
- messages, fault messages
ms.assetid: 8f1b40af-2c75-4167-8b62-a86b791907c9
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dee8a1fca0e30a96b6a714b5c717c0638bc8144
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-fault-message"></a><span data-ttu-id="83cc8-102">エラー メッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="83cc8-102">How to Add a Fault Message</span></span>
<span data-ttu-id="83cc8-103">作成したバックエンド システムへのポートには、要求と応答が含まれています。</span><span class="sxs-lookup"><span data-stu-id="83cc8-103">When you create a port to the back-end system, it contains a request and a response.</span></span> <span data-ttu-id="83cc8-104">エラーに割り当てることができるように、メッセージを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83cc8-104">You must add a message so that you can assign it to the fault.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="83cc8-105">エラー メッセージを追加するには</span><span class="sxs-lookup"><span data-stu-id="83cc8-105">To add a fault message</span></span>  
  
1.  <span data-ttu-id="83cc8-106">**オーケストレーション**ウィンドウを右クリックして**メッセージ**を選択し、**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="83cc8-106">In the **Orchestration View** window, right-click **Messages**, and select **New Message**.</span></span>  
  
     <span data-ttu-id="83cc8-107">これにより Message_3 が作成され、このエラーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="83cc8-107">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="83cc8-108">Message_3 を右クリックし **プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="83cc8-108">Right-click Message_3, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="83cc8-109">**プロパティ**ダイアログ ボックスで、設定、**メッセージの種類**です。</span><span class="sxs-lookup"><span data-stu-id="83cc8-109">In the **Properties** dialog box, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="83cc8-110">選択**.NET クラス**し、 **SystemString**です。</span><span class="sxs-lookup"><span data-stu-id="83cc8-110">Select **.NET Classes** and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83cc8-111">参照</span><span class="sxs-lookup"><span data-stu-id="83cc8-111">See Also</span></span>  
 [<span data-ttu-id="83cc8-112">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="83cc8-112">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)