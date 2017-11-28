---
title: "手順 3: InterAct ストアと転送 (するプル) シナリオの動的送信ポートのオーケストレーションを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d5bbfed-f2cb-4caa-91e2-58f0bdb3b3c5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 486133586a3db8669a58aae59c3ec67a4f561999
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-create-an-orchestration-for-dynamic-send-port-for-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="2fe21-102">手順 3: InterAct ストアと転送 (するプル) シナリオの動的送信ポートのオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-102">Step 3A: Create an orchestration for dynamic send port for InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="2fe21-103">このセクションの手順を開始する前に」の手順を完了する必要があります、[手順 2 C: InterAct ストア アンド フォワード (プル) シナリオの対話の送信ポート追加](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)セクションです。</span><span class="sxs-lookup"><span data-stu-id="2fe21-103">Before you begin the steps in this section, you must complete the steps in the [Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md) section.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="2fe21-104">オーケストレーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="2fe21-104">To Create an Orchestration</span></span>  
  
1.  <span data-ttu-id="2fe21-105">すべてのメッセージの種類のソフトウェア ExchangeSnFRequest メッセージをサブスクライブする受信図形を作成します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-105">Create the Receive shape that subscribes to all of the messages of message type Sw-ExchangeSnFRequest.</span></span>  
  
2.  <span data-ttu-id="2fe21-106">ExchangeRequestSnF メッセージからすべての必要な値を取得する式図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-106">Add an Expression shape to get all of the required values from the ExchangeRequestSnF message.</span></span> <span data-ttu-id="2fe21-107">次の式図形のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fe21-107">Refer to the following Expression Shape sample:</span></span>  
  
    ```  
    ExchangeSnFRequestDoc=ExchangeSnFRequest;  
    AcquireQueuePath="/Sw-ExchangeSnFRequest/Sw-SnFRequest/Sw-SnFOpRequest/Sw-AcquireSnFRequest/";  
  
    QueueNameNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath + "SwInt-Queue");  
    SessionModeNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-SessionMode");  
    ForceAcquireNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-ForceAcquire");  
    OrderByNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-OrderBy");  
    RecoveryModeNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-RecoveryMode");  
  
    QueueName=QueueNameNode.InnerText;  
    SessionMode=SessionModeNode.InnerText;  
    ForceAcquire=ForceAcquireNode.InnerText;  
    OrderBy=OrderByNode.InnerText;  
    RecoveryMode=RecoveryModeNode.InnerText;  
  
    MessageFormat="InteractMessage";  
    IsPull=true;  
    ```  
  
3.  <span data-ttu-id="2fe21-108">動的送信の PullSnFRequest の種類のメッセージと URL を構築します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-108">Construct a message of type PullSnFRequest and the URL for Dynamic Send.</span></span> <span data-ttu-id="2fe21-109">割り当て図形のメッセージの構築の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fe21-109">Refer to the Assignment Shape of Construct Message sample:</span></span>  
  
    ```  
    PullMessage = new System.Xml.XmlDocument();  
    PullMessage.LoadXml(@"<Sw-PullSnFRequest/>");  
    PullRequest = PullMessage;  
  
    DynamicPull(Microsoft.XLANGs.BaseTypes.Address) = "INTERACT://<machine  
     name>/" + QueueName + "/" + SessionMode + "/" + ForceAcquire + "/" +   
    OrderBy + "/" + RecoveryMode + "/" + MessageFormat;  
    ```  
  
4.  <span data-ttu-id="2fe21-110">このサンプルでは、PullMessage は、ソフトウェア PullSnFRequest の種類のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="2fe21-110">In this sample, PullMessage is a message of type Sw-PullSnFRequest.</span></span>  
  
5.  <span data-ttu-id="2fe21-111">PullMessage (プル要求) を送信する送信図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-111">Add a Send shape to send the PullMessage (pull request).</span></span>  
  
6.  <span data-ttu-id="2fe21-112">プル メッセージを送信して、動的バインドとプルの応答を受信するために、要求-応答ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-112">Add a request-response port for sending the pull message and for receiving the pull response with the dynamic binding.</span></span>  
  
7.  <span data-ttu-id="2fe21-113">前の手順で作成したポートと送信図形を接続します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-113">Connect the Send shape with the port created in the previous step.</span></span>  
  
8.  <span data-ttu-id="2fe21-114">PullResponse (PullSnFResponse の種類のメッセージ) を受信し、以前に作成したポートと受信図形を接続するための受信図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-114">Add a Receive shape to receive the PullResponse (message of type PullSnFResponse) and then connect the Receive shape with the port previously created.</span></span>  
  
9. <span data-ttu-id="2fe21-115">送信図形を使用してそれぞれのフォルダーへの応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-115">Send the response to the respective folder using a Send shape.</span></span>  
  
10. <span data-ttu-id="2fe21-116">すべてのメッセージをプルする場合に、ループ内でこれらのアクティビティ (プル要求の送信と応答の受信) のすべてを追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-116">Add all of these activities (sending a pull request and receiving the response) in a loop if you want to pull all of the messages.</span></span>  
  
11. <span data-ttu-id="2fe21-117">キューの制限時間を空になるまでのプルを保持する CheckQueueEmpty の式図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="2fe21-117">Add an Expression shape CheckQueueEmpty to keep pulling until the time queue is empty.</span></span> <span data-ttu-id="2fe21-118">次の式図形のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fe21-118">Refer the following Expression Shape sample:</span></span>  
  
    ```  
    PullResponseDoc=PullResponse;  
    PullResponseNode=PullResponseDoc.SelectSingleNode("/SwPullSnFResponse/  
    SwGbl-Status/SwGbl-StatusAttributes/SwGbl-Code");  
    if(PullResponseNode !=null && PullResponseNode.InnerText=="Sw.SnF.QueueEmpty")  
    {  
        IsPull=false;  
    }  
    ```  
  
12. <span data-ttu-id="2fe21-119">IsPull 設定すると、false、キューが空です。</span><span class="sxs-lookup"><span data-stu-id="2fe21-119">This will set the IsPull = false, once the queue is empty.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe21-120">参照</span><span class="sxs-lookup"><span data-stu-id="2fe21-120">See Also</span></span>  
 [<span data-ttu-id="2fe21-121">手順 3 b: InterAct ストアと転送 (するプル) シナリオ用の動的送信ポートにオーケストレーションをバインド</span><span class="sxs-lookup"><span data-stu-id="2fe21-121">Step 3B: Bind the orchestration with dynamic send port for InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-port-for-interact-scenario.md)