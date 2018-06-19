---
redirect_url: /biztalk/core/using-tibco-rendezvous-send-ports-from-biztalk-server/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: d4a4f4fce200089db0e29d09b3ea49af00f3792f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014497"
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-send-messages"></a><span data-ttu-id="5385f-101">BizTalk Server を TIBCO Rendezvous から使用してメッセージを送信する</span><span class="sxs-lookup"><span data-stu-id="5385f-101">Using BizTalk Server from TIBCO Rendezvous to Send Messages</span></span>
<span data-ttu-id="5385f-102">Microsoft BizTalk Adapter for TIBCO Rendezvous は、非同期 API (Transport.Send) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5385f-102">Microsoft BizTalk Adapter for TIBCO Rendezvous uses the asynchronous API (Transport.Send).</span></span> <span data-ttu-id="5385f-103">メッセージ コンテキスト プロパティを使用して、このアダプターが送信するメッセージの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5385f-103">You can specify what kind of message the adapter sends using a message context property:</span></span>  
  
-   <span data-ttu-id="5385f-104">**構造化**: アダプターには、BizTalk Server から受信した XML データに基づいて、TIBRVMSG_MSG 構造化されたメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="5385f-104">**Structured**: The adapter generates a TIBRVMSG_MSG structured message, based on the XML data received from BizTalk Server.</span></span> <span data-ttu-id="5385f-105">(\*)</span><span class="sxs-lookup"><span data-stu-id="5385f-105">(\*)</span></span>  
  
 <span data-ttu-id="5385f-106">BizTalk Server が 127 文字を超える名前を持つフィールドのあるメッセージを送信した場合、BizTalk Adapter for TIBCO Rendezvous は、TIBCO Rendezvous の最大フィールド名サイズ (127 文字) に名前を切り捨てます。</span><span class="sxs-lookup"><span data-stu-id="5385f-106">If BizTalk Server sends a message with fields that have names longer than 127 characters, BizTalk Adapter for TIBCO Rendezvous truncates the names to the maximum field name size for TIBCO Rendezvous, which is 127.</span></span>  
  
 <span data-ttu-id="5385f-107">`reply subject name` プロパティが指定されている場合、このプロパティを使用して TIBCO Rendezvous メッセージの返信の件名が設定されます。</span><span class="sxs-lookup"><span data-stu-id="5385f-107">If a `reply subject name` property is provided, it is used to set the reply subject on the TIBCO Rendezvous message.</span></span> <span data-ttu-id="5385f-108">受信ポートが応答を待機して BizTalk Server に転送するように設定されているか、その他の TIBCO Rendezvous プログラムが応答を処理すると想定されています。</span><span class="sxs-lookup"><span data-stu-id="5385f-108">It is assumed that either a receive port is set to listen for the reply and forward it to BizTalk Server, or some other TIBCO Rendezvous program is taking care of the reply.</span></span>  
  
 <span data-ttu-id="5385f-109">トリプレット (サービス、デーモン、およびネットワーク) がトランスポートの構成を形成します。</span><span class="sxs-lookup"><span data-stu-id="5385f-109">The triplet (service, daemon, network) makes up the transport configuration.</span></span> <span data-ttu-id="5385f-110">トランスポートの構成が空白の場合 (既定)、メッセージは既定のトランスポート オブジェクトを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="5385f-110">An empty (default) transport configuration results in a message being sent through the default transport object.</span></span>  
  
 <span data-ttu-id="5385f-111">コード ページを指定しない場合、このアダプターは UTF-8 エンコーディング (コード ページ 65001) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5385f-111">If the code page is left unspecified, the adapter uses UTF-8 encoding (code page 65001).</span></span> <span data-ttu-id="5385f-112">伝送側では、認定済みメッセージはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5385f-112">Certified Messages are not supported on the transmitter side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5385f-113">参照</span><span class="sxs-lookup"><span data-stu-id="5385f-113">See Also</span></span>  
 <span data-ttu-id="5385f-114">[TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="5385f-114">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="5385f-115">TIBCO Rendezvous 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="5385f-115">Creating TIBCO Rendezvous Send Handlers</span></span>](../core/creating-tibco-rendezvous-send-handlers.md)