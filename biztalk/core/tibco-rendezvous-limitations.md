---
redirect_url: /biztalk/core/installing-biztalk-adapter-for-tibco-rendezvous/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: bcccc92430a73685ced9ad7259d8ec57dfc450b8
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013233"
---
# <a name="tibco-rendezvous-limitations"></a><span data-ttu-id="bc502-101">TIBCO Rendezvous の制限事項</span><span class="sxs-lookup"><span data-stu-id="bc502-101">TIBCO Rendezvous Limitations</span></span>
<span data-ttu-id="bc502-102">TIBCO Rendezvous では、フィールド名が一意であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="bc502-102">In TIBCO Rendezvous, field name uniqueness is not guaranteed.</span></span> <span data-ttu-id="bc502-103">TIBCO Rendezvous メッセージに 2 つの同じフィールド名がある場合、生成される XML は無効になります。</span><span class="sxs-lookup"><span data-stu-id="bc502-103">If a TIBCO Rendezvous message contains two field names that are the same, the resulting XML is not valid.</span></span>  
  
 <span data-ttu-id="bc502-104">他にも次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="bc502-104">Other limitations include the following:</span></span>  
  
-   <span data-ttu-id="bc502-105">フィールドを並べ替えることはできません。</span><span class="sxs-lookup"><span data-stu-id="bc502-105">Field ordering/sorting is not provided.</span></span>  
  
-   <span data-ttu-id="bc502-106">TIBCO Rendezvous のドキュメントによると、サブジェクト名には印刷できない文字を使用できないことになっていますが、そのような文字を使用することはできます。</span><span class="sxs-lookup"><span data-stu-id="bc502-106">According to TIBCO Rendezvous documentation, non-printable characters are not used in subject names; however, it is still possible that such characters are used.</span></span> <span data-ttu-id="bc502-107">BizTalk Adapter for TIBCO Rendezvous では印刷できない文字が入ったサブジェクト名をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="bc502-107">BizTalk Adapter for TIBCO Rendezvous does not support subject names containing those characters.</span></span>  
  
-   <span data-ttu-id="bc502-108">デーモンへのセキュリティで保護された接続はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bc502-108">Secure connection to daemons is not supported.</span></span>  
  
-   <span data-ttu-id="bc502-109">カスタム データ型はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bc502-109">Custom data types are not supported.</span></span>  
  
-   <span data-ttu-id="bc502-110">認定メッセージングは送信側ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bc502-110">Certified Messaging is not supported on the transmit side.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc502-111">参照</span><span class="sxs-lookup"><span data-stu-id="bc502-111">See Also</span></span>  
 <span data-ttu-id="bc502-112">[TIBCO Rendezvous の概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="bc502-112">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="bc502-113">作業の開始</span><span class="sxs-lookup"><span data-stu-id="bc502-113">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)