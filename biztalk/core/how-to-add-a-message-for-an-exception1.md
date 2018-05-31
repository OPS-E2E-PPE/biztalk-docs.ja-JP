---
title: Exception1 のメッセージを追加する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: b60bfdfb222761aadd54b6c32567dfa6821355ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246594"
---
# <a name="how-to-add-a-message-for-an-exception"></a><span data-ttu-id="c60f3-102">例外のメッセージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="c60f3-102">How to Add a Message for an Exception</span></span>
<span data-ttu-id="c60f3-103">このトピックでは、例外に関するメッセージを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c60f3-103">The following topic describes how to add a message for an exception.</span></span>  
  
### <a name="to-add-a-message-for-an-exception"></a><span data-ttu-id="c60f3-104">例外に関するメッセージを追加するには</span><span class="sxs-lookup"><span data-stu-id="c60f3-104">To add a message for an exception</span></span>  
  
1.  <span data-ttu-id="c60f3-105">**オーケストレーション ビュー**ウィンドウを右クリックして**メッセージ**選択と**新しいメッセージ**です。</span><span class="sxs-lookup"><span data-stu-id="c60f3-105">In the **Orchestration View** window, right-click **Messages** and select **New Message**.</span></span>  
  
     <span data-ttu-id="c60f3-106">これにより Message_3 が作成され、このエラーに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="c60f3-106">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="c60f3-107">右クリック**Message_3**選択**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c60f3-107">Right-click **Message_3** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="c60f3-108">**プロパティ**ウィンドウで、設定、**メッセージの種類**です。</span><span class="sxs-lookup"><span data-stu-id="c60f3-108">In the **Properties** window, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="c60f3-109">選択 **.Net クラス**、し、 **SystemString**です。</span><span class="sxs-lookup"><span data-stu-id="c60f3-109">Select **.Net Classes**, and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c60f3-110">参照</span><span class="sxs-lookup"><span data-stu-id="c60f3-110">See Also</span></span>  
 [<span data-ttu-id="c60f3-111">BizTalk Server 例外処理の使用</span><span class="sxs-lookup"><span data-stu-id="c60f3-111">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)