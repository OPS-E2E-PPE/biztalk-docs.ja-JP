---
title: ESB ディスパッチャー コンポーネント |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85655b5f-4717-42d1-b005-0a5592d5653b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe377221034637eab23b70c50ccf48a8454a23bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294906"
---
# <a name="the-esb-dispatcher-component"></a><span data-ttu-id="d4b5a-102">ESB ディスパッチャー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d4b5a-102">The ESB Dispatcher Component</span></span>
<span data-ttu-id="d4b5a-103">Itinerary サービスのメッセージング ベース ESB ディスパッチャー コンポーネント内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-103">Messaging-based itinerary services are executed inside the ESB Dispatcher component.</span></span> <span data-ttu-id="d4b5a-104">ディスパッチャーのコンポーネントでは、送信メッセージのエンドポイントの場所のプロパティを動的に設定でき、メッセージを動的に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-104">The Dispatcher component can also dynamically set endpoint location properties for outbound messages and dynamically transform messages.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="d4b5a-105">コンポーネント プロパティ</span><span class="sxs-lookup"><span data-stu-id="d4b5a-105">Component Properties</span></span>  
 <span data-ttu-id="d4b5a-106">ディスパッチャーのコンポーネントには、6 つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-106">The Dispatcher component has six properties:</span></span>  
  
-   <span data-ttu-id="d4b5a-107">**RoutingServiceName**です。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-107">**RoutingServiceName**.</span></span> <span data-ttu-id="d4b5a-108">このプロパティは、メッセージ ベースのルーティング サービスの登録名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-108">This property specifies the registered name for the messaging-based routing service.</span></span> <span data-ttu-id="d4b5a-109">既定値は**Microsoft.Practices.ESB.Services.Routing**です。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-109">The default value is **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
-   <span data-ttu-id="d4b5a-110">**TransformServiceName**です。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-110">**TransformServiceName**.</span></span> <span data-ttu-id="d4b5a-111">このプロパティは、トランス フォームのメッセージング ベースのサービスの登録名を指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-111">This property specifies the registered name for the messaging-based transform service.</span></span> <span data-ttu-id="d4b5a-112">既定値は**Microsoft.Practices.ESB.Services.Transform**です。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-112">The default value is **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
-   <span data-ttu-id="d4b5a-113">**検証**です。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-113">**Validate**.</span></span> <span data-ttu-id="d4b5a-114">このプロパティは、メッセージが検証に使用する必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-114">This property specifies whether a message needs to be validated.</span></span>  
  
-   <span data-ttu-id="d4b5a-115">**有効になっている**です。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-115">**Enabled**.</span></span> <span data-ttu-id="d4b5a-116">このプロパティは、有効またはコンポーネントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-116">This property enables or disables the component.</span></span>  
  
-   <span data-ttu-id="d4b5a-117">**エンドポイント**です。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-117">**Endpoint**.</span></span> <span data-ttu-id="d4b5a-118">このプロパティは、BizTalk ESB Toolkit に登録されている形式での競合回避モジュールの接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-118">This property is a resolver connection string in a format registered with BizTalk ESB Toolkit.</span></span>  
  
-   <span data-ttu-id="d4b5a-119">**マップ名**です。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-119">**Map Name**.</span></span> <span data-ttu-id="d4b5a-120">このプロパティは、マップの完全修飾名または接続文字列の形式に登録されている[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="d4b5a-120">This property is either the fully qualified name of a map or a connection string format registered with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span></span>  
  
    -   <span data-ttu-id="d4b5a-121">マップ名の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d4b5a-121">The following is an example of a map name:</span></span>  
  
        ```  
        GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
        ```