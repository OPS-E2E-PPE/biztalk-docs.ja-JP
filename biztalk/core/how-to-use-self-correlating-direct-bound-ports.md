---
title: 自己関連付けを行う直接バインド ポートを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feb651fa-3e35-4598-b229-335448f6919c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fb70074983ed41bb3d5397d08156b6db1201080
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383324"
---
# <a name="how-to-use-self-correlating-direct-bound-ports"></a><span data-ttu-id="1312b-102">自己関連付けを行う Direct を使用する方法のポートのバインド</span><span class="sxs-lookup"><span data-stu-id="1312b-102">How to Use Self-Correlating Direct Bound Ports</span></span>
<span data-ttu-id="1312b-103">自己関連付けを行う直接バインド ポートは、自己参照です。</span><span class="sxs-lookup"><span data-stu-id="1312b-103">Self-correlating direct bound ports are self referential.</span></span> <span data-ttu-id="1312b-104">これは、自己関連付けを行う直接バインド ポートがオーケストレーションがその外側のオーケストレーションへのメッセージの送信に使用できる情報を提供することを意味します。</span><span class="sxs-lookup"><span data-stu-id="1312b-104">This means that a self-correlating direct bound port supplies the information that an orchestration can use to send messages back to its enclosing orchestration.</span></span> <span data-ttu-id="1312b-105">自己関連付けを行う直接バインドを使用する場合、オーケストレーション エンジンは、オーケストレーション インスタンスに特定のメッセージの関連付けトークンを生成します。</span><span class="sxs-lookup"><span data-stu-id="1312b-105">When using the self-correlating direct binding, the orchestration engine generates a correlation token on a message that is particular to the orchestration instance.</span></span> <span data-ttu-id="1312b-106">これは、関連付けセットを使用せずに特定のオーケストレーション インスタンスにメッセージを取得する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1312b-106">This provides the capability of getting messages back to a particular orchestration instance without using a correlation set.</span></span>  
  
 <span data-ttu-id="1312b-107">たとえば、指定することで自己関連付けを行う直接バインド ポートをオーケストレーション A で受信を作成できます**直接**の**ポートのバインド**を選択して**自己関連付け**ポート構成ウィザードでします。</span><span class="sxs-lookup"><span data-stu-id="1312b-107">For example, you can create a receiving self-correlating direct bound port in Orchestration A by specifying **Direct** for **Port binding** and selecting **Self Correlating** in the Port Configuration Wizard.</span></span> <span data-ttu-id="1312b-108">次に、オーケストレーション B でを宣言するポートと同じポートの種類の送信ポートのオーケストレーション パラメーターとしてオーケストレーション A. で定義されています。これを行うには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1312b-108">Then, in Orchestration B, you declare a port as a Send Port Orchestration Parameter of the same port type as defined in Orchestration A. To do so, do the following:</span></span>  
  
1. <span data-ttu-id="1312b-109">オーケストレーションの種類 ウィンドウで、右クリック**オーケストレーション パラメーター**、 をクリックし、**新しいポート パラメーター**します。</span><span class="sxs-lookup"><span data-stu-id="1312b-109">In the Orchestration View window, right-click **Orchestration Parameters**, and then click **New Port Parameter**.</span></span>  
  
2. <span data-ttu-id="1312b-110">[プロパティ] ウィンドウでの**通信方向**を選択します**送信**、および**ポートの種類**、オーケストレーション A. で定義されている同じポートの種類を選択します</span><span class="sxs-lookup"><span data-stu-id="1312b-110">In the Properties window, for **Communication Direction**, select **Send**, and for **Port Type**, select the same port type as defined in Orchestration A.</span></span>  
  
   <span data-ttu-id="1312b-111">この宣言は、オーケストレーション デザイナのポート画面に論理送信ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1312b-111">This declaration creates a logical send port on the Port Surface in Orchestration Designer.</span></span> <span data-ttu-id="1312b-112">オーケストレーション A は、オーケストレーション B を使用してを呼び出す、**オーケストレーションの開始**図形し、その他のオーケストレーション パラメーターと共に、パラメーターとしてオーケストレーション B に新しいポートを渡します、ビジネス ロジックを実行します。して渡された新しいポートでメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="1312b-112">Orchestration A calls Orchestration B using the **Start Orchestration** shape and passes the new port as a parameter, along with the other orchestration parameters, to Orchestration B. Orchestration B then performs its business logic and sends a message on the new port that was passed to it.</span></span> <span data-ttu-id="1312b-113">メッセージは、受信側自己関連付けを行う直接バインド ポートにオーケストレーション B. を開始したオーケストレーションのインスタンスの送信します。</span><span class="sxs-lookup"><span data-stu-id="1312b-113">The message is sent to the receiving self-correlating direct bound port of the instance of Orchestration A that started Orchestration B.</span></span>  
  
   <span data-ttu-id="1312b-114">上記の一連のイベントで行うこともできますが、**オーケストレーションの呼び出し**図形、そのときにのみ意味を使用して、**オーケストレーションの開始**図形。</span><span class="sxs-lookup"><span data-stu-id="1312b-114">Although the preceding sequence of events can also be done with a **Call Orchestration** shape, it only makes sense when using a **Start Orchestration** shape.</span></span> <span data-ttu-id="1312b-115">これを使用する場合、**オーケストレーションの呼び出し**図形をポートは、参照によって渡されます。</span><span class="sxs-lookup"><span data-stu-id="1312b-115">This is because when using a **Call Orchestration** shape, ports are passed by reference.</span></span> <span data-ttu-id="1312b-116">ポートの極性は、両方のオーケストレーションで同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1312b-116">The polarity of the port must be same in both of the orchestrations.</span></span> <span data-ttu-id="1312b-117">そのため、1 つのオーケストレーションから渡すポートの通信方向は、呼び出し先オーケストレーションのポート参照の方向と同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1312b-117">Therefore, the communication direction of the port you pass in from one orchestration must be the same as the direction of the port reference in the called orchestration.</span></span> <span data-ttu-id="1312b-118">ただしを使用する場合、**オーケストレーションの開始**図形がオーケストレーションの非同期のインスタンス化が生成され、持つことはできません**アウト**または**Ref**パラメーター。そのため、自己関連付けを行う直接バインド ポートは、オーケストレーションに応答して、オーケストレーション インスタンスがインスタンス化するための手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="1312b-118">However, when using the **Start Orchestration** shape, an asynchronous instantiation of an orchestration is generated and it cannot have **Out** or **Ref** parameters; therefore, the self-correlating direct bound port provides a way for an orchestration to respond back to the orchestration instance that instantiated it.</span></span>  
  
   <span data-ttu-id="1312b-119">自己関連付け直接バインド ポートを行うを使用する方法の例を参照してください「を実装するスキャッター/ギャザー パターン」SDK サンプル[ http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)します。</span><span class="sxs-lookup"><span data-stu-id="1312b-119">For an example of how to use self-correlating direct bound ports, see the SDK sample "Implementing Scatter and Gather Pattern" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1312b-120">参照</span><span class="sxs-lookup"><span data-stu-id="1312b-120">See Also</span></span>  
 <span data-ttu-id="1312b-121">[メッセージ ボックスの直接バインド ポートを使用する方法](../core/how-to-use-messagebox-direct-bound-ports.md) </span><span class="sxs-lookup"><span data-stu-id="1312b-121">[How to Use MessageBox Direct Bound Ports](../core/how-to-use-messagebox-direct-bound-ports.md) </span></span>  
 [<span data-ttu-id="1312b-122">パートナー オーケストレーション直接バインド ポートの使用方法</span><span class="sxs-lookup"><span data-stu-id="1312b-122">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)