---
title: メッセージ強化サンプルを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7015a2fe-3727-48f3-a2ed-c368e0630626
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afa17db3817a485f11c63a88c796c93e6ec5354b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242862"
---
# <a name="running-the-message-enrichment-sample"></a><span data-ttu-id="ecfaf-102">メッセージ強化サンプルを実行しています。</span><span class="sxs-lookup"><span data-stu-id="ecfaf-102">Running the Message Enrichment Sample</span></span>
<span data-ttu-id="ecfaf-103">メッセージ強化サンプルでは、行程導入サンプルで提供される Windows フォームのテスト クライアント アプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ecfaf-103">The Message Enrichment sample uses a Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="ecfaf-104">**Message Enrichment サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="ecfaf-104">**To run Message Enrichment sample**</span></span>  
  
1. <span data-ttu-id="ecfaf-105">GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="ecfaf-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="ecfaf-106">Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルをし、Esb.Itinerary.Test.exe という名前のアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="ecfaf-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="ecfaf-107">クリア、 **WCF サービスを使用して**クライアント側の旅行プランを利用できるようにチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="ecfaf-107">Clear the **Use WCF Service** check box so that a client-side itinerary can be utilized.</span></span>  
  
4. <span data-ttu-id="ecfaf-108">をクリックして、**ロード行程**ボタンをクリックし、\Source\Samples\MessageEnrichment\Itineraries フォルダーにあるサンプルのスケジュールのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecfaf-108">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the \Source\Samples\MessageEnrichment\Itineraries folder.</span></span>  
  
5. <span data-ttu-id="ecfaf-109">をクリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\MessageEnrichment\Test\ フォルダーから OrderDoc.xml サンプル メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecfaf-109">Click the **LoadMessage** button, and then select the OrderDoc.xml sample message from the \Source\Samples\MessageEnrichment\Test\ folder.</span></span>  
  
6. <span data-ttu-id="ecfaf-110">をクリックして、 **SubmitRequest**行程入口サービスに要求を送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecfaf-110">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span>  
  
7. <span data-ttu-id="ecfaf-111">C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out 参照\\%MessageID%.xml 出力メッセージを確認します。</span><span class="sxs-lookup"><span data-stu-id="ecfaf-111">Browse to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out\\%MessageID%.xml to see the output message.</span></span>  
  
   <span data-ttu-id="ecfaf-112">メッセージ強化サンプルのしくみについては、次を参照してください。 [、メッセージ強化サンプルのしくみ](../esb-toolkit/how-the-message-enrichment-sample-works.md)します。</span><span class="sxs-lookup"><span data-stu-id="ecfaf-112">For information about how the Message Enrichment sample works, see [How the Message Enrichment Sample Works](../esb-toolkit/how-the-message-enrichment-sample-works.md).</span></span>