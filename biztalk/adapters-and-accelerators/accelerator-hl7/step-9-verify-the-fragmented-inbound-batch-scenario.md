---
title: '手順 9: 断片化した受信バッチ シナリオの確認 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ba61866-2e1b-49e2-be57-ef281407d0a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dce0f283695af423b96c07103a1c2f5837cf4b6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970677"
---
# <a name="step-9-verify-the-fragmented-inbound-batch-scenario"></a>手順 9: 断片化した受信バッチのシナリオを確認します。
この手順では、受信バッチの断片化しているシナリオを確認します。  
  
 シナリオを確認するには、次のツールを使用する必要があります。  
  
- **MllpSend ツール**、コマンドラインから、バッチ メッセージを受信ポートに送信するために使用します。  
  
- **MllpReceive ツール**、コマンドラインから (バッチに含まれる) として送信ポートからの個々 のメッセージの受信を確認するために使用します。 MllpReceive ツールのこのインスタンスは、シミュレートされた基幹業務アプリケーションとして機能します。 受信確認を生成も、メッセージの受信、上に、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]統合エンジン。  
  
- 送信ポートから受信確認の受信を確認するために使用 MllpReceive ツールの 2 番目のインスタンス。  
  
### <a name="to-test-the-fragmented-inbound-batch-scenario"></a>受信バッチの断片化しているシナリオをテストするには  
  
1. をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリックします**コマンド プロンプト**します。  
  
2. コマンド プロンプトに移動します。  **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータ**します。  
  
3. コマンド プロンプトで「 **mllpreceive/p 41000/sb 11/eb 28/cr 13/hl7ack"\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>のアクセラレータHL7\Samples\Sample アプリケーションに同意 ACK.txt**、し、キーを押します**Enter**します。 コマンド プロンプト ウィンドウは 5 の手順を実行して、システムは、入力を受け取るまで待機状態になります。  
  
   > [!NOTE]
   >  手順 3 でのコマンドは、ポート 41000 をリッスンする MLLP リスナー アプリケーションを実行します。 このポートはメッセージを配信する送信ポートに関連付けられて (で作成した[手順 5: メッセージを配信する送信ポートを作成](../../adapters-and-accelerators/accelerator-hl7/step-5-create-a-send-port-to-deliver-messages.md))。 MllpReceive ツールは、メッセージを受信し、受信確認 (ACK) を BTAHL7 (ようにサンプル アプリケーションを受け入れる ACK.txt サンプル ファイルに含まれる) に送信する基幹業務アプリケーションとして機能します。 コマンド プロンプト ウィンドウで返されたすべてのメッセージが表示されます。 手順 3 でのコマンドでは、MLLP メッセージの既定 EB、SB、CR 文字を指定します。  
  
4. 手順 1. と 2. を別のコマンド プロンプト ウィンドウを開き、MLLP ユーティリティのディレクトリに移動します。 コマンド プロンプトで「 **mllpreceive/p 41002**、キーを押しますと **」と入力**します。 コマンド プロンプト ウィンドウは 5 の手順を実行して、システムの出力を受信するまで待機状態になります。  
  
   > [!NOTE]
   >  手順 4. でコマンドには、リッスンするポート 41002 MLLP リスナー アプリケーションが実行されます。 このポートはバッチ メッセージの元に受信確認を配信する送信ポートに関連付けられて (で作成した[手順 6: 受信確認を配信する送信ポートを作成](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-acknowledgments.md))。 MllpReceive ツールは、元のバッチを送信した基幹業務アプリケーションとして機能します。 コマンド プロンプト ウィンドウで返された受信確認が表示されます。 手順 4 でのコマンドでは、MLLP メッセージの既定 EB、SB、CR 文字を指定します。  
  
5. 手順 1. と 2. を別のコマンド プロンプト ウィンドウを開き、MLLP ユーティリティのディレクトリに移動します。 コマンド プロンプトで「 **mllpsend/twoway/sb 11/eb 28/cr 13/f"\<*ドライブ*\>: \Batching Tutorial\Instances\FragmentedInboundBatch.txt"/p 21000**ここで、 \<*ドライブ*\>インストールのドライブ文字、およびキーを押します**Enter**します。  
  
   > [!NOTE]
   >  手順 5 でのコマンドは、受信ポートには、元のバッチ メッセージの送信をシミュレートします。 コンソールに表示する必要があります"送信済みメッセージ: 1"、MllpSend ツールが 1 つのバッチ メッセージを送信することを示します。 表示されない場合は"送信済みメッセージ: 1"、イベント ビューアーを確認します。 手順 5. で入力したコマンドのテキストを確認し、送信の構成のトラブルシューティング、受信ポート、および状態の[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BTAHL7 とします。  
  
### <a name="to-verify-the-results-of-the-fragmented-inbound-batch-tutorial"></a>受信バッチの断片化しているチュートリアルの結果を確認するには  
  
1.  、しばらく 41000 ポートでメッセージをリッスン MllpReceive ツールが表示されるバッチから断片化され Tutorial_BatchSource パーティに送信されると、個々 のメッセージの内容を確認します。 2 つのメッセージの内容は次のようにする必要があります。  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT ^ A03|000001|Tutorial_BatchSource|MESA_IS|  
    |ADT ^ A03|000002|Tutorial_BatchSource|MESA_IS|  
  
2.  少し遅れていることを確認、41002 ポートで受信確認のリッスン MllpReceive ツールは、BTAHL7 の統合エンジンからバッチのソースに返される 2 つの受信確認の内容を表示します。 2 つの受信確認の内容は次のようにする必要があります。  
  
    |MSH.9|MSH.3|MSH.5|MSA.2|MSA.1|  
    |-----------|-----------|-----------|-----------|-----------|  
    |ACK ^ A03 ^ ACK|MESA_IS|Tutorial_BatchSource|000001|AA|  
    |ACK ^ A03 ^ ACK|MESA_IS|Tutorial_BatchSource|000002|AA|  
  
## <a name="see-also"></a>参照  
 [パート 2: 内のバッチ/バッチ アウト シナリオ](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [パート 3: バッチの作成シナリオ](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)