---
title: "TIBCO Rendezvous イベントと受信場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive locations, life cycle
ms.assetid: 3576af82-4723-4efc-961e-40b1150cf13d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9278687ff212fc2368eca138780417d7c052824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a><span data-ttu-id="a9f61-102">TIBCO Rendezvous イベントと受信場所</span><span class="sxs-lookup"><span data-stu-id="a9f61-102">TIBCO Rendezvous Events and Receive Locations</span></span>
<span data-ttu-id="a9f61-103">TIBCO Rendezvous システムは、選択したサブジェクト名にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="a9f61-103">Any TIBCO Rendezvous system can send messages to their subject name of choice.</span></span> <span data-ttu-id="a9f61-104">概念*イベント*の他の TIBCO Rendezvous プログラムでメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a9f61-104">The concept of *event* is the generation of messages by other TIBCO Rendezvous programs.</span></span>  
  
 <span data-ttu-id="a9f61-105">次の手順は、受信場所のライフ サイクルについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="a9f61-105">The following steps describe the life cycle of a receive location:</span></span>  
  
1.  <span data-ttu-id="a9f61-106">受信場所が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a9f61-106">Receive location is created.</span></span>  
  
2.  <span data-ttu-id="a9f61-107">受信場所がホストに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="a9f61-107">Receive location is associated with a host.</span></span>  
  
3.  <span data-ttu-id="a9f61-108">受信場所がオーケストレーションにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="a9f61-108">Receive location is bound to an orchestration.</span></span>  
  
4.  <span data-ttu-id="a9f61-109">受信場所が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="a9f61-109">Receive location is enabled.</span></span>  
  
5.  <span data-ttu-id="a9f61-110">受信場所がメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="a9f61-110">Receive location receives messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a9f61-111">各受信場所には一意の名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="a9f61-111">Each receive location must have a unique name.</span></span> <span data-ttu-id="a9f61-112">2 つの受信場所が同じ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の展開で同じ名前を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="a9f61-112">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a9f61-113">お勧め強力なアクセス制御リスト (ACL) に設定することで、受信場所のドロップ場所。</span><span class="sxs-lookup"><span data-stu-id="a9f61-113">It is recommended that you set strong access control lists (ACL) in the receive locations drop locations.</span></span> <span data-ttu-id="a9f61-114">たとえば、ファイルの受信場所がメッセージを取得するディレクトリに強力な ACL を設定し、認証されたユーザーだけがこの場所にメッセージを格納できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9f61-114">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f61-115">参照</span><span class="sxs-lookup"><span data-stu-id="a9f61-115">See Also</span></span>  
 [<span data-ttu-id="a9f61-116">作成元の TIBCO Rendezvous 受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="a9f61-116">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)