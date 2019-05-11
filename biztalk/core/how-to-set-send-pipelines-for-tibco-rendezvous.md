---
redirect_url: /biztalk/core/creating-tibco-rendezvous-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 062194b411096af3e03afee826b73efad09c2036
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383896"
---
# <a name="how-to-set-send-pipelines-for-tibco-rendezvous"></a><span data-ttu-id="fa634-101">TIBCO Rendezvous の送信パイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="fa634-101">How to Set Send Pipelines for TIBCO Rendezvous</span></span>
<span data-ttu-id="fa634-102">Microsoft BizTalk Adapter for TIBCO Rendezvous では、送信、XMLTransmit および XMLReceive を選択して受信パイプラインはそれぞれことが必要です。</span><span class="sxs-lookup"><span data-stu-id="fa634-102">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you select XMLTransmit and XMLReceive for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="fa634-103">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="fa634-103">To set pipelines</span></span>  
  
1.  <span data-ttu-id="fa634-104">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="fa634-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="fa634-105">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="fa634-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="fa634-106">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fa634-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="fa634-107">たとえば、送信ポートの名前を入力`SendToTIBCORV`します。</span><span class="sxs-lookup"><span data-stu-id="fa634-107">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="fa634-108">**型**ドロップダウン リストで、 **TIBCO Rendezvous**します。</span><span class="sxs-lookup"><span data-stu-id="fa634-108">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="fa634-109">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa634-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="fa634-110">送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="fa634-110">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="fa634-111">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。</span><span class="sxs-lookup"><span data-stu-id="fa634-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="fa634-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa634-112">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa634-113">参照</span><span class="sxs-lookup"><span data-stu-id="fa634-113">See Also</span></span>  
 <span data-ttu-id="fa634-114">[TIBCO Rendezvous 送信ハンドラーを作成します。](../core/creating-tibco-rendezvous-send-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="fa634-114">[Creating TIBCO Rendezvous Send Handlers](../core/creating-tibco-rendezvous-send-handlers.md) </span></span>  
 [<span data-ttu-id="fa634-115">TIBCO Rendezvous 受信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="fa634-115">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)