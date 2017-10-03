---
title: "PeopleSoft Enterprise のパイプラインを設定する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting pipelines
- pipelines, setting
ms.assetid: 36914615-eac0-47b6-9e66-deeb40d21f10
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69bebce2dadf0bb038b0e8c56ffa544ad02c78ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-pipelines-for-peoplesoft-enterprise"></a><span data-ttu-id="b9949-102">PeopleSoft Enterprise のパイプラインを設定する方法</span><span class="sxs-lookup"><span data-stu-id="b9949-102">How to Set Pipelines for PeopleSoft Enterprise</span></span>
<span data-ttu-id="b9949-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise では、適切なパイプラインを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9949-103">Microsoft BizTalk Adapter for PeopleSoft Enterprise requires that you select an appropriate pipeline.</span></span>  
  
## <a name="setting-pipelines"></a><span data-ttu-id="b9949-104">パイプラインの設定</span><span class="sxs-lookup"><span data-stu-id="b9949-104">Setting Pipelines</span></span>  
  
#### <a name="to-set-pipelines"></a><span data-ttu-id="b9949-105">パイプラインを設定するには</span><span class="sxs-lookup"><span data-stu-id="b9949-105">To set pipelines</span></span>  
  
1.  <span data-ttu-id="b9949-106">BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、し、必要な展開アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="b9949-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="b9949-107">右クリック**送信ポート**、 をポイント**新規**、クリックして**静的な送信請求-応答送信ポート**です。</span><span class="sxs-lookup"><span data-stu-id="b9949-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="b9949-108">**送信ポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="b9949-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="b9949-109">たとえば、送信ポートの名前を入力`SSOSendToPeopleSoft`です。</span><span class="sxs-lookup"><span data-stu-id="b9949-109">Type a name for the send port, for example, `SSOSendToPeopleSoft`.</span></span>  
  
    2.  <span data-ttu-id="b9949-110">**型**ドロップダウン リストで、 **PeopleSoft**です。</span><span class="sxs-lookup"><span data-stu-id="b9949-110">From the **Type** drop-down list, select **PeopleSoft**.</span></span>  
  
    3.  <span data-ttu-id="b9949-111">**送信ハンドラー**ドロップダウン リストで、URI を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9949-111">From the **Send handler** drop-down list, select the URI.</span></span>  
  
    4.  <span data-ttu-id="b9949-112">送信パイプラインのドロップダウン リストから選択**[microsoft.biztalk.defaultpipelines.xmltransmit]**です。</span><span class="sxs-lookup"><span data-stu-id="b9949-112">From the Send Pipeline drop-down list, select **Microsoft.BizTalk.DefaultPipelines.XMLTransmit**.</span></span>  
  
    5.  <span data-ttu-id="b9949-113">**受信パイプライン**ドロップダウン リストで、 **[microsoft.biztalk.defaultpiplelines.xmlreceive]**です。</span><span class="sxs-lookup"><span data-stu-id="b9949-113">From the **Receive Pipeline** drop-down list, select **Microsoft.BizTalk.DefaultPiplelines.XMLReceive**.</span></span>  
  
4.  <span data-ttu-id="b9949-114">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9949-114">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9949-115">参照</span><span class="sxs-lookup"><span data-stu-id="b9949-115">See Also</span></span>  
 [<span data-ttu-id="b9949-116">PeopleSoft 送信ハンドラーの作成</span><span class="sxs-lookup"><span data-stu-id="b9949-116">Creating PeopleSoft Send Handlers</span></span>](../core/creating-peoplesoft-send-handlers.md)