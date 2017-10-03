---
title: "TIBCO Enterprise Message Service のパイプラインを送信を設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines
- setting send pipelines
- pipelines, send
ms.assetid: 6a84d874-4b4d-4b23-913f-f5c72af1e96e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d037782e2580d52c6609c3669e2805aae92ce9eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-tibco-enterprise-message-service"></a><span data-ttu-id="d85bd-102">TIBCO Enterprise Message Service 用の送信パイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="d85bd-102">How to Set Send Pipelines for TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="d85bd-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service では、送信パイプラインに XMLTransmit、受信パイプラインに XMLReceive をそれぞれ選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d85bd-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service requires that you select XMLTransmit and XMLReceive for the Send and Receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="d85bd-104">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="d85bd-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="d85bd-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="d85bd-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="d85bd-106">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="d85bd-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="d85bd-107">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="d85bd-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="d85bd-108">たとえば、送信ポートの名前を入力`SendToTIBCOEMS`です。</span><span class="sxs-lookup"><span data-stu-id="d85bd-108">Type a name for the send port, for example, `SendToTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="d85bd-109">**型**ドロップダウン リストで、 **TIBCO EMS**です。</span><span class="sxs-lookup"><span data-stu-id="d85bd-109">From the **Type** drop-down list, select **TIBCO EMS**.</span></span>  
  
    3.  <span data-ttu-id="d85bd-110">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="d85bd-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="d85bd-111">送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。</span><span class="sxs-lookup"><span data-stu-id="d85bd-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="d85bd-112">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。</span><span class="sxs-lookup"><span data-stu-id="d85bd-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="d85bd-113">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d85bd-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d85bd-114">参照</span><span class="sxs-lookup"><span data-stu-id="d85bd-114">See Also</span></span>  
 [<span data-ttu-id="d85bd-115">設定する方法 TIBCO Enterprise Message Service 用の受信パイプライン</span><span class="sxs-lookup"><span data-stu-id="d85bd-115">How to Set Receive Pipelines for TIBCO Enterprise Message Service</span></span>](../core/how-to-set-receive-pipelines-for-tibco-enterprise-message-service.md)