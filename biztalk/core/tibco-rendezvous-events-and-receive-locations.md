---
redirect_url: /biztalk/core/creating-tibco-rendezvous-receive-handlers/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: b93e747cdc665fb5a8407ca2a3d052b880236378
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-rendezvous-events-and-receive-locations"></a><span data-ttu-id="5ab86-101">TIBCO Rendezvous イベントと受信場所</span><span class="sxs-lookup"><span data-stu-id="5ab86-101">TIBCO Rendezvous Events and Receive Locations</span></span>
<span data-ttu-id="5ab86-102">TIBCO Rendezvous システムは、選択したサブジェクト名にメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="5ab86-102">Any TIBCO Rendezvous system can send messages to their subject name of choice.</span></span> <span data-ttu-id="5ab86-103">概念*イベント*の他の TIBCO Rendezvous プログラムでメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5ab86-103">The concept of *event* is the generation of messages by other TIBCO Rendezvous programs.</span></span>  
  
 <span data-ttu-id="5ab86-104">次の手順は、受信場所のライフ サイクルについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="5ab86-104">The following steps describe the life cycle of a receive location:</span></span>  
  
1.  <span data-ttu-id="5ab86-105">受信場所が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5ab86-105">Receive location is created.</span></span>  
  
2.  <span data-ttu-id="5ab86-106">受信場所がホストに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="5ab86-106">Receive location is associated with a host.</span></span>  
  
3.  <span data-ttu-id="5ab86-107">受信場所がオーケストレーションにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="5ab86-107">Receive location is bound to an orchestration.</span></span>  
  
4.  <span data-ttu-id="5ab86-108">受信場所が有効化されます。</span><span class="sxs-lookup"><span data-stu-id="5ab86-108">Receive location is enabled.</span></span>  
  
5.  <span data-ttu-id="5ab86-109">受信場所がメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="5ab86-109">Receive location receives messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5ab86-110">各受信場所には一意の名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="5ab86-110">Each receive location must have a unique name.</span></span> <span data-ttu-id="5ab86-111">2 つの受信場所が同じ [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の展開で同じ名前を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="5ab86-111">Two receive locations cannot have the same name in the same [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5ab86-112">お勧め強力なアクセス制御リスト (ACL) に設定することで、受信場所のドロップ場所。</span><span class="sxs-lookup"><span data-stu-id="5ab86-112">It is recommended that you set strong access control lists (ACL) in the receive locations drop locations.</span></span> <span data-ttu-id="5ab86-113">たとえば、ファイルの受信場所がメッセージを取得するディレクトリに強力な ACL を設定し、認証されたユーザーだけがこの場所にメッセージを格納できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ab86-113">For example, you must set strong ACLs for the directory where the file receive location picks up messages, so that only authorized users can drop messages in this location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab86-114">参照</span><span class="sxs-lookup"><span data-stu-id="5ab86-114">See Also</span></span>  
 [<span data-ttu-id="5ab86-115">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="5ab86-115">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)