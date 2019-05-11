---
title: 統合ゲートウェイと HTTP 出力コネクタを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Integration Gateway
- gateway nodes, creating
- HTTP Output Connector
ms.assetid: a02ee533-07a8-42fa-a72a-7e5359b18f40
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b054893004f270ca352dc537c60ef8fcb719cba9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340832"
---
# <a name="how-to-configure-the-integration-gateway-and-http-output-connector"></a><span data-ttu-id="b2f31-102">統合ゲートウェイと HTTP 出力コネクタを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b2f31-102">How to Configure the Integration Gateway and HTTP Output Connector</span></span>
<span data-ttu-id="b2f31-103">統合ゲートウェイと HTTP 出力コネクタを構成するこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b2f31-103">Follow these steps to configure the Integration Gateway and HTTP Output Connector.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="b2f31-104">作成して新しいゲートウェイ ノードを構成するには</span><span class="sxs-lookup"><span data-stu-id="b2f31-104">To create and configure a new gateway node</span></span>  
  
1.  <span data-ttu-id="b2f31-105">Web ブラウザーでは、PeopleSoft アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="b2f31-105">In a Web browser, open the PeopleSoft application.</span></span>  
  
2.  <span data-ttu-id="b2f31-106">検索**PeopleTools**、 **Integration Broker**、し、**ゲートウェイ**。</span><span class="sxs-lookup"><span data-stu-id="b2f31-106">Locate **PeopleTools**, select **Integration Broker**, and then select **Gateways**.</span></span>  
  
3.  <span data-ttu-id="b2f31-107">**検索によって**フィールドに「 `LOCAL`、 をクリックし、**検索**します。</span><span class="sxs-lookup"><span data-stu-id="b2f31-107">In the **Search By** field, type `LOCAL`, and then click **Search**.</span></span>  
  
     <span data-ttu-id="b2f31-108">![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")</span><span class="sxs-lookup"><span data-stu-id="b2f31-108">![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")</span></span>  
  
4.  <span data-ttu-id="b2f31-109">入力`machine-name/PSIGW/PeopleSoftListeningConnector`に、**ゲートウェイ URL**エントリ。</span><span class="sxs-lookup"><span data-stu-id="b2f31-109">Enter `machine-name/PSIGW/PeopleSoftListeningConnector` into the **Gateway URL** entry.</span></span>  
  
     <span data-ttu-id="b2f31-110">![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")</span><span class="sxs-lookup"><span data-stu-id="b2f31-110">![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")</span></span>  
  
5.  <span data-ttu-id="b2f31-111">をクリックして**更新**、 をクリックし、**保存**します。</span><span class="sxs-lookup"><span data-stu-id="b2f31-111">Click **Refresh**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="b2f31-112">をクリックして、**プロパティ**リンク**HTTPTARGET**をその ID のプロパティと値の組み合わせを表示するには</span><span class="sxs-lookup"><span data-stu-id="b2f31-112">Click the **Properties** link for **HTTPTARGET** to view the properties/value combination for that ID.</span></span>  
  
     <span data-ttu-id="b2f31-113">ここでは、またはノード定義には、URL を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="b2f31-113">You can set the URL here, or at the Node Definition.</span></span> <span data-ttu-id="b2f31-114">ここでは、ノード レベルで、URL を設定します。</span><span class="sxs-lookup"><span data-stu-id="b2f31-114">For this discussion, set the URL at the Node level.</span></span>  
  
     <span data-ttu-id="b2f31-115">![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")</span><span class="sxs-lookup"><span data-stu-id="b2f31-115">![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f31-116">参照</span><span class="sxs-lookup"><span data-stu-id="b2f31-116">See Also</span></span>  
 [<span data-ttu-id="b2f31-117">PeopleSoft の HTTP ホストとポートを作成する</span><span class="sxs-lookup"><span data-stu-id="b2f31-117">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)