---
title: 手順 10:Interrogative シナリオの確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interrogative tutorial, verifying solution
ms.assetid: 1f28800b-4a1d-4f29-8123-5cdea4b4a365
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7d716ad28e7833885291c43d5870e6430624065
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288963"
---
# <a name="step-10-verify-the-interrogative-scenario"></a>手順 10:Interrogative シナリオを確認します。
この手順では、このチュートリアルでは、エンド ツー エンド シナリオを確認します。  
  
### <a name="to-send-the-query-message"></a>クエリ メッセージを送信するには  
  
1.  コマンド プロンプトを開きます。  
  
2.  コマンド プロンプトに移動 **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータ**します。  
  
3.  コマンド プロンプトで「 **MllpReceive/P 24000**、およびキーを押します **」と入力**します。 これをリッスンするポート 24000 MLLP リスナー アプリケーションを実行し、他の画面に受信メッセージを表示します。 このアプリケーションでは、病院の情報システムをシミュレートします。  
  
4.  追加のコマンド プロンプトを開きます。  
  
5.  2 番目のコマンド プロンプト ウィンドウに移動 **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータ**.  
  
6.  2 番目のコマンド プロンプトで次のように入力します**MllpSend/SB 11/EB 28/CR 13/TWOWAY/P 22000/F"\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>。HL7\SDK\Interrogative Tutorial\QRY^Q01.txt のアクセラレータ**、キーを押しますと **」と入力します。**  
  
    > [!NOTE]
    >  このコマンドは、MLLP ポート 22000 と (確認) の応答を待機するには、このチュートリアルの先頭で作成したクエリ メッセージを送信します。 ADT では、受信ポートがこのメッセージを取得し、それを処理します。  
  
7.  次の結果があることを確認します。  
  
    -   MLLP リスナー アプリケーションには、次の値を持つメッセージを表示する必要があります。  
  
        ```  
        MSH|^~\&|ADT||HIS||19990303||QRY^Q01|MSG00001|P|2.4  
        QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
        ```  
  
    -   MllpSend ユーティリティがさらに、受信確認ファイルを作成、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\ のアクセラレータQRY^Q01.txt.RESPONSE をという名前の interrogative チュートリアル フォルダー。 このファイルには、受信確認として、次の情報が含まれています。  
  
        ```  
        MSH|^~\&|HIS||ADT||20040331154031.2222-0800||ACK^Q01^ACK|10000GSM|P|2.4  
        MSA|CA|MSG00001  
        ****END ACK****  
        ```  
  
### <a name="to-send-the-response-message"></a>応答メッセージを送信するには  
  
1. MllpReceive アプリケーションを実行しているコマンド プロンプトでキーを押して**Ctrl + C**前の操作をキャンセルします。  
  
2. コマンド プロンプトで「 **MllpReceive/P 25000**、押します **」と入力**します。  
  
   > [!NOTE]
   >  手順 2 をリッスンするポート 25000 MLLP リスナー アプリケーションを実行し、他の画面に受信メッセージを表示します。 このアプリケーションでは、ADT system をシミュレートします。  
  
3. 2 番目のコマンド プロンプトで次のように入力します**MllpSend/SB 11/EB 28/CR 13/P 23000/F"\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>のアクセラレータ。HL7\SDK\Interrogative Tutorial\DSR.txt"**、キーを押します**Enter**します。  
  
   > [!NOTE]
   >  手順 3 では、MLLP ポート 23000 には、このチュートリアルの先頭で作成した応答メッセージを送信します。 HIS では、受信ポートがこのメッセージを取得し、それを処理します。  
  
4. 次の結果があることを確認します。  
  
   -   MLLP リスナー アプリケーションには、次の値を持つメッセージを表示する必要があります。  
  
       ```  
       MSH|^~\&|HIS||ADT||19990505||DSR^Q01|ZXT23469|P|2.4  
       MSA|AA|MSG00003  
       QRD|200307231012|D|I|4387|||20^LI|12233|RES|ALL  
       DSP|||RESULTS FOR PATIENT#12233 SMITH, JOHN H. 07/23/03  
       DSP|||SPECIMEN#H85 COLLECTED 07/22/03 /07/0/0  
       DSP|||ELECTROLYTES  
       DSP||| SODIUM 136 [135-148] MEQ/L STAT  
       DSP||| POTASSIUM 4.2 [3.5-5.0] MEQ/L STAT  
       DSP||| CHLORIDE 91 [95-111] MEQ/L STAT  
       DSP||| CO2 25 [20-30] MEQ/L STAT  
       DSP|||CO2 25 [20-30] MEQ/L STAT|LB  
       ```  
  
   > [!NOTE]
   >  上記のメッセージが正しく表示されない場合は、状態と動作状況の追跡 (HAT) ツールを使用して、エラーをトラブルシューティングします。  
  
   おめでとうございます! BTAHL7 Interrogative チュートリアルが正常に完了しました。  
  
## <a name="see-also"></a>参照  
 [バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [エンド ツー エンドのチュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)   
 [メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)