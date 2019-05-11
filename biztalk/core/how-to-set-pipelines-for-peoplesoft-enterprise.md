---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 2681c3141f6c89479c3632b1a00f35ee495aa4b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383922"
---
# <a name="how-to-set-pipelines-for-peoplesoft-enterprise"></a><span data-ttu-id="8a69e-101">PeopleSoft Enterprise のパイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="8a69e-101">How to Set Pipelines for PeopleSoft Enterprise</span></span>
<span data-ttu-id="8a69e-102">Microsoft BizTalk Adapter for PeopleSoft Enterprise では、適切なパイプラインを選択することが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a69e-102">Microsoft BizTalk Adapter for PeopleSoft Enterprise requires that you select an appropriate pipeline.</span></span>  
  
## <a name="setting-pipelines"></a><span data-ttu-id="8a69e-103">パイプラインの設定</span><span class="sxs-lookup"><span data-stu-id="8a69e-103">Setting Pipelines</span></span>  
  
#### <a name="to-set-pipelines"></a><span data-ttu-id="8a69e-104">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="8a69e-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="8a69e-105">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="8a69e-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="8a69e-106">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="8a69e-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="8a69e-107">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8a69e-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="8a69e-108">たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`します。</span><span class="sxs-lookup"><span data-stu-id="8a69e-108">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="8a69e-109">**型**ドロップダウン リストで、 **PeopleSoft**します。</span><span class="sxs-lookup"><span data-stu-id="8a69e-109">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="8a69e-110">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a69e-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="8a69e-111">送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="8a69e-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="8a69e-112">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。</span><span class="sxs-lookup"><span data-stu-id="8a69e-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="8a69e-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a69e-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a69e-114">参照</span><span class="sxs-lookup"><span data-stu-id="8a69e-114">See Also</span></span>  
 [<span data-ttu-id="8a69e-115">PeopleSoft 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="8a69e-115">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)