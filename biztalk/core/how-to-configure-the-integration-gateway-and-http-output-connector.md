---
title: 統合ゲートウェイと HTTP 出力コネクタを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: acfa52be85a664432af95af0ca292e9cc394c6ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247922"
---
# <a name="how-to-configure-the-integration-gateway-and-http-output-connector"></a><span data-ttu-id="b60cb-102">統合ゲートウェイと HTTP 出力コネクタを構成する方法</span><span class="sxs-lookup"><span data-stu-id="b60cb-102">How to Configure the Integration Gateway and HTTP Output Connector</span></span>
<span data-ttu-id="b60cb-103">統合ゲートウェイと HTTP 出力コネクタを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b60cb-103">Follow these steps to configure the Integration Gateway and HTTP Output Connector.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="b60cb-104">新しいゲートウェイ ノードを作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="b60cb-104">To create and configure a new gateway node</span></span>  
  
1.  <span data-ttu-id="b60cb-105">Web ブラウザーで、PeopleSoft アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="b60cb-105">In a Web browser, open the PeopleSoft application.</span></span>  
  
2.  <span data-ttu-id="b60cb-106">検索**PeopleTools** **Integration Broker**、し、**ゲートウェイ**です。</span><span class="sxs-lookup"><span data-stu-id="b60cb-106">Locate **PeopleTools**, select **Integration Broker**, and then select **Gateways**.</span></span>  
  
3.  <span data-ttu-id="b60cb-107">**検索によって**フィールドに「 `LOCAL`、クリックしてして**検索**です。</span><span class="sxs-lookup"><span data-stu-id="b60cb-107">In the **Search By** field, type `LOCAL`, and then click **Search**.</span></span>  
  
     ![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")  
  
4.  <span data-ttu-id="b60cb-108">入力`machine-name/PSIGW/PeopleSoftListeningConnector`に、**ゲートウェイ URL**エントリです。</span><span class="sxs-lookup"><span data-stu-id="b60cb-108">Enter `machine-name/PSIGW/PeopleSoftListeningConnector` into the **Gateway URL** entry.</span></span>  
  
     ![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")  
  
5.  <span data-ttu-id="b60cb-109">をクリックして**更新**、クリックして**保存**です。</span><span class="sxs-lookup"><span data-stu-id="b60cb-109">Click **Refresh**, and then click **Save**.</span></span>  
  
6.  <span data-ttu-id="b60cb-110">クリックして、**プロパティ**リンク**HTTPTARGET**をその ID のプロパティ/値の組み合わせを表示するには</span><span class="sxs-lookup"><span data-stu-id="b60cb-110">Click the **Properties** link for **HTTPTARGET** to view the properties/value combination for that ID.</span></span>  
  
     <span data-ttu-id="b60cb-111">URL をここか、またはノード定義に設定できます。</span><span class="sxs-lookup"><span data-stu-id="b60cb-111">You can set the URL here, or at the Node Definition.</span></span> <span data-ttu-id="b60cb-112">ここでの説明では、URL をノード レベルに設定します。</span><span class="sxs-lookup"><span data-stu-id="b60cb-112">For this discussion, set the URL at the Node level.</span></span>  
  
     ![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")  
  
## <a name="see-also"></a><span data-ttu-id="b60cb-113">参照</span><span class="sxs-lookup"><span data-stu-id="b60cb-113">See Also</span></span>  
 [<span data-ttu-id="b60cb-114">PeopleSoft HTTP ホストおよびポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="b60cb-114">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)