---
title: HTTP ノードをテストする方法 |Microsoft Docs
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
ms.openlocfilehash: 27e3ebdc1c75ba0e42e5af8a57e194d3ab363753
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333881"
---
# <a name="how-to-test-the-http-node"></a><span data-ttu-id="23261-102">HTTP ノードをテストする方法</span><span class="sxs-lookup"><span data-stu-id="23261-102">How to Test the HTTP Node</span></span>
<span data-ttu-id="23261-103">HTTP ノードをテストする次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="23261-103">Follow these steps to test the HTTP node.</span></span>  
  
### <a name="to-test-the-http-node"></a><span data-ttu-id="23261-104">HTTP ノードをテストするには</span><span class="sxs-lookup"><span data-stu-id="23261-104">To test the HTTP node</span></span>  
  
1.  <span data-ttu-id="23261-105">PeopleSoft Enterprise に移動します。 **PeopleTools**、 **Integration Broker**、**モニター**、**メッセージの監視**します。</span><span class="sxs-lookup"><span data-stu-id="23261-105">In PeopleSoft Enterprise, navigate to **PeopleTools**, **Integration Broker**, **Monitor**, **Monitor Message**.</span></span>  
  
     <span data-ttu-id="23261-106">![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")</span><span class="sxs-lookup"><span data-stu-id="23261-106">![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")</span></span>  
  
2.  <span data-ttu-id="23261-107">をクリックして、**ノードの状態**タブ。</span><span class="sxs-lookup"><span data-stu-id="23261-107">Click the **Node Status** tab.</span></span>  
  
3.  <span data-ttu-id="23261-108">**Message Node Name**フィールドに、入力`MSEXTERNAL`、 をクリックし、**ルックアップ**アイコン。</span><span class="sxs-lookup"><span data-stu-id="23261-108">In the **Message Node Name** field, enter `MSEXTERNAL`, and then click the **Lookup** icon.</span></span>  
  
4.  <span data-ttu-id="23261-109">**Message Node Name**、 **MSEXTERNAL**します。</span><span class="sxs-lookup"><span data-stu-id="23261-109">Under **Message Node Name**, select **MSEXTERNAL**.</span></span>  
  
     <span data-ttu-id="23261-110">メッセージが表示され、PeopleSoft が HTTP 経由で通信することを示します。</span><span class="sxs-lookup"><span data-stu-id="23261-110">A message appears and indicates that PeopleSoft is communicating through HTTP.</span></span>  
  
     <span data-ttu-id="23261-111">![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")</span><span class="sxs-lookup"><span data-stu-id="23261-111">![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")</span></span>  
  
     <span data-ttu-id="23261-112">メッセージを受け取らない場合は、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="23261-112">If you do not receive the message, verify the following:</span></span>  
  
    1.  <span data-ttu-id="23261-113">IP アドレスとポート、受信ポートと、ノードの間と一致します。</span><span class="sxs-lookup"><span data-stu-id="23261-113">The IP addresses and ports match between the receive port and the node.</span></span>  
  
    2.  <span data-ttu-id="23261-114">BizTalk Server が実行されています。</span><span class="sxs-lookup"><span data-stu-id="23261-114">BizTalk Server is running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23261-115">参照</span><span class="sxs-lookup"><span data-stu-id="23261-115">See Also</span></span>  
 [<span data-ttu-id="23261-116">PeopleSoft の HTTP ホストとポートを作成する</span><span class="sxs-lookup"><span data-stu-id="23261-116">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)