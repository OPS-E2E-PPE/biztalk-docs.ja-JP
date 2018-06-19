---
redirect_url: /biztalk/core/creating-peoplesoft-send-handlers/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: e5f68232aa0cb59835523df0afac01f3d1949489
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013881"
---
# <a name="how-to-set-pipelines-for-peoplesoft-enterprise"></a><span data-ttu-id="c88df-101">PeopleSoft Enterprise のパイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="c88df-101">How to Set Pipelines for PeopleSoft Enterprise</span></span>
<span data-ttu-id="c88df-102">Microsoft BizTalk Adapter for PeopleSoft Enterprise では、適切なパイプラインを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c88df-102">Microsoft BizTalk Adapter for PeopleSoft Enterprise requires that you select an appropriate pipeline.</span></span>  
  
## <a name="setting-pipelines"></a><span data-ttu-id="c88df-103">パイプラインの設定</span><span class="sxs-lookup"><span data-stu-id="c88df-103">Setting Pipelines</span></span>  
  
#### <a name="to-set-pipelines"></a><span data-ttu-id="c88df-104">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="c88df-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="c88df-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c88df-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="c88df-106">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c88df-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="c88df-107">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="c88df-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="c88df-108">たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`です。</span><span class="sxs-lookup"><span data-stu-id="c88df-108">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="c88df-109">**型**ドロップダウン リストで、 **PeopleSoft**です。</span><span class="sxs-lookup"><span data-stu-id="c88df-109">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="c88df-110">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="c88df-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="c88df-111">送信パイプラインのドロップダウン リストから選択 **[microsoft.biztalk.defaultpipelines.xmltransmit]** です。</span><span class="sxs-lookup"><span data-stu-id="c88df-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="c88df-112">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** です。</span><span class="sxs-lookup"><span data-stu-id="c88df-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="c88df-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c88df-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c88df-114">参照</span><span class="sxs-lookup"><span data-stu-id="c88df-114">See Also</span></span>  
 [<span data-ttu-id="c88df-115">PeopleSoft 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="c88df-115">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)