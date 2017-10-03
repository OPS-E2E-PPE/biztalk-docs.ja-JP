---
title: "ASPX ページの接続のタイムアウトの設定 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ASPX pages, connection time-out
- connections, time-out
ms.assetid: 61d9c996-caf4-48bd-bda7-52f2797a941b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83e083b9f2f0262095e58b4ed9842627888773dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="setting-the-connection-time-out-for-an-aspx-page"></a><span data-ttu-id="69e9c-102">ASPX ページの接続のタイムアウトの設定</span><span class="sxs-lookup"><span data-stu-id="69e9c-102">Setting the Connection Time-Out for an ASPX Page</span></span>
<span data-ttu-id="69e9c-103">同期メッセージに ASPX ページを使用する場合は、着信メッセージを待機できるように、ASPX ページの接続タイムアウトを増やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="69e9c-103">When you use an ASPX page for synchronous messages, you must increase the connection time-out for the ASPX page so that it can wait for the expected message.</span></span>  
  
 <span data-ttu-id="69e9c-104">ASPX ページの接続タイムアウトを増やすと、予期しない結果が生じる場合があります。</span><span class="sxs-lookup"><span data-stu-id="69e9c-104">Increasing the connection time-out for the ASPX page can have unintended consequences.</span></span> <span data-ttu-id="69e9c-105">第一に、サービス拒否攻撃のリスクが増し、スレッド プールを使い果たすおそれがあります。</span><span class="sxs-lookup"><span data-stu-id="69e9c-105">First, it increases the risk of a denial-of-service attack and the threat of exhausting the thread pool.</span></span> <span data-ttu-id="69e9c-106">第二に、ASPX ページに同期接続が多すぎると、システムが動かなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69e9c-106">Second, if there are too many synchronous connections on the ASPX page, the system can lock up.</span></span> <span data-ttu-id="69e9c-107">したがって、接続タイムアウトを増やす必要がありますが、増やしすぎないように注意してください。</span><span class="sxs-lookup"><span data-stu-id="69e9c-107">Therefore, while you must increase the connection time-out, be careful not to increase it too much.</span></span>  
  
 <span data-ttu-id="69e9c-108">接続タイムアウトは RosettaNet 組織が許容する最小限に設定してください。</span><span class="sxs-lookup"><span data-stu-id="69e9c-108">Set the connection time-out to the minimum allowed by the RosettaNet organization.</span></span> <span data-ttu-id="69e9c-109">Partner Interface Process (PIP) のタイミング パラメータの詳細については、RosettaNet PIP 仕様の「表 4-3: メッセージ交換コントロール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69e9c-109">For more information about the timing parameters for a Partner Interface Process (PIP), see Table 4-3: Message Exchange Controls, in the RosettaNet PIP Specification.</span></span>  
  
### <a name="to-set-the-connection-time-out-for-the-aspx-page"></a><span data-ttu-id="69e9c-110">ASPX ページの接続タイムアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="69e9c-110">To set the connection time-out for the ASPX page</span></span>  
  
1.  <span data-ttu-id="69e9c-111">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="69e9c-111">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="69e9c-112">IIS マネージャーでは、ローカル コンピューターのノードを展開し、順に展開**Websites**です。</span><span class="sxs-lookup"><span data-stu-id="69e9c-112">In IIS Manager, expand the node for the local computer, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="69e9c-113">**[既定の Web サイト]**を右クリックし、 **[プロパティ]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69e9c-113">Right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="69e9c-114">既定の Web サイトのプロパティ ダイアログ ボックスで、 **Web サイト** タブの 、**接続タイムアウト**ボックスで、適切な値を入力し、をクリックして**ok**です。</span><span class="sxs-lookup"><span data-stu-id="69e9c-114">In the Default Web Site Properties dialog box, on the **Web Site** tab, in the **Connection Timeout** box, type an appropriate value, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e9c-115">参照</span><span class="sxs-lookup"><span data-stu-id="69e9c-115">See Also</span></span>  
 [<span data-ttu-id="69e9c-116">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="69e9c-116">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)