---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-enterpriseone/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: 73b4e2f88adb05c90812dd809ea60704a591602f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383914"
---
# <a name="how-to-set-send-pipelines-for-jd-edwards-enterpriseone"></a><span data-ttu-id="59c07-101">JD Edwards EnterpriseOne の送信パイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="59c07-101">How to Set Send Pipelines for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="59c07-102">Microsoft の BizTalk Adapter for JD Edwards EnterpriseOne では、選択する必要があります**XMLTransmit**と**XMLReceive**送信および受信パイプラインはそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="59c07-102">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne requires that you select **XMLTransmit** and **XMLReceive** for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="59c07-103">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="59c07-103">To set pipelines</span></span>  
  
1.  <span data-ttu-id="59c07-104">BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="59c07-104">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="59c07-105">右クリック**送信ポート**、 をポイント**新規**、 をクリックし、**静的な送信請求-応答送信ポート**します。</span><span class="sxs-lookup"><span data-stu-id="59c07-105">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="59c07-106">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="59c07-106">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="59c07-107">たとえば、送信ポートの名前を入力`SendToJDEEnterpriseOne`します。</span><span class="sxs-lookup"><span data-stu-id="59c07-107">Type a name for the send port, for example, `SendToJDEEnterpriseOne`.</span></span>  
  
    2.  <span data-ttu-id="59c07-108">**型**ドロップダウン リストで、 **JDE EnterpriseOne**します。</span><span class="sxs-lookup"><span data-stu-id="59c07-108">From the **Type** drop-down list, select **JDE EnterpriseOne**.</span></span>  
  
    3.  <span data-ttu-id="59c07-109">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="59c07-109">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="59c07-110">送信パイプラインのドロップダウン リストから選択**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**します。</span><span class="sxs-lookup"><span data-stu-id="59c07-110">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="59c07-111">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]** します。</span><span class="sxs-lookup"><span data-stu-id="59c07-111">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="59c07-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="59c07-112">Click **OK**.</span></span>  
  
