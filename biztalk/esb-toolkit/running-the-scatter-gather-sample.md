---
title: スキャッター/ギャザー サンプルを実行する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53676974-ea1f-4c95-9dbb-98fff92286fa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cda345b5a96f36125432e454b5f239f756a76652
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023760"
---
# <a name="running-the-scatter-gather-sample"></a><span data-ttu-id="68947-102">スキャッター/ギャザー サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="68947-102">Running the Scatter-Gather Sample</span></span>
<span data-ttu-id="68947-103">スキャッター/ギャザー サンプルを使用して、Windows フォームは、旅行プラン サービスの機能がこのパターンでどのように適用されるかを示すために、旅行プラン サンプルで提供されるクライアント アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="68947-103">The Scatter-Gather sample uses a the Windows Forms test client application provided with the Itinerary On-Ramp sample to demonstrate how this pattern applies the features of the Itinerary service.</span></span>  
  
 <span data-ttu-id="68947-104">**スキャッター/ギャザー サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="68947-104">**To run the Scatter-Gather sample**</span></span>  
  
1. <span data-ttu-id="68947-105">GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="68947-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="68947-106">Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルをし、Esb.Itinerary.Test.exe という名前のアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="68947-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="68947-107">をクリックして、 **LoadItinerary**ボタンをクリックし、\Source\Samples\ScatterGather\Itineraries フォルダーから ScatterGatherItinerary.xml という名前のサンプルの旅行プランを選択します。</span><span class="sxs-lookup"><span data-stu-id="68947-107">Click the **LoadItinerary** button, and then select the sample itinerary named ScatterGatherItinerary.xml from the \Source\Samples\ScatterGather\Itineraries folder.</span></span>  
  
4. <span data-ttu-id="68947-108">クリア、**は Request Response**サービス操作のチェック ボックスを一方向の旅行プランをアプリケーションが実行されるようにします。</span><span class="sxs-lookup"><span data-stu-id="68947-108">Clear the **Is Request Response** check box so the application will perform a one-way itinerary services operation.</span></span>  
  
5. <span data-ttu-id="68947-109">(省略可能)設定、 **WCF サービスを使用して**受信場所のチェック ボックス、OnRamp.Itinerary.Response.WCF を使用するアプリケーションの場合、既定ではなく OnRamp.Itinerary.Response.SOAP 受信場所。</span><span class="sxs-lookup"><span data-stu-id="68947-109">(Optional) Set the **Use WCF Service** check box if you want the application to use the OnRamp.Itinerary.Response.WCF receive location instead of the default OnRamp.Itinerary.Response.SOAP receive location.</span></span>  
  
6. <span data-ttu-id="68947-110">をクリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="68947-110">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7. <span data-ttu-id="68947-111">をクリックして、 **SubmitRequest**行程入口サービスに要求を送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="68947-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="68947-112">応答メッセージを表示するフォルダー \Source\Samples\DynamicResolution\Test\FileDrop\Out を開きます。</span><span class="sxs-lookup"><span data-stu-id="68947-112">Open the folder \Source\Samples\DynamicResolution\Test\FileDrop\Out to see the response message.</span></span>  
  
   <span data-ttu-id="68947-113">散布図を収集サンプルが ESB スケジュール サービスを使用する方法については、[、スキャッター/ギャザー サンプルのしくみ](../esb-toolkit/how-the-scatter-gather-sample-works.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68947-113">For information about how the Scatter Gather sample uses the ESB Itinerary service, see [How the Scatter-Gather Sample Works](../esb-toolkit/how-the-scatter-gather-sample-works.md).</span></span>