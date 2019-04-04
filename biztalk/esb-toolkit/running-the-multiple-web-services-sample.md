---
title: 複数の Web を実行しているサービスのサンプル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b201c7c3-213a-4009-8872-5a4c1cbb8195
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765d9785bde94f363ea56178f3cc0f500381d4e9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997523"
---
# <a name="running-the-multiple-web-services-sample"></a><span data-ttu-id="879f5-102">複数の Web サービス サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="879f5-102">Running the Multiple Web Services Sample</span></span>
<span data-ttu-id="879f5-103">複数の Web サービス サンプルでは、行程導入サンプルで提供される Windows フォームのテスト クライアント アプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="879f5-103">The Multiple Web Services sample uses the Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="879f5-104">**複数の Web サービス サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="879f5-104">**To run the Multiple Web Services sample**</span></span>  
  
1. <span data-ttu-id="879f5-105">GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="879f5-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2. <span data-ttu-id="879f5-106">Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプルをし、Esb.Itinerary.Test.exe という名前のアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="879f5-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3. <span data-ttu-id="879f5-107">クリア、 **WCF サービスを使用して**クライアント側の旅行プランを利用できるようにチェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="879f5-107">Clear the **Use WCF Service** check box, so that a client-side itinerary can be utilized.</span></span>  
  
4. <span data-ttu-id="879f5-108">をクリックして、**ロード行程**ボタンをクリックし、\Source\Samples\MultipleWebServices\Itineraries フォルダーにあるサンプルのスケジュールのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="879f5-108">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the \Source\Samples\MultipleWebServices\Itineraries folder.</span></span>  
  
5. <span data-ttu-id="879f5-109">選択、**方法の 2 つのサービス**サービス操作のチェック ボックスの双方向の旅行プランをアプリケーションが実行されるようにします。</span><span class="sxs-lookup"><span data-stu-id="879f5-109">Select the **Two Way Service** check box so the application will perform a two-way itinerary services operation.</span></span>  
  
6. <span data-ttu-id="879f5-110">をクリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="879f5-110">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7. <span data-ttu-id="879f5-111">をクリックして、 **SubmitRequest**行程入口サービスに要求を送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="879f5-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="879f5-112">表示される応答メッセージの待機、**結果**ボックス。</span><span class="sxs-lookup"><span data-stu-id="879f5-112">Wait for a response message to appear in the **Result** box.</span></span>  
  
   <span data-ttu-id="879f5-113">ESB スケジュール サービスを複数の Web サービス サンプルで使用する方法については、[、複数 Web サービス サンプルのしくみ](../esb-toolkit/how-the-multiple-web-services-sample-works.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="879f5-113">For information about how the Multiple Web Services sample uses the ESB Itinerary service, see [How the Multiple Web Services Sample Works](../esb-toolkit/how-the-multiple-web-services-sample-works.md).</span></span>