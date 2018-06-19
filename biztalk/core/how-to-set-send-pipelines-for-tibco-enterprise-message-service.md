---
redirect_url: /biztalk/core/creating-tibco-enterprise-message-service-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: dc9746babaa80520b2a99948c5796c9b064899e0
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015585"
---
# <a name="how-to-set-send-pipelines-for-tibco-enterprise-message-service"></a><span data-ttu-id="dfd2d-101">TIBCO Enterprise Message Service 用の送信パイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="dfd2d-101">How to Set Send Pipelines for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="dfd2d-102">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service では、送信パイプラインに XMLTransmit、受信パイプラインに XMLReceive をそれぞれ選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfd2d-102">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service requires that you select XMLTransmit and XMLReceive for the Send and Receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="dfd2d-103">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="dfd2d-103">To set pipelines</span></span>  
  
1.  <span data-ttu-id="dfd2d-104">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="dfd2d-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="dfd2d-105">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="dfd2d-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="dfd2d-106">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="dfd2d-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="dfd2d-107">たとえば、送信ポートの名前を入力`SendToTIBCOEMS`です。</span><span class="sxs-lookup"><span data-stu-id="dfd2d-107">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="dfd2d-108">**型**ドロップダウン リストで、 **TIBCO EMS**です。</span><span class="sxs-lookup"><span data-stu-id="dfd2d-108">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="dfd2d-109">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfd2d-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="dfd2d-110">送信パイプラインのドロップダウン リストから選択 **[microsoft.biztalk.defaultpipelines.xmltransmit]** です。</span><span class="sxs-lookup"><span data-stu-id="dfd2d-110">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="dfd2d-111">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** です。</span><span class="sxs-lookup"><span data-stu-id="dfd2d-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="dfd2d-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dfd2d-112">Click **OK**.</span></span>  
  
