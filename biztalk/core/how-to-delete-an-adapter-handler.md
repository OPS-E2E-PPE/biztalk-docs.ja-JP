---
title: アダプター ハンドラーを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, handlers
- deleting, handlers [adapters]
- handlers [adapters], deleting
ms.assetid: 95db5652-e175-45d1-b713-1ad73655a592
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27bc813ad300eb4b0931ba4174c63becafd09807
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385355"
---
# <a name="how-to-delete-an-adapter-handler"></a><span data-ttu-id="9b88f-102">アダプター ハンドラーを削除する方法</span><span class="sxs-lookup"><span data-stu-id="9b88f-102">How to Delete an Adapter Handler</span></span>
<span data-ttu-id="9b88f-103">送信を削除したり、BizTalk Server 管理コンソールを使用して、アダプターのハンドラーを受信できます。</span><span class="sxs-lookup"><span data-stu-id="9b88f-103">You can delete a send or receive adapter handler by using the BizTalk Server Administration Console.</span></span>  
  
 <span data-ttu-id="9b88f-104">削除する必要があります、アダプター ハンドラーを削除する前にすべての受信場所または送信ポートが関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="9b88f-104">Before you remove an adapter handler, you must remove all receive locations or send ports with which it is associated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b88f-105">アダプター ハンドラーを削除するには、SSO 管理者グループのメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="9b88f-105">You must be a member of the SSO Administration group to delete an adapter handler.</span></span>  
  
### <a name="to-delete-an-adapter-handler"></a><span data-ttu-id="9b88f-106">アダプター ハンドラーを削除するには</span><span class="sxs-lookup"><span data-stu-id="9b88f-106">To delete an adapter handler</span></span>  
  
1.  <span data-ttu-id="9b88f-107">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**順に展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="9b88f-107">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="9b88f-108">展開したアダプターの一覧で、アダプター ハンドラーを削除するアダプターを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b88f-108">In the expanded adapter list, select the adapter for which you want to delete the adapter handler.</span></span>  
  
3.  <span data-ttu-id="9b88f-109">クリックして、削除するアダプターのハンドラーを右クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="9b88f-109">Right-click the adapter handler that you want to delete, and then click **Delete**.</span></span>  
  
4.  <span data-ttu-id="9b88f-110">クリックして**はい**アダプター ハンドラーの削除することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b88f-110">Click **Yes** to confirm that you want to delete this adapter handler.</span></span>  
  
5.  <span data-ttu-id="9b88f-111">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9b88f-111">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b88f-112">参照</span><span class="sxs-lookup"><span data-stu-id="9b88f-112">See Also</span></span>  
 [<span data-ttu-id="9b88f-113">アダプター ハンドラーの作成と削除</span><span class="sxs-lookup"><span data-stu-id="9b88f-113">Creating and Deleting Adapter Handlers</span></span>](../core/creating-and-deleting-adapter-handlers.md)