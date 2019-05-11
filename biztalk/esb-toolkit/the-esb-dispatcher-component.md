---
title: ESB ディスパッチャー コンポーネント |Microsoft Docs
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
ms.openlocfilehash: 0a3a46e9a8fab078b9599fce9d149781bf140001
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399836"
---
# <a name="the-esb-dispatcher-component"></a><span data-ttu-id="4fc8e-102">ESB ディスパッチャー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4fc8e-102">The ESB Dispatcher Component</span></span>
<span data-ttu-id="4fc8e-103">ESB ディスパッチャー コンポーネント内でメッセージング ベースのスケジュール サービスが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-103">Messaging-based itinerary services are executed inside the ESB Dispatcher component.</span></span> <span data-ttu-id="4fc8e-104">ディスパッチャー コンポーネントでは、送信メッセージのエンドポイントの場所のプロパティを動的に設定でき、メッセージを動的に変換することができます。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-104">The Dispatcher component can also dynamically set endpoint location properties for outbound messages and dynamically transform messages.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="4fc8e-105">コンポーネント プロパティ</span><span class="sxs-lookup"><span data-stu-id="4fc8e-105">Component Properties</span></span>  
 <span data-ttu-id="4fc8e-106">ディスパッチャー コンポーネントでは、6 つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-106">The Dispatcher component has six properties:</span></span>  
  
- <span data-ttu-id="4fc8e-107">**RoutingServiceName**します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-107">**RoutingServiceName**.</span></span> <span data-ttu-id="4fc8e-108">このプロパティは、メッセージング ベースのルーティング サービスの登録名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-108">This property specifies the registered name for the messaging-based routing service.</span></span> <span data-ttu-id="4fc8e-109">既定値は**Microsoft.Practices.ESB.Services.Routing**します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-109">The default value is **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
- <span data-ttu-id="4fc8e-110">**TransformServiceName**します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-110">**TransformServiceName**.</span></span> <span data-ttu-id="4fc8e-111">このプロパティは、変換のメッセージング ベースのサービスの登録名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-111">This property specifies the registered name for the messaging-based transform service.</span></span> <span data-ttu-id="4fc8e-112">既定値は**Microsoft.Practices.ESB.Services.Transform**します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-112">The default value is **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
- <span data-ttu-id="4fc8e-113">**検証**です。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-113">**Validate**.</span></span> <span data-ttu-id="4fc8e-114">このプロパティは、メッセージを検証する必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-114">This property specifies whether a message needs to be validated.</span></span>  
  
- <span data-ttu-id="4fc8e-115">**有効になっている**します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-115">**Enabled**.</span></span> <span data-ttu-id="4fc8e-116">このプロパティは、有効またはコンポーネントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-116">This property enables or disables the component.</span></span>  
  
- <span data-ttu-id="4fc8e-117">**エンドポイント**します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-117">**Endpoint**.</span></span> <span data-ttu-id="4fc8e-118">このプロパティは、BizTalk ESB Toolkit に登録されている形式での競合回避モジュールの接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-118">This property is a resolver connection string in a format registered with BizTalk ESB Toolkit.</span></span>  
  
- <span data-ttu-id="4fc8e-119">**マップ名**します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-119">**Map Name**.</span></span> <span data-ttu-id="4fc8e-120">このプロパティは、マップの完全修飾名または接続文字列の形式に登録されている[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="4fc8e-120">This property is either the fully qualified name of a map or a connection string format registered with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span></span>  
  
  -   <span data-ttu-id="4fc8e-121">マップ名の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4fc8e-121">The following is an example of a map name:</span></span>  
  
      ```  
      GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
      ```