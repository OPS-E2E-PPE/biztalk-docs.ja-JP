---
title: "JD Edwards EnterpriseOne の送信を設定する方法がパイプライン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send pipelines
- send pipelines, configuring [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], configuring
- adapters [JD Edwards EnterpriseOne adapters], send pipelines
- JD Edwards EnterpriseOne adapters, configuring
ms.assetid: 4cfcecc1-febe-47c8-b75f-2b84defcdbbc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c9a6337195c8050afca1f12a015ec492db7f7ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-jd-edwards-enterpriseone"></a><span data-ttu-id="27f7c-102">JD Edwards EnterpriseOne の送信パイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="27f7c-102">How to Set Send Pipelines for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="27f7c-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne を選択することが必要です**XMLTransmit**と**XMLReceive**の送信および受信パイプラインをそれぞれします。</span><span class="sxs-lookup"><span data-stu-id="27f7c-103">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne requires that you select **XMLTransmit** and **XMLReceive** for the send and receive pipelines respectively.</span></span>  
  
### <a name="to-set-pipelines"></a><span data-ttu-id="27f7c-104">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="27f7c-104">To set pipelines</span></span>  
  
1.  <span data-ttu-id="27f7c-105">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="27f7c-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="27f7c-106">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="27f7c-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="27f7c-107">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="27f7c-107">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="27f7c-108">たとえば、送信ポートの名前を入力`SendToJDEEnterpriseOne`です。</span><span class="sxs-lookup"><span data-stu-id="27f7c-108">Type a name for the send port, for example, `SendToJDEEnterpriseOne`.</span></span>  
  
    2.  <span data-ttu-id="27f7c-109">**型**ドロップダウン リストで、 **JDE EnterpriseOne**です。</span><span class="sxs-lookup"><span data-stu-id="27f7c-109">From the **Type** drop-down list, select **JDE EnterpriseOne**.</span></span>  
  
    3.  <span data-ttu-id="27f7c-110">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="27f7c-110">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="27f7c-111">送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。</span><span class="sxs-lookup"><span data-stu-id="27f7c-111">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="27f7c-112">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。</span><span class="sxs-lookup"><span data-stu-id="27f7c-112">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="27f7c-113">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27f7c-113">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27f7c-114">参照</span><span class="sxs-lookup"><span data-stu-id="27f7c-114">See Also</span></span>  
 [<span data-ttu-id="27f7c-115">JD Edwards EnterpriseOne 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="27f7c-115">Creating JD Edwards EnterpriseOne Send Handlers</span></span>](../core/creating-jd-edwards-enterpriseone-send-handlers.md)