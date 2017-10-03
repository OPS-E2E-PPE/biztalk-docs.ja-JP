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
# <a name="step-3a-create-an-orchestration-for-dynamic-send-port-for-interact-store-and-forward-pull-scenario"></a>手順 3: InterAct ストアと転送 (するプル) シナリオの動的送信ポートのオーケストレーションを作成します。
このセクションの手順を開始する前に」の手順を完了する必要があります、[手順 2 C: InterAct ストア アンド フォワード (プル) シナリオの対話の送信ポート追加](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md)セクションです。  
  
### <a name="to-create-an-orchestration"></a>オーケストレーションを作成するには  
  
1.  すべてのメッセージの種類のソフトウェア ExchangeSnFRequest メッセージをサブスクライブする受信図形を作成します。  
  
2.  ExchangeRequestSnF メッセージからすべての必要な値を取得する式図形を追加します。 次の式図形のサンプルを参照してください。  
  
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
  
3.  動的送信の PullSnFRequest の種類のメッセージと URL を構築します。 割り当て図形のメッセージの構築の例を参照してください。  
  
    ```  
    PullMessage = new System.Xml.XmlDocument();  
    PullMessage.LoadXml(@"<Sw-PullSnFRequest/>");  
    PullRequest = PullMessage;  
  
    DynamicPull(Microsoft.XLANGs.BaseTypes.Address) = "INTERACT://<machine  
     name>/" + QueueName + "/" + SessionMode + "/" + ForceAcquire + "/" +   
    OrderBy + "/" + RecoveryMode + "/" + MessageFormat;  
    ```  
  
4.  このサンプルでは、PullMessage は、ソフトウェア PullSnFRequest の種類のメッセージです。  
  
5.  PullMessage (プル要求) を送信する送信図形を追加します。  
  
6.  プル メッセージを送信して、動的バインドとプルの応答を受信するために、要求-応答ポートを追加します。  
  
7.  前の手順で作成したポートと送信図形を接続します。  
  
8.  PullResponse (PullSnFResponse の種類のメッセージ) を受信し、以前に作成したポートと受信図形を接続するための受信図形を追加します。  
  
9. 送信図形を使用してそれぞれのフォルダーへの応答を送信します。  
  
10. すべてのメッセージをプルする場合に、ループ内でこれらのアクティビティ (プル要求の送信と応答の受信) のすべてを追加します。  
  
11. キューの制限時間を空になるまでのプルを保持する CheckQueueEmpty の式図形を追加します。 次の式図形のサンプルを参照してください。  
  
    ```  
    PullResponseDoc=PullResponse;  
    PullResponseNode=PullResponseDoc.SelectSingleNode("/SwPullSnFResponse/  
    SwGbl-Status/SwGbl-StatusAttributes/SwGbl-Code");  
    if(PullResponseNode !=null && PullResponseNode.InnerText=="Sw.SnF.QueueEmpty")  
    {  
        IsPull=false;  
    }  
    ```  
  
12. IsPull 設定すると、false、キューが空です。  
  
## <a name="see-also"></a>参照  
 [手順 3 b: InterAct ストアと転送 (するプル) シナリオ用の動的送信ポートにオーケストレーションをバインド](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-port-for-interact-scenario.md)