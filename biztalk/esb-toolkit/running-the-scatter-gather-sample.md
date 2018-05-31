---
title: スキャッター/ギャザー サンプルを実行している |Microsoft ドキュメント
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
ms.openlocfilehash: 7dcafa519aac074ccb339373a591b590846c9341
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294658"
---
# <a name="running-the-scatter-gather-sample"></a><span data-ttu-id="c2aad-102">スキャッター/ギャザー サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="c2aad-102">Running the Scatter-Gather Sample</span></span>
<span data-ttu-id="c2aad-103">スキャッター/ギャザー サンプルでは、Windows フォームは、このパターンが行程サービスの機能を適用する方法を示すために、行程入り口サンプルに用意されているクライアント アプリケーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="c2aad-103">The Scatter-Gather sample uses a the Windows Forms test client application provided with the Itinerary On-Ramp sample to demonstrate how this pattern applies the features of the Itinerary service.</span></span>  
  
 <span data-ttu-id="c2aad-104">**スキャッター/ギャザー サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="c2aad-104">**To run the Scatter-Gather sample**</span></span>  
  
1.  <span data-ttu-id="c2aad-105">GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="c2aad-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="c2aad-106">Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプル、および Esb.Itinerary.Test.exe をという名前のアプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c2aad-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="c2aad-107">クリックして、 **LoadItinerary**ボタンをクリックし、サンプル itinerary \Source\Samples\ScatterGather\Itineraries フォルダーから ScatterGatherItinerary.xml をという名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2aad-107">Click the **LoadItinerary** button, and then select the sample itinerary named ScatterGatherItinerary.xml from the \Source\Samples\ScatterGather\Itineraries folder.</span></span>  
  
4.  <span data-ttu-id="c2aad-108">クリア、**要求応答の**サービス操作のチェック ボックスをアプリケーションで一方向の日程を実行するようにします。</span><span class="sxs-lookup"><span data-stu-id="c2aad-108">Clear the **Is Request Response** check box so the application will perform a one-way itinerary services operation.</span></span>  
  
5.  <span data-ttu-id="c2aad-109">(省略可能)設定、 **WCF サービスを使用して**する場合は、アプリケーション、OnRamp.Itinerary.Response.WCF を使用する チェック ボックスの受信場所、既定ではなく OnRamp.Itinerary.Response.SOAP 受信場所。</span><span class="sxs-lookup"><span data-stu-id="c2aad-109">(Optional) Set the **Use WCF Service** check box if you want the application to use the OnRamp.Itinerary.Response.WCF receive location instead of the default OnRamp.Itinerary.Response.SOAP receive location.</span></span>  
  
6.  <span data-ttu-id="c2aad-110">クリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2aad-110">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7.  <span data-ttu-id="c2aad-111">クリックして、 **SubmitRequest**行程入り口サービスに要求を送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c2aad-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="c2aad-112">応答メッセージを表示するフォルダー \Source\Samples\DynamicResolution\Test\FileDrop\Out を開きます。</span><span class="sxs-lookup"><span data-stu-id="c2aad-112">Open the folder \Source\Samples\DynamicResolution\Test\FileDrop\Out to see the response message.</span></span>  
  
 <span data-ttu-id="c2aad-113">散布図を収集サンプルが、ESB 行程サービスでどのように使用する方法については、次を参照してください。 [「スキャッター/ギャザー サンプルの動作](../esb-toolkit/how-the-scatter-gather-sample-works.md)です。</span><span class="sxs-lookup"><span data-stu-id="c2aad-113">For information about how the Scatter Gather sample uses the ESB Itinerary service, see [How the Scatter-Gather Sample Works](../esb-toolkit/how-the-scatter-gather-sample-works.md).</span></span>