---
title: 手順 10:エンド ツー エンド シナリオの確認 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- end-to-end tutorial, verifying solution
ms.assetid: 24b74ba6-e303-4ab1-8a93-25a430e4894d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 081f2e7f81c7ea293cac8717434a451d0d2ecd6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289057"
---
# <a name="step-10-verify-the-end-to-end-scenario"></a>手順 10:エンド ツー エンド シナリオを確認します。
この手順では、このチュートリアルでは、エンド ツー エンド シナリオを確認します。  
  
### <a name="to-verify-the-end-to-end-tutorial-scenario"></a>エンド ツー エンドのチュートリアルのシナリオを確認するには  
  
1. をクリックして**開始**、 をポイント**プログラム**、 をポイント**アクセサリ**、順にクリックします**コマンド プロンプト**します。  
  
2. コマンド プロンプト ウィンドウに移動します **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>Accelerator HL7\SDK\MLLP ユーティリティfor**。、キーを押しますと**Enter**します。  
  
   > [!NOTE]
   >  SDK フォルダーの下の MLLP ユーティリティ フォルダーが見つからない場合 MLLP テスト ツールがインストールしない可能性があります。 コントロール パネル を開き、開きます**プログラム追加と削除**します。 選択**Microsoft BizTalk\<バージョン\>Accelerator 用 HL7**、し、**変更**します。 BTAHL7 セットアップ ウィザードで **変更**します。 展開、**アダプター**フォルダーを表示するかどうか、 **MLLP テスト ツール**がインストールされています。 それ以外の場合は、それをインストールします。  
  
3. コマンド プロンプト ウィンドウで次のように入力します。 **mllpreceive/p 14000**、し、キーを押します**Enter**します。 これにより、MLLP リスナー アプリケーション ポート 14000 にリッスンしていると、MLLP メッセージの既定 EB、SB、CR 文字を指定することを実行し、他の画面に受信メッセージを表示します。  
  
4. クリックして、追加のコマンド プロンプトを開始**開始**、 をポイント**プログラム**、 をポイント**アクセサリ**、順にクリックします**コマンド プロンプト**.  
  
5. 2 番目のコマンド プロンプト ウィンドウに移動 **\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータ**、キーを押しますと**Enter**します。  
  
   > [!NOTE]
   >  次の手順では、メッセージを送信します。  
  
6. コマンド プロンプト ウィンドウで次のように入力します**mllpsend/SB 11/EB 28/CR 13/f"\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\ のアクセラレータ。エンド ツー エンド Tutorial\ADT ^ A03.txt"** ここで、 \<*ドライブ*\>インストールのドライブ文字します。 **Enter**キーを押します。  
  
7. 次の結果があることを確認します。  
  
   -   MLLP リスナー アプリケーションには、メッセージを表示する必要があります。 メッセージの最初の行には、次の値が必要です。  
  
       ```  
       MSH|^~\&|BTAHL7^IE^UUID|MCM|HI^System^GUID||199601121005||ADT^A04|000001|P|2.4|||SU|NE  
       ```  
  
   -   メッセージが表示されます\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_sendMsg_RX のアクセラレータです。 このメッセージは、MLLP リスナー アプリケーションに表示されるメッセージと同じである必要があります。 メッセージと同じ値を次のように、メッセージの最初の行を確認します。 Nd MSH5、次のコードを MSH3 の値が一致、Tutorial_RXSystem の指定した値であることに注意してください。  
  
       ```  
       MSH|^~\&|BTAHL7|MCM|Tutorial_RXSystem||199601121005||ADT^A03|000001|P|2.3.1  
       ```  
  
   -   2 つのメッセージが表示される\<*ドライブ*\>: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\End ツー エンド Tutorial\Tutorial_sendAck_ADT のアクセラレータです。 これらのメッセージの 1 つは、アプリケーションの受信確認です。もう 1 つは、コミットの確認です。 アプリケーションの受信確認は、次の内容が必要です。  
  
       ```  
       MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|000001|P|2.3.1|||AL  
       MSA|AA|000001  
       ```  
  
   -   コミットの確認には、次の内容が必要です。  
  
       ```  
       MSH|^~\&|BTAHL7InterfaceEngine||Tutorial_ADTSystem|MCM|<datetime>||ACK^A03^ACK|100000|P|2.3.1  
       MSA|CA|000001  
       ```  
  
   > [!NOTE]
   >  メッセージが正しく表示されない場合、エラーのトラブルシューティングの状態と動作状況の追跡 (HAT) ツールを使用します。  
  
   おめでとうございます! BTAHL7 のエンド ツー エンド チュートリアルを正常に完了しました。  
  
## <a name="see-also"></a>参照  
 [エンド ツー エンドのチュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)