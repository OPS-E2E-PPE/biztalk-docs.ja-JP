---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 263f1f5d9441a30687df3e1a7a1170b7bf35e2fc
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
ms.locfileid: "24015073"
---
# <a name="how-to-set-send-pipelines-for-jd-edwards-enterpriseone"></a><span data-ttu-id="f25e6-101">JD Edwards EnterpriseOne の送信パイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="f25e6-101">How to Set Send Pipelines for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="f25e6-102">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne を選択することが必要です**XMLTransmit**と**XMLReceive**の送信および受信パイプラインをそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="f25e6-102">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne requires that you select **XMLTransmit** and **XMLReceive** for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="f25e6-103">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="f25e6-103">To set pipelines</span></span>  
  
1.  <span data-ttu-id="f25e6-104">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="f25e6-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="f25e6-105">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="f25e6-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="f25e6-106">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="f25e6-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="f25e6-107">たとえば、送信ポートの名前を入力`SendToJDEEnterpriseOne`です。</span><span class="sxs-lookup"><span data-stu-id="f25e6-107">Type a name for the send port, for example, `SendToJDEEnterpriseOne`.</span></span>  
  
    2.  <span data-ttu-id="f25e6-108">**型**ドロップダウン リストで、 **JDE EnterpriseOne**です。</span><span class="sxs-lookup"><span data-stu-id="f25e6-108">From the **Type** drop-down list, select **JDE EnterpriseOne**.</span></span>  
  
    3.  <span data-ttu-id="f25e6-109">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="f25e6-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="f25e6-110">送信パイプラインのドロップダウン リストから選択 **[microsoft.biztalk.defaultpipelines.xmltransmit]** です。</span><span class="sxs-lookup"><span data-stu-id="f25e6-110">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="f25e6-111">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** です。</span><span class="sxs-lookup"><span data-stu-id="f25e6-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="f25e6-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f25e6-112">Click **OK**.</span></span>  
  
