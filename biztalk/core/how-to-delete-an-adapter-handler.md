---
title: "アダプター ハンドラーを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, handlers
- deleting, handlers [adapters]
- handlers [adapters], deleting
ms.assetid: 95db5652-e175-45d1-b713-1ad73655a592
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3d591779a55fb7050e4ed229e19d19a312645462
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-delete-an-adapter-handler"></a><span data-ttu-id="d47e7-102">アダプター ハンドラーを削除する方法</span><span class="sxs-lookup"><span data-stu-id="d47e7-102">How to Delete an Adapter Handler</span></span>
<span data-ttu-id="d47e7-103">BizTalk Server 管理コンソールを使用して、送信または受信のアダプター ハンドラーを削除できます。</span><span class="sxs-lookup"><span data-stu-id="d47e7-103">You can delete a send or receive adapter handler by using the BizTalk Server Administration Console.</span></span>  
  
 <span data-ttu-id="d47e7-104">アダプター ハンドラーを削除する前に、ハンドラーと関連付けられている受信場所と送信ポートをすべて削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d47e7-104">Before you remove an adapter handler, you must remove all receive locations or send ports with which it is associated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d47e7-105">アダプター ハンドラーを削除するには、SSO 管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d47e7-105">You must be a member of the SSO Administration group to delete an adapter handler.</span></span>  
  
### <a name="to-delete-an-adapter-handler"></a><span data-ttu-id="d47e7-106">アダプター ハンドラーを削除するには</span><span class="sxs-lookup"><span data-stu-id="d47e7-106">To delete an adapter handler</span></span>  
  
1.  <span data-ttu-id="d47e7-107">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**プラットフォームの設定**を順に展開**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="d47e7-107">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="d47e7-108">展開したアダプターの一覧から、アダプター ハンドラーを削除するアダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="d47e7-108">In the expanded adapter list, select the adapter for which you want to delete the adapter handler.</span></span>  
  
3.  <span data-ttu-id="d47e7-109">削除、およびをクリックするアダプターのハンドラーを右クリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="d47e7-109">Right-click the adapter handler that you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="d47e7-110">をクリックして**はい**をこのアダプターのハンドラーを削除することを確認します。</span><span class="sxs-lookup"><span data-stu-id="d47e7-110">Click **Yes** to confirm that you want to delete this adapter handler.</span></span>  
  
5.  <span data-ttu-id="d47e7-111">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d47e7-111">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47e7-112">参照</span><span class="sxs-lookup"><span data-stu-id="d47e7-112">See Also</span></span>  
 [<span data-ttu-id="d47e7-113">作成して、アダプター ハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="d47e7-113">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)