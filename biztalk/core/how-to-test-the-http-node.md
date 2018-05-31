---
title: HTTP ノードをテストする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP node, testing
- testing HTTP node
ms.assetid: f6881e8f-9f92-4312-bb5e-06bbfb9fe0bb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2790a4e3fa0ff1ed9a9b9b0c2018108c9cbb1282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255530"
---
# <a name="how-to-test-the-http-node"></a><span data-ttu-id="777c9-102">HTTP ノードをテストする方法</span><span class="sxs-lookup"><span data-stu-id="777c9-102">How to Test the HTTP Node</span></span>
<span data-ttu-id="777c9-103">HTTP ノードをテストするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="777c9-103">Follow these steps to test the HTTP node.</span></span>  
  
### <a name="to-test-the-http-node"></a><span data-ttu-id="777c9-104">HTTP ノードをテストするには</span><span class="sxs-lookup"><span data-stu-id="777c9-104">To test the HTTP node</span></span>  
  
1.  <span data-ttu-id="777c9-105">PeopleSoft Enterprise でに移動**PeopleTools**、 **Integration Broker**、**モニター**、 **Monitor Message**です。</span><span class="sxs-lookup"><span data-stu-id="777c9-105">In PeopleSoft Enterprise, navigate to **PeopleTools**, **Integration Broker**, **Monitor**, **Monitor Message**.</span></span>  
  
     ![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")  
  
2.  <span data-ttu-id="777c9-106">クリックして、**ノードの状態**タブです。</span><span class="sxs-lookup"><span data-stu-id="777c9-106">Click the **Node Status** tab.</span></span>  
  
3.  <span data-ttu-id="777c9-107">**Message Node Name**フィールドに「 `MSEXTERNAL`、[] をクリックし、、**ルックアップ**アイコン。</span><span class="sxs-lookup"><span data-stu-id="777c9-107">In the **Message Node Name** field, enter `MSEXTERNAL`, and then click the **Lookup** icon.</span></span>  
  
4.  <span data-ttu-id="777c9-108">**Message Node Name** **MSEXTERNAL**です。</span><span class="sxs-lookup"><span data-stu-id="777c9-108">Under **Message Node Name**, select **MSEXTERNAL**.</span></span>  
  
     <span data-ttu-id="777c9-109">PeopleSoft が HTTP 経由で通信していることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="777c9-109">A message appears and indicates that PeopleSoft is communicating through HTTP.</span></span>  
  
     ![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")  
  
     <span data-ttu-id="777c9-110">メッセージが表示されない場合は、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="777c9-110">If you do not receive the message, verify the following:</span></span>  
  
    1.  <span data-ttu-id="777c9-111">IP アドレスおよびポートが、受信ポートおよびノードと一致していること。</span><span class="sxs-lookup"><span data-stu-id="777c9-111">The IP addresses and ports match between the receive port and the node.</span></span>  
  
    2.  <span data-ttu-id="777c9-112">BizTalk Server が実行されていること。</span><span class="sxs-lookup"><span data-stu-id="777c9-112">BizTalk Server is running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="777c9-113">参照</span><span class="sxs-lookup"><span data-stu-id="777c9-113">See Also</span></span>  
 [<span data-ttu-id="777c9-114">PeopleSoft HTTP ホストおよびポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="777c9-114">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)