---
title: "手順 3: FileAct ストア アンド フォワード (プル) シナリオの動的送信ポート用のオーケストレーションを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5675d476-ad36-4bbc-8e87-786edc9c805d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c91f9054885de1d19b467646ee7b82b342a76d6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-create-an-orchestration-for-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="9dd68-102">手順 3: FileAct ストア アンド フォワード (プル) シナリオの動的送信ポート用のオーケストレーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-102">Step 3A: Create an orchestration for dynamic send port for FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="9dd68-103">このセクションの手順を開始する前に」の手順を完了する必要があります、[手順 2 C: FileAct ストア アンド フォワード (プル) シナリオの FILEACT 送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)セクションです。</span><span class="sxs-lookup"><span data-stu-id="9dd68-103">Before you begin the steps in this section, you must complete the steps in the [Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md) section.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="9dd68-104">オーケストレーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="9dd68-104">To Create an Orchestration</span></span>  
  
1.  <span data-ttu-id="9dd68-105">すべてのメッセージの種類のソフトウェア ExchangeSnFRequest メッセージをサブスクライブする受信図形を作成します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-105">Create the Receive shape that subscribes to all of the messages of message type Sw-ExchangeSnFRequest.</span></span>  
  
2.  <span data-ttu-id="9dd68-106">ExchangeRequestSnF メッセージからすべての必要な値を取得する式図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-106">Add an Expression shape to get all of the required values from the ExchangeRequestSnF message.</span></span> <span data-ttu-id="9dd68-107">次の式図形のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dd68-107">Refer to the following Expression Shape sample:</span></span>  
  
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
  
    MessageFormat="FileactMessage";  
    IsPull=true;  
  
    ```  
  
3.  <span data-ttu-id="9dd68-108">動的送信の PullSnFRequest の種類のメッセージと URL を構築します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-108">Construct a message of type PullSnFRequest and the URL for Dynamic Send.</span></span> <span data-ttu-id="9dd68-109">割り当て図形のメッセージの構築の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dd68-109">Refer to the Assignment Shape of Construct Message sample:</span></span>  
  
    ```  
    PullMessage = new System.Xml.XmlDocument();  
    PullMessage.LoadXml(@"<Sw-PullSnFRequest/>");  
    PullRequest = PullMessage;  
  
    DynamicPull(Microsoft.XLANGs.BaseTypes.Address) = "FILEACT://localhost/" + QueueName + "/" + SessionMode + "/" + ForceAcquire + "/" + OrderBy + "/" + RecoveryMode + "/" + MessageFormat;  
  
    ```  
  
4.  <span data-ttu-id="9dd68-110">このサンプルでは、PullMessage は、ソフトウェア PullSnFRequest の種類のメッセージです。</span><span class="sxs-lookup"><span data-stu-id="9dd68-110">In this sample, PullMessage is a message of type Sw-PullSnFRequest.</span></span>  
  
5.  <span data-ttu-id="9dd68-111">PullMessage (プル要求) を送信する送信図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-111">Add a Send shape to send the PullMessage (pull request).</span></span>  
  
6.  <span data-ttu-id="9dd68-112">プル メッセージを送信して、動的バインドとプルの応答を受信するために、要求-応答ポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-112">Add a request-response port for sending the pull message and for receiving the pull response with the dynamic binding.</span></span>  
  
7.  <span data-ttu-id="9dd68-113">前の手順で作成したポートと送信図形を接続します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-113">Connect the Send shape with the port created in the previous step.</span></span>  
  
8.  <span data-ttu-id="9dd68-114">PullResponse (PullSnFResponse の種類のメッセージ) を受信し、以前に作成したポートと受信図形を接続するための受信図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-114">Add a Receive shape to receive the PullResponse (message of type PullSnFResponse) and then connect the Receive shape with the port previously created.</span></span>  
  
9. <span data-ttu-id="9dd68-115">送信図形を使用してそれぞれのフォルダーへの応答を送信します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-115">Send the response to the respective folder using a Send shape.</span></span>  
  
10. <span data-ttu-id="9dd68-116">すべてのメッセージをプルする場合に、ループ内でこれらのアクティビティ (プル要求の送信と応答の受信) のすべてを追加します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-116">Add all of these activities (sending a pull request and receiving the response) in a loop if you want to pull all of the messages.</span></span>  
  
11. <span data-ttu-id="9dd68-117">キューの制限時間を空になるまでのプルを保持する CheckQueueEmpty の式図形を追加します。</span><span class="sxs-lookup"><span data-stu-id="9dd68-117">Add an Expression shape CheckQueueEmpty to keep pulling until the time queue is empty.</span></span> <span data-ttu-id="9dd68-118">次の式図形のサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dd68-118">Refer the following Expression Shape sample:</span></span>  
  
    ```  
    PullResponseDoc=PullResponse;  
    PullResponseNode=PullResponseDoc.SelectSingleNode("/Sw-PullSnFResponse/SwGbl-Status/SwGbl-StatusAttributes/SwGbl-Code");  
    if(PullResponseNode !=null && PullResponseNode.InnerText=="Sw.SnF.QueueEmpty")  
    {  
        IsPull=false;  
    }  
  
    ```  
  
12. <span data-ttu-id="9dd68-119">IsPull 設定すると、false、キューが空です。</span><span class="sxs-lookup"><span data-stu-id="9dd68-119">This will set the IsPull = false, once the queue is empty.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd68-120">参照</span><span class="sxs-lookup"><span data-stu-id="9dd68-120">See Also</span></span>  
 [<span data-ttu-id="9dd68-121">手順 3 b: FileAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションをバインド</span><span class="sxs-lookup"><span data-stu-id="9dd68-121">Step 3B: Bind the orchestration with dynamic send port for FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-for-fileact-store-and-forward.md)