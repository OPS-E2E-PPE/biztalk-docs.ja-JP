---
title: "手順 9: 断片化した受信バッチのシナリオを確認してください |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ba61866-2e1b-49e2-be57-ef281407d0a5
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7e57d55be3d72ebe98f685733335db81503384a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-9-verify-the-fragmented-inbound-batch-scenario"></a>手順 9: 断片化した受信バッチのシナリオを確認してください。
この手順では、受信バッチの断片化しているシナリオを確認します。  
  
 シナリオを確認するには、次のツールを使用してが含まれます。  
  
-   **MllpSend ツール**、これを使用してコマンドラインから、受信ポートにバッチ メッセージを送信します。  
  
-   **MllpReceive ツール**、これを使用してコマンドラインからの (バッチに含まれる) として送信ポートからの個々 のメッセージの受信を確認してください。 MllpReceive ツールのこのインスタンスは、シミュレートされた基幹業務アプリケーションとして機能します。 メッセージの受信を生成することも、受信確認に戻す、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]統合エンジンです。  
  
-   送信ポートから受信確認の受信を確認するために使用する MllpReceive ツールの 2 番目のインスタンス。  
  
### <a name="to-test-the-fragmented-inbound-batch-scenario"></a>受信バッチの断片化しているシナリオをテストするには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリック**コマンド プロンプト**です。  
  
2.  コマンド プロンプトでに移動  **\<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator の HL7\SDK\MLLP * ユーティリティ * です。  
  
3.  コマンド プロンプトで次のように入力します **mllpreceive/p 41000/sb 11/eb 28/cr 13/hl7ack"\<*ドライブ*>: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\。Samples\Sample アプリケーションに同意 ACK.txt** を押してから**Enter**です。 コマンド プロンプト ウィンドウは、手順 5. を実行して、システムの入力を受信するまで待機状態を入力します。  
  
    > [!NOTE]
    >  手順 3 でのコマンドは、ポート 41000 をリッスンする MLLP リスナー アプリケーションを実行します。 このポートがメッセージを配信する送信ポートに関連付けられている (で作成されるよう[手順 5: 提供のメッセージを送信ポートを作成](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md))。 MllpReceive ツールをメッセージを受信し、受信確認 (ACK) を BTAHL7 (に記載されているサンプル ファイルのサンプル アプリケーションに同意 ACK.txt) に送信する基幹業務アプリケーションとして機能します。 コマンド プロンプト ウィンドウで返されたすべてのメッセージが表示されます。 手順 3 でのコマンドは、MLLP メッセージの既定の EB、SB、および CR の文字を指定します。  
  
4.  手順 1. と 2. を別のコマンド プロンプト ウィンドウを開き、MLLP Utilities ディレクトリに移動します。 コマンド プロンプトで次のように入力します。 **mllpreceive/p 41002**、キーを押します**Enter**です。 コマンド プロンプト ウィンドウは、手順 5. を実行して、システムの出力を受信するまで待機状態を入力します。  
  
    > [!NOTE]
    >  手順 4. で、コマンドは、ポート 41002 をリッスンしている MLLP リスナー アプリケーションを実行します。 このポートに受信確認をバッチ メッセージのソースに配信する送信ポートに関連付けられて (で作成されるよう[手順 6: 配信の受信確認を送信ポートを作成](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md))。 MllpReceive ツールは、元のバッチを送信した基幹業務アプリケーションとして機能します。 コマンド プロンプト ウィンドウで返された受信確認が表示されます。 手順 4. で、コマンドでは、MLLP メッセージの既定の EB、SB、および CR の文字を指定します。  
  
5.  手順 1. と 2. を別のコマンド プロンプト ウィンドウを開き、MLLP Utilities ディレクトリに移動します。 コマンド プロンプトで次のように入力します **mllpsend/twoway/sb 11/eb 28/cr 13/f"\<*ドライブ*>: \Batching Tutorial\Instances\FragmentedInboundBatch.txt"/p 21000 *。*ここで、 \<*ドライブ*> インストール ドライブであり、キーを押します**Enter**です。  
  
    > [!NOTE]
    >  手順 5. でコマンドは、受信ポートに元のバッチ メッセージの送信をシミュレートします。 コンソールに表示する必要があります"送信済みメッセージ: 1"、MllpSend ツールが、1 つのバッチ メッセージを送信することを示すです。 表示されない場合は"送信済みメッセージ: 1"、イベント ビューアーを確認します。 手順 5 で入力したコマンドのテキストを確認し、送信の構成のトラブルシューティングを行う、受信ポート、およびのステータス[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BTAHL7 とします。  
  
### <a name="to-verify-the-results-of-the-fragmented-inbound-batch-tutorial"></a>受信バッチ断片化チュートリアルの結果を確認するには  
  
1.  少し遅れて、41000 のポートでメッセージをリッスン MllpReceive ツールが表示されるバッチから断片化され Tutorial_BatchSource パーティに送信されると、個々 のメッセージの内容を確認します。 2 つのメッセージの内容は次のようにする必要があります。  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT ^ A03|000001|Tutorial_BatchSource|MESA_IS|  
    |ADT ^ A03|000002|Tutorial_BatchSource|MESA_IS|  
  
2.  少し遅れて、41002 のポートで受信確認をリッスンして MllpReceive ツールが表示されるバッチの発生元へ、BTAHL7 統合エンジンから返された 2 つの受信確認の内容を確認します。 2 つの受信確認の内容は、次のようにする必要があります。  
  
    |MSH.9|MSH.3|MSH.5|MSA.2|MSA.1|  
    |-----------|-----------|-----------|-----------|-----------|  
    |ACK ^ A03 ^ ACK|MESA_IS|Tutorial_BatchSource|000001|AA|  
    |ACK ^ A03 ^ ACK|MESA_IS|Tutorial_BatchSource|000002|AA|  
  
## <a name="see-also"></a>参照  
 [パート 2: バッチのシナリオをバッチ処理/](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [パート 3: 作成するバッチのシナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)