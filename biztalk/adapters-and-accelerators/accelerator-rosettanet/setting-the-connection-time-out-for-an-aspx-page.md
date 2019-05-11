---
title: ASPX ページの接続のタイムアウトの設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ASPX pages, connection time-out
- connections, time-out
ms.assetid: 61d9c996-caf4-48bd-bda7-52f2797a941b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d28867e323a3fb7c3b50ab787b31b19c32c36e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281838"
---
# <a name="setting-the-connection-time-out-for-an-aspx-page"></a><span data-ttu-id="f5c26-102">ASPX ページの接続のタイムアウトの設定</span><span class="sxs-lookup"><span data-stu-id="f5c26-102">Setting the Connection Time-Out for an ASPX Page</span></span>
<span data-ttu-id="f5c26-103">同期メッセージに ASPX ページを使用するときに、予期されるメッセージを待機できるように、ASPX ページの接続のタイムアウトを増やす必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5c26-103">When you use an ASPX page for synchronous messages, you must increase the connection time-out for the ASPX page so that it can wait for the expected message.</span></span>  
  
 <span data-ttu-id="f5c26-104">ASPX ページを指定することは、接続のタイムアウトを増やすと意図しない結果。</span><span class="sxs-lookup"><span data-stu-id="f5c26-104">Increasing the connection time-out for the ASPX page can have unintended consequences.</span></span> <span data-ttu-id="f5c26-105">最初に、サービス拒否攻撃のリスクと、スレッド プールを使い果たすおそれが増加します。</span><span class="sxs-lookup"><span data-stu-id="f5c26-105">First, it increases the risk of a denial-of-service attack and the threat of exhausting the thread pool.</span></span> <span data-ttu-id="f5c26-106">次に、ASPX ページで同期接続が多すぎますがある場合、システムが動かなくなります。</span><span class="sxs-lookup"><span data-stu-id="f5c26-106">Second, if there are too many synchronous connections on the ASPX page, the system can lock up.</span></span> <span data-ttu-id="f5c26-107">そのため、接続のタイムアウトを増やす必要があります、中には、増やしすぎないしないように注意します。</span><span class="sxs-lookup"><span data-stu-id="f5c26-107">Therefore, while you must increase the connection time-out, be careful not to increase it too much.</span></span>  
  
 <span data-ttu-id="f5c26-108">RosettaNet 組織で許容される最小の接続のタイムアウトを設定します。</span><span class="sxs-lookup"><span data-stu-id="f5c26-108">Set the connection time-out to the minimum allowed by the RosettaNet organization.</span></span> <span data-ttu-id="f5c26-109">詳細については、タイミング パラメーター パートナー インターフェイス プロセス (PIP) の表 4-3 を参照してください。RosettaNet PIP 仕様のメッセージ交換コントロール。</span><span class="sxs-lookup"><span data-stu-id="f5c26-109">For more information about the timing parameters for a Partner Interface Process (PIP), see Table 4-3: Message Exchange Controls, in the RosettaNet PIP Specification.</span></span>  
  
### <a name="to-set-the-connection-time-out-for-the-aspx-page"></a><span data-ttu-id="f5c26-110">ASPX ページの接続タイムアウトを設定するには</span><span class="sxs-lookup"><span data-stu-id="f5c26-110">To set the connection time-out for the ASPX page</span></span>  
  
1.  <span data-ttu-id="f5c26-111">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**インターネット インフォメーション サービス (IIS) マネージャー**.</span><span class="sxs-lookup"><span data-stu-id="f5c26-111">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="f5c26-112">IIS マネージャーでは、ローカルのコンピューターのノードを展開し、順に展開**Websites**します。</span><span class="sxs-lookup"><span data-stu-id="f5c26-112">In IIS Manager, expand the node for the local computer, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="f5c26-113">**[既定の Web サイト]** を右クリックし、 **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f5c26-113">Right-click **Default Web Site**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="f5c26-114">既定の Web サイトのプロパティ ダイアログ ボックスで、 **Web サイト** タブで、**接続タイムアウト**ボックスで、適切な値を入力し、をクリックし、 **ok**。</span><span class="sxs-lookup"><span data-stu-id="f5c26-114">In the Default Web Site Properties dialog box, on the **Web Site** tab, in the **Connection Timeout** box, type an appropriate value, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c26-115">参照</span><span class="sxs-lookup"><span data-stu-id="f5c26-115">See Also</span></span>  
 [<span data-ttu-id="f5c26-116">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f5c26-116">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)