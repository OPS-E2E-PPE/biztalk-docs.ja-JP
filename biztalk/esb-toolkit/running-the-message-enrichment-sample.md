---
title: "メッセージ強化サンプルを実行している |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7015a2fe-3727-48f3-a2ed-c368e0630626
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4ed3b3ebc24a908dfefd70711db0d40638c2d3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-message-enrichment-sample"></a><span data-ttu-id="82f3d-102">メッセージ強化サンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="82f3d-102">Running the Message Enrichment Sample</span></span>
<span data-ttu-id="82f3d-103">Message Enrichment サンプルでは、行程入り口サンプルに用意されている、テスト クライアントの Windows フォーム アプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="82f3d-103">The Message Enrichment sample uses a Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="82f3d-104">**Message Enrichment サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="82f3d-104">**To run Message Enrichment sample**</span></span>  
  
1.  <span data-ttu-id="82f3d-105">GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="82f3d-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="82f3d-106">Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプル、および Esb.Itinerary.Test.exe をという名前のアプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="82f3d-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="82f3d-107">クリア、**を使用して WCF サービス**クライアント側の日程を利用するようにチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="82f3d-107">Clear the **Use WCF Service** check box so that a client-side itinerary can be utilized.</span></span>  
  
4.  <span data-ttu-id="82f3d-108">クリックして、**ロード行程**ボタンをクリックし、\Source\Samples\MessageEnrichment\Itineraries フォルダーにあるサンプルの日程のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="82f3d-108">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the \Source\Samples\MessageEnrichment\Itineraries folder.</span></span>  
  
5.  <span data-ttu-id="82f3d-109">クリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\MessageEnrichment\Test\ フォルダーから OrderDoc.xml サンプル メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="82f3d-109">Click the **LoadMessage** button, and then select the OrderDoc.xml sample message from the \Source\Samples\MessageEnrichment\Test\ folder.</span></span>  
  
6.  <span data-ttu-id="82f3d-110">クリックして、 **SubmitRequest**行程入り口サービスに要求を送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="82f3d-110">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span>  
  
7.  <span data-ttu-id="82f3d-111">参照 C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out\\%MessageID%.xml 出力メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="82f3d-111">Browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out\\%MessageID%.xml to see the output message.</span></span>  
  
 <span data-ttu-id="82f3d-112">Message Enrichment サンプルのしくみについては、次を参照してください。 [「メッセージ強化サンプルの動作](../esb-toolkit/how-the-message-enrichment-sample-works.md)です。</span><span class="sxs-lookup"><span data-stu-id="82f3d-112">For information about how the Message Enrichment sample works, see [How the Message Enrichment Sample Works](../esb-toolkit/how-the-message-enrichment-sample-works.md).</span></span>