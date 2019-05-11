---
title: Exception3 のメッセージを追加する方法 |Microsoft Docs
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
ms.openlocfilehash: 23c2f0fd7b761bb5eeaa3a9ec276de2f2d1ef897
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343787"
---
# <a name="how-to-add-a-message-for-an-exception"></a><span data-ttu-id="24590-102">例外のメッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="24590-102">How to Add a Message for an Exception</span></span>
<span data-ttu-id="24590-103">以下の手順を実行すると、エラー メッセージを追加します。</span><span class="sxs-lookup"><span data-stu-id="24590-103">Follow these steps to add a fault with a message.</span></span>  
  
### <a name="to-add-a-message-for-an-exception"></a><span data-ttu-id="24590-104">例外のメッセージを追加するには</span><span class="sxs-lookup"><span data-stu-id="24590-104">To add a message for an exception</span></span>  
  
1.  <span data-ttu-id="24590-105">**オーケストレーション**ウィンドウを右クリックして**メッセージ**選択と**新しいメッセージ**。</span><span class="sxs-lookup"><span data-stu-id="24590-105">In the **Orchestration View** window, right-click **Messages** and select **New Message**.</span></span>  
  
     <span data-ttu-id="24590-106">これには、エラーに割り当てることができる Message_3 が作成されます。</span><span class="sxs-lookup"><span data-stu-id="24590-106">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="24590-107">右クリック**Message_3**選択**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="24590-107">Right-click **Message_3** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="24590-108">**プロパティ**ダイアログ ボックスで、セット、**メッセージの種類**します。</span><span class="sxs-lookup"><span data-stu-id="24590-108">In the **Properties** dialog box, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="24590-109">選択 **.NET クラス**、し、 **systemstring**します。</span><span class="sxs-lookup"><span data-stu-id="24590-109">Select **.NET Classes**, and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24590-110">参照</span><span class="sxs-lookup"><span data-stu-id="24590-110">See Also</span></span>  
 [<span data-ttu-id="24590-111">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="24590-111">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling4.md)