---
title: Exception3 のメッセージを追加する方法 |Microsoft ドキュメント
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
ms.assetid: 920f9b4d-e002-457c-ad44-f41bf2600e06
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ea1bb901437e77d63f42f6dd878bc7f23305a73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246490"
---
# <a name="how-to-add-a-message-for-an-exception"></a><span data-ttu-id="83131-102">例外のメッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="83131-102">How to Add a Message for an Exception</span></span>
<span data-ttu-id="83131-103">メッセージにエラーを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="83131-103">Follow these steps to add a fault with a message.</span></span>  
  
### <a name="to-add-a-message-for-an-exception"></a><span data-ttu-id="83131-104">例外に関するメッセージを追加するには</span><span class="sxs-lookup"><span data-stu-id="83131-104">To add a message for an exception</span></span>  
  
1.  <span data-ttu-id="83131-105">**オーケストレーション ビュー**ウィンドウを右クリックして**メッセージ**選択と**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="83131-105">In the **Orchestration View** window, right-click **Messages** and select **New Message**.</span></span>  
  
     <span data-ttu-id="83131-106">これにより Message_3 が作成され、このエラーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="83131-106">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="83131-107">右クリック**Message_3**選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="83131-107">Right-click **Message_3** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="83131-108">**プロパティ**ダイアログ ボックスで、設定、**メッセージの種類**です。</span><span class="sxs-lookup"><span data-stu-id="83131-108">In the **Properties** dialog box, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="83131-109">選択 **.NET クラス**、し、 **SystemString**です。</span><span class="sxs-lookup"><span data-stu-id="83131-109">Select **.NET Classes**, and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83131-110">参照</span><span class="sxs-lookup"><span data-stu-id="83131-110">See Also</span></span>  
 [<span data-ttu-id="83131-111">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="83131-111">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling4.md)