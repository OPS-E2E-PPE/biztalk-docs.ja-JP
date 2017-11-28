---
title: "新しいゲートウェイ ノードを作成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: gateway nodes, creating
ms.assetid: e7c5f9a7-a58e-4661-9cb5-2414e31a57a3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b371243d58389415349d5a88c05b7bf312e70ef9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-new-gateway-node"></a><span data-ttu-id="dca2d-102">新しいゲートウェイ ノードを作成する方法</span><span class="sxs-lookup"><span data-stu-id="dca2d-102">How to Create a New Gateway Node</span></span>
<span data-ttu-id="dca2d-103">PeopleSoft Enterprise に新しいゲートウェイ ノードを作成して構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dca2d-103">Follow these steps to create and configure a new Gateway node in PeopleSoft Enterprise.</span></span>  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a><span data-ttu-id="dca2d-104">新しいゲートウェイ ノードを作成および構成するには</span><span class="sxs-lookup"><span data-stu-id="dca2d-104">To create and configure a new gateway node</span></span>  
  
1.  <span data-ttu-id="dca2d-105">Peoplesoft の左側のパネルでをクリックして、**ノード定義**リンクします。</span><span class="sxs-lookup"><span data-stu-id="dca2d-105">In PeopleSoft, on the left panel, click the **Node Definitions** link.</span></span>  
  
2.  <span data-ttu-id="dca2d-106">クリックして、**新しい値を追加**タブです。</span><span class="sxs-lookup"><span data-stu-id="dca2d-106">Click the **Add a New Value** tab.</span></span>  
  
3.  <span data-ttu-id="dca2d-107">**ノード名**フィールドに「 `MSEXTERNAL`、クリックしてして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="dca2d-107">In the **Node Name** field, enter `MSEXTERNAL`, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="dca2d-108">クリックして、**ノード**タブをクリックし、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dca2d-108">Click the **Node** tab, and enter the following information:</span></span>  
  
    1.  <span data-ttu-id="dca2d-109">**説明:**ノードの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="dca2d-109">**Description:** Enter a description for the node.</span></span>  
  
    2.  <span data-ttu-id="dca2d-110">**ノード型:**選択**外部**です。</span><span class="sxs-lookup"><span data-stu-id="dca2d-110">**Node Type:** Select **External**.</span></span>  
  
    3.  <span data-ttu-id="dca2d-111">**ルーティングの種類:**選択**暗黙**です。</span><span class="sxs-lookup"><span data-stu-id="dca2d-111">**Routing Type:** Select **Implicit**.</span></span>  
  
     ![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")  
  
5.  <span data-ttu-id="dca2d-112">クリックして、**コネクタ**タブをクリックし、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dca2d-112">Click the **Connectors** tab, and enter the following information:</span></span>  
  
    1.  <span data-ttu-id="dca2d-113">**ゲートウェイ ID:**入力`LOCAL`です。</span><span class="sxs-lookup"><span data-stu-id="dca2d-113">**Gateway ID:** Enter `LOCAL`.</span></span>  
  
    2.  <span data-ttu-id="dca2d-114">**コネクタ ID:**入力`HTTPTARGET`です。</span><span class="sxs-lookup"><span data-stu-id="dca2d-114">**Connector ID:** Enter `HTTPTARGET`.</span></span>  
  
     ![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")  
  
6.  <span data-ttu-id="dca2d-115">クリックして、**ルックアップ**アイコン。</span><span class="sxs-lookup"><span data-stu-id="dca2d-115">Click the **Lookup** icon.</span></span>  
  
7.  <span data-ttu-id="dca2d-116">**コネクタ ID**をクリックして、 **HTTPTARGET**リンクします。</span><span class="sxs-lookup"><span data-stu-id="dca2d-116">Under **Connector ID**, click the **HTTPTARGET** link.</span></span>  
  
     ![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")  
  
8.  <span data-ttu-id="dca2d-117">**プロパティ** タブで、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="dca2d-117">On the **Properties** tab, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="dca2d-118">**ヘッダー:**入力`Y`です。</span><span class="sxs-lookup"><span data-stu-id="dca2d-118">**Header:** Enter `Y`.</span></span>  
  
    2.  <span data-ttu-id="dca2d-119">**HTTPPROPERTY:**入力`POST`です。</span><span class="sxs-lookup"><span data-stu-id="dca2d-119">**HTTPPROPERTY:** Enter `POST`.</span></span>  
  
    3.  <span data-ttu-id="dca2d-120">**[Primaryurl]:**ターゲット コンピューター (開発用コンピューター) のポートと IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="dca2d-120">**PrimaryURL:** Enter the IP address and port of the target computer (the development computer).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dca2d-121">**受信ポート**以前に設定します。</span><span class="sxs-lookup"><span data-stu-id="dca2d-121">The **Receive Port** was previously set.</span></span>  
  
     ![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")  
  
## <a name="see-also"></a><span data-ttu-id="dca2d-122">参照</span><span class="sxs-lookup"><span data-stu-id="dca2d-122">See Also</span></span>  
 [<span data-ttu-id="dca2d-123">PeopleSoft HTTP ホストおよびポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="dca2d-123">Creating a PeopleSoft HTTP Host and Port</span></span>](../core/creating-a-peoplesoft-http-host-and-port.md)