---
title: 新しいゲートウェイ ノードを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- gateway nodes, creating
ms.assetid: e7c5f9a7-a58e-4661-9cb5-2414e31a57a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c26dd33fcdc4bd8ad43f03ef3fff6d006480a1c1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976163"
---
# <a name="how-to-create-a-new-gateway-node"></a><span data-ttu-id="1566e-102">新しいゲートウェイ ノードを作成する方法</span><span class="sxs-lookup"><span data-stu-id="1566e-102">How to Create a New Gateway Node</span></span>
<span data-ttu-id="1566e-103">PeopleSoft Enterprise に新しいゲートウェイ ノードを作成して構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="1566e-103">Follow these steps to create and configure a new Gateway node in PeopleSoft Enterprise.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="1566e-104">新しいゲートウェイ ノードを作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="1566e-104">To create and configure a new gateway node</span></span>  
  
1. <span data-ttu-id="1566e-105">Peoplesoft の左側のパネルでクリックして、**ノード定義**リンク。</span><span class="sxs-lookup"><span data-stu-id="1566e-105">In PeopleSoft, on the left panel, click the **Node Definitions** link.</span></span>  
  
2. <span data-ttu-id="1566e-106">をクリックして、**新しい値を追加**タブ。</span><span class="sxs-lookup"><span data-stu-id="1566e-106">Click the **Add a New Value** tab.</span></span>  
  
3. <span data-ttu-id="1566e-107">**ノード名**フィールドに、入力`MSEXTERNAL`、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1566e-107">In the **Node Name** field, enter `MSEXTERNAL`, and then click **Add**.</span></span>  
  
4. <span data-ttu-id="1566e-108">をクリックして、**ノード**タブをクリックし、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1566e-108">Click the **Node** tab, and enter the following information:</span></span>  
  
   1. <span data-ttu-id="1566e-109">**説明:** ノードの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1566e-109">**Description:** Enter a description for the node.</span></span>  
  
   2. <span data-ttu-id="1566e-110">**ノード型:** 選択**外部**します。</span><span class="sxs-lookup"><span data-stu-id="1566e-110">**Node Type:** Select **External**.</span></span>  
  
   3. <span data-ttu-id="1566e-111">**ルーティングの種類:** 選択**暗黙的な**します。</span><span class="sxs-lookup"><span data-stu-id="1566e-111">**Routing Type:** Select **Implicit**.</span></span>  
  
      <span data-ttu-id="1566e-112">![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")</span><span class="sxs-lookup"><span data-stu-id="1566e-112">![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")</span></span>  
  
5. <span data-ttu-id="1566e-113">をクリックして、**コネクタ**タブをクリックし、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1566e-113">Click the **Connectors** tab, and enter the following information:</span></span>  
  
   1. <span data-ttu-id="1566e-114">**ゲートウェイ ID:** 入力`LOCAL`します。</span><span class="sxs-lookup"><span data-stu-id="1566e-114">**Gateway ID:** Enter `LOCAL`.</span></span>  
  
   2. <span data-ttu-id="1566e-115">**コネクタ ID:** 入力`HTTPTARGET`します。</span><span class="sxs-lookup"><span data-stu-id="1566e-115">**Connector ID:** Enter `HTTPTARGET`.</span></span>  
  
      <span data-ttu-id="1566e-116">![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")</span><span class="sxs-lookup"><span data-stu-id="1566e-116">![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")</span></span>  
  
6. <span data-ttu-id="1566e-117">をクリックして、**ルックアップ**アイコン。</span><span class="sxs-lookup"><span data-stu-id="1566e-117">Click the **Lookup** icon.</span></span>  
  
7. <span data-ttu-id="1566e-118">**コネクタ ID**、クリックして、 **HTTPTARGET**リンク。</span><span class="sxs-lookup"><span data-stu-id="1566e-118">Under **Connector ID**, click the **HTTPTARGET** link.</span></span>  
  
    <span data-ttu-id="1566e-119">![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")</span><span class="sxs-lookup"><span data-stu-id="1566e-119">![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")</span></span>  
  
8. <span data-ttu-id="1566e-120">**プロパティ**タブで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1566e-120">On the **Properties** tab, enter the following information:</span></span>  
  
   1.  <span data-ttu-id="1566e-121">**ヘッダー:** 入力`Y`します。</span><span class="sxs-lookup"><span data-stu-id="1566e-121">**Header:** Enter `Y`.</span></span>  
  
   2.  <span data-ttu-id="1566e-122">**[Httpproperty]:** 入力`POST`します。</span><span class="sxs-lookup"><span data-stu-id="1566e-122">**HTTPPROPERTY:** Enter `POST`.</span></span>  
  
   3.  <span data-ttu-id="1566e-123">**[Primaryurl]:** IP アドレスとポート、ターゲット コンピューター (開発用コンピューター) を入力します。</span><span class="sxs-lookup"><span data-stu-id="1566e-123">**PrimaryURL:** Enter the IP address and port of the target computer (the development computer).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="1566e-124">**受信ポート**以前に設定します。</span><span class="sxs-lookup"><span data-stu-id="1566e-124">The **Receive Port** was previously set.</span></span>  
  
    <span data-ttu-id="1566e-125">![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")</span><span class="sxs-lookup"><span data-stu-id="1566e-125">![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1566e-126">参照</span><span class="sxs-lookup"><span data-stu-id="1566e-126">See Also</span></span>  
 [<span data-ttu-id="1566e-127">PeopleSoft の HTTP ホストとポートを作成する</span><span class="sxs-lookup"><span data-stu-id="1566e-127">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)