---
title: 手順 4:ソリューションのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 60c39521-eee2-49f7-a9f9-2dfb9ab468e9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56869aa22ab54efe78838403ae060154b98a001a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392472"
---
# <a name="step-4-test-the-solution"></a><span data-ttu-id="50372-102">手順 4:ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="50372-102">Step 4: Test the Solution</span></span>
<span data-ttu-id="50372-103">このトピックの「ファイルと関連付けられているフォルダーにダミー要求メッセージを削除することにより、ソリューションをテストするポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="50372-103">In this topic you test the solution by dropping a dummy request message in the folder you associated with the FILE receive port.</span></span> <span data-ttu-id="50372-104">呼び出すためにのみダミー要求メッセージをドロップする前述のように、 **Wcf-webhttp**ポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="50372-104">As explained in, you drop a dummy request message only to invoke the **WCF-WebHttp** send port.</span></span> <span data-ttu-id="50372-105">次のようなダミー要求メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="50372-105">You can create a dummy request message like the following:</span></span>  
  
```  
<Root>  
  <Input>Azure Market Place REST API integration</Input>  
<Root>  
```  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="50372-106">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="50372-106">To test the solution</span></span>  
  
1.  <span data-ttu-id="50372-107">BizTalk Server 管理コンソールから開始**BizTalk アプリケーション 1**します。</span><span class="sxs-lookup"><span data-stu-id="50372-107">From the BizTalk Server Administration Console, start **BizTalk Application 1**.</span></span> <span data-ttu-id="50372-108">これは、前の手順で作成したすべてのポートを開始します。</span><span class="sxs-lookup"><span data-stu-id="50372-108">This starts all the ports that we created in previous steps.</span></span>  
  
2.  <span data-ttu-id="50372-109">Windows エクスプ ローラーを開き、ファイルと関連付けた場所に移動して受信場所。</span><span class="sxs-lookup"><span data-stu-id="50372-109">Open Windows Explorer, and navigate to the location that you associated with the FILE receive location.</span></span> <span data-ttu-id="50372-110">この場所で、ダミーの要求メッセージをコピーします。</span><span class="sxs-lookup"><span data-stu-id="50372-110">At this location, copy the dummy request message.</span></span>  
  
3.  <span data-ttu-id="50372-111">ファイルが、REST インターフェイスから応答メッセージを処理する FILE 送信ポートと関連付けられている場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="50372-111">When the file disappears, check the location you associated with FILE send port that consumes the response message from the REST interface.</span></span> <span data-ttu-id="50372-112">XML 応答メッセージを含めることが必要があります。</span><span class="sxs-lookup"><span data-stu-id="50372-112">It should contain an XML response message.</span></span> <span data-ttu-id="50372-113">遅延は米国航空の実行からのフライトの詳細を表示する XML メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="50372-113">Open the XML message to see the details of flights from US air carries that are delayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50372-114">参照</span><span class="sxs-lookup"><span data-stu-id="50372-114">See Also</span></span>  
 [<span data-ttu-id="50372-115">チュートリアル 5:BizTalk Server を使用して REST インターフェイスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="50372-115">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)