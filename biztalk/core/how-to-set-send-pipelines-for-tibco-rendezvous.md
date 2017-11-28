---
title: "TIBCO Rendezvous の送信を設定する方法がパイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines
- pipelines, send
ms.assetid: a28a02c1-6f30-4749-b819-c1e707757680
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48d3a72c2282e335f2d3e020ec0e77a8b7afbd35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-tibco-rendezvous"></a><span data-ttu-id="c18d6-102">TIBCO Rendezvous の送信パイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="c18d6-102">How to Set Send Pipelines for TIBCO Rendezvous</span></span>
<span data-ttu-id="c18d6-103">Microsoft BizTalk Adapter for TIBCO Rendezvous では、送信パイプラインに XMLTransmit、受信パイプラインに XMLReceive をそれぞれ選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18d6-103">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you select XMLTransmit and XMLReceive for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="c18d6-104">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="c18d6-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="c18d6-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="c18d6-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="c18d6-106">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="c18d6-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="c18d6-107">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="c18d6-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="c18d6-108">たとえば、送信ポートの名前を入力`SendToTIBCORV`です。</span><span class="sxs-lookup"><span data-stu-id="c18d6-108">Type a name for the send port, for example, `SendToTIBCORV`.</span></span>  
  
    2.  <span data-ttu-id="c18d6-109">**型**ドロップダウン リストで、 **TIBCO Rendezvous**です。</span><span class="sxs-lookup"><span data-stu-id="c18d6-109">From the **Type** drop-down list, select **TIBCO Rendezvous**.</span></span>  
  
    3.  <span data-ttu-id="c18d6-110">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="c18d6-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="c18d6-111">送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。</span><span class="sxs-lookup"><span data-stu-id="c18d6-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="c18d6-112">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。</span><span class="sxs-lookup"><span data-stu-id="c18d6-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="c18d6-113">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c18d6-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c18d6-114">参照</span><span class="sxs-lookup"><span data-stu-id="c18d6-114">See Also</span></span>  
 <span data-ttu-id="c18d6-115">[TIBCO Rendezvous 送信ハンドラーを作成します。](../core/creating-tibco-rendezvous-send-handlers.md) </span><span class="sxs-lookup"><span data-stu-id="c18d6-115">[Creating TIBCO Rendezvous Send Handlers](../core/creating-tibco-rendezvous-send-handlers.md) </span></span>  
 [<span data-ttu-id="c18d6-116">作成元の TIBCO Rendezvous 受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="c18d6-116">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)