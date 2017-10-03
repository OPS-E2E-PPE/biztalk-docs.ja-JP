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
# <a name="step-3a-create-an-orchestration-for-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a>手順 3: FileAct ストア アンド フォワード (プル) シナリオの動的送信ポート用のオーケストレーションを作成します。
このセクションの手順を開始する前に」の手順を完了する必要があります、[手順 2 C: FileAct ストア アンド フォワード (プル) シナリオの FILEACT 送信ポートを追加](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md)セクションです。  
  
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
  
    MessageFormat="FileactMessage";  
    IsPull=true;  
  
    ```  
  
3.  動的送信の PullSnFRequest の種類のメッセージと URL を構築します。 割り当て図形のメッセージの構築の例を参照してください。  
  
    ```  
    PullMessage = new System.Xml.XmlDocument();  
    PullMessage.LoadXml(@"<Sw-PullSnFRequest/>");  
    PullRequest = PullMessage;  
  
    DynamicPull(Microsoft.XLANGs.BaseTypes.Address) = "FILEACT://localhost/" + QueueName + "/" + SessionMode + "/" + ForceAcquire + "/" + OrderBy + "/" + RecoveryMode + "/" + MessageFormat;  
  
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
    PullResponseNode=PullResponseDoc.SelectSingleNode("/Sw-PullSnFResponse/SwGbl-Status/SwGbl-StatusAttributes/SwGbl-Code");  
    if(PullResponseNode !=null && PullResponseNode.InnerText=="Sw.SnF.QueueEmpty")  
    {  
        IsPull=false;  
    }  
  
    ```  
  
12. IsPull 設定すると、false、キューが空です。  
  
## <a name="see-also"></a>参照  
 [手順 3 b: FileAct ストア アンド フォワード (プル) シナリオ用の動的送信ポートにオーケストレーションをバインド](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-for-fileact-store-and-forward.md)