---
title: "手順 4: ソリューションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60c39521-eee2-49f7-a9f9-2dfb9ab468e9
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64f0ae6cb124ea9d8710797790b9176289faafc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-the-solution"></a><span data-ttu-id="87a9c-102">手順 4: ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="87a9c-102">Step 4: Test the Solution</span></span>
<span data-ttu-id="87a9c-103">このトピックでは、FILE 受信ポートに関連付けられているフォルダーにダミー要求メッセージをドロップして、ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="87a9c-103">In this topic you test the solution by dropping a dummy request message in the folder you associated with the FILE receive port.</span></span> <span data-ttu-id="87a9c-104">呼び出す場合にのみダミー要求メッセージをドロップするで説明したよう、 **Wcf-webhttp**ポートを送信します。</span><span class="sxs-lookup"><span data-stu-id="87a9c-104">As explained in, you drop a dummy request message only to invoke the **WCF-WebHttp** send port.</span></span> <span data-ttu-id="87a9c-105">次のようなダミー要求メッセージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="87a9c-105">You can create a dummy request message like the following:</span></span>  
  
```  
<Root>  
  <Input>Azure Market Place REST API integration</Input>  
<Root>  
```  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="87a9c-106">ソリューションをテストするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="87a9c-106">To test the solution</span></span>  
  
1.  <span data-ttu-id="87a9c-107">BizTalk Server 管理コンソールから起動**BizTalk アプリケーション 1**です。</span><span class="sxs-lookup"><span data-stu-id="87a9c-107">From the BizTalk Server Administration Console, start **BizTalk Application 1**.</span></span> <span data-ttu-id="87a9c-108">これによって、前の手順で作成したすべてのポートが起動されます。</span><span class="sxs-lookup"><span data-stu-id="87a9c-108">This starts all the ports that we created in previous steps.</span></span>  
  
2.  <span data-ttu-id="87a9c-109">Windows エクスプローラーを開き、FILE 受信場所と関連付けた場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="87a9c-109">Open Windows Explorer, and navigate to the location that you associated with the FILE receive location.</span></span> <span data-ttu-id="87a9c-110">この場所で、ダミー要求メッセージをコピーします。</span><span class="sxs-lookup"><span data-stu-id="87a9c-110">At this location, copy the dummy request message.</span></span>  
  
3.  <span data-ttu-id="87a9c-111">ファイルがない場合は、REST インターフェイスからの応答メッセージを使用する FILE 送信ポートと関連付けた場所を調べます。</span><span class="sxs-lookup"><span data-stu-id="87a9c-111">When the file disappears, check the location you associated with FILE send port that consumes the response message from the REST interface.</span></span> <span data-ttu-id="87a9c-112">XML 応答メッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="87a9c-112">It should contain an XML response message.</span></span> <span data-ttu-id="87a9c-113">XML メッセージを開き、送れた米国航空会社のフライトの詳細を見ます。</span><span class="sxs-lookup"><span data-stu-id="87a9c-113">Open the XML message to see the details of flights from US air carries that are delayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a9c-114">参照</span><span class="sxs-lookup"><span data-stu-id="87a9c-114">See Also</span></span>  
 [<span data-ttu-id="87a9c-115">チュートリアル 5: BizTalk Server を使用して REST インターフェイスの呼び出し</span><span class="sxs-lookup"><span data-stu-id="87a9c-115">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)