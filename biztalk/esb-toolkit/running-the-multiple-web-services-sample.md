---
title: 複数の Web を実行しているサービスのサンプル |Microsoft ドキュメント
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
ms.openlocfilehash: 4ec54fabb7ed140fd88b5a2d5a07d788805c741e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294802"
---
# <a name="running-the-multiple-web-services-sample"></a><span data-ttu-id="681bc-102">複数の Web サービス サンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="681bc-102">Running the Multiple Web Services Sample</span></span>
<span data-ttu-id="681bc-103">複数の Web サービス サンプルでは、Windows フォーム クライアント テスト アプリケーション行程入り口サンプルを使用します。</span><span class="sxs-lookup"><span data-stu-id="681bc-103">The Multiple Web Services sample uses the Windows Forms test client application provided with the Itinerary On-Ramp sample.</span></span>  
  
 <span data-ttu-id="681bc-104">**複数の Web サービス サンプルを実行するには**</span><span class="sxs-lookup"><span data-stu-id="681bc-104">**To run the Multiple Web Services sample**</span></span>  
  
1.  <span data-ttu-id="681bc-105">GlobalBank.ESB アプリケーションが既に実行されていない場合は、Microsoft BizTalk 管理コンソールを使用して、開始します。</span><span class="sxs-lookup"><span data-stu-id="681bc-105">If the GlobalBank.ESB application is not already running, use the Microsoft BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="681bc-106">Windows エクスプ ローラーでフォルダー \Source\Samples\Itinerary\Source\ESB を開きます。インストールした Itinerary.Test、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]サンプル、および Esb.Itinerary.Test.exe をという名前のアプリケーションを開始します。</span><span class="sxs-lookup"><span data-stu-id="681bc-106">In Windows Explorer, open the folder \Source\Samples\Itinerary\Source\ESB.Itinerary.Test where you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] samples, and then start the application named Esb.Itinerary.Test.exe.</span></span>  
  
3.  <span data-ttu-id="681bc-107">クリア、**を使用して WCF サービス**できるように、クライアント側の日程を利用できますが、チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="681bc-107">Clear the **Use WCF Service** check box, so that a client-side itinerary can be utilized.</span></span>  
  
4.  <span data-ttu-id="681bc-108">クリックして、**ロード行程**ボタンをクリックし、\Source\Samples\MultipleWebServices\Itineraries フォルダーにあるサンプルの日程のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="681bc-108">Click the **Load Itinerary** button, and then select one of the sample itineraries located in the \Source\Samples\MultipleWebServices\Itineraries folder.</span></span>  
  
5.  <span data-ttu-id="681bc-109">選択、 **2 つの方法サービス**サービス操作のチェック ボックスをアプリケーションで双方向の日程を実行するようにします。</span><span class="sxs-lookup"><span data-stu-id="681bc-109">Select the **Two Way Service** check box so the application will perform a two-way itinerary services operation.</span></span>  
  
6.  <span data-ttu-id="681bc-110">クリックして、 **LoadMessage**ボタンをクリックし、\Source\Samples\Itinerary\Test\Data フォルダーから NAOrderDoc.xml サンプル メッセージを選択します。</span><span class="sxs-lookup"><span data-stu-id="681bc-110">Click the **LoadMessage** button, and then select the NAOrderDoc.xml sample message from the \Source\Samples\Itinerary\Test\Data folder.</span></span>  
  
7.  <span data-ttu-id="681bc-111">クリックして、 **SubmitRequest**行程入り口サービスに要求を送信するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="681bc-111">Click the **SubmitRequest** button to send the request to the Itinerary On-Ramp service.</span></span> <span data-ttu-id="681bc-112">表示される応答メッセージの待機、**結果**ボックス。</span><span class="sxs-lookup"><span data-stu-id="681bc-112">Wait for a response message to appear in the **Result** box.</span></span>  
  
 <span data-ttu-id="681bc-113">複数の Web サービス サンプルでの ESB 行程サービスの使用方法については、次を参照してください。 [「複数 Web サービス サンプルの動作](../esb-toolkit/how-the-multiple-web-services-sample-works.md)です。</span><span class="sxs-lookup"><span data-stu-id="681bc-113">For information about how the Multiple Web Services sample uses the ESB Itinerary service, see [How the Multiple Web Services Sample Works](../esb-toolkit/how-the-multiple-web-services-sample-works.md).</span></span>