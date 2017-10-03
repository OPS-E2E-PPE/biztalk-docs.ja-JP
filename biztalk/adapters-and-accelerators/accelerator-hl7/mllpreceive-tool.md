---
title: "MllpReceive ツール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- MllpReceive tool
- MLLP-encoded messages, MllpReceive tool
ms.assetid: 7069444b-1412-40bf-b567-fa86f76cd007
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c23aac352b47a328cfc8f412bb3beca50a61e1c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mllpreceive-tool"></a>MllpReceive ツール
MLLP 送信ポートからデータを受信するのに MllpReceive ツールを使用することができます。  
  
 使用してこのツールをインストールする、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]カスタム インストール手順です。 BTAHL7 をインストールする標準的なインストールを実行した場合必要があります、カスタム インストールを実行し、このチュートリアルでは正常に動作する順序でテスト ツールをインストールします。 カスタム セットアップ 画面で、次のように選択します**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**。フォルダーです。 詳細については、次を参照してください。[カスタム インストールを実行する](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)です。  
  
 BTAHL7 セットアップでこのツールをインストールする*\<ドライブ >*: \Program Files\Microsoft BizTalk\<バージョン > Accelerator for HL7\SDK\MLLP ユーティリティです。  
  
 このツールを使用する、[エンド ツー エンド チュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)、 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)、[バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)、および[メッセージ強化チュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md). インストールした場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]して、既定のインストール、チュートリアルの結果をテストすることはできません MLLPTest ツール (含む MllpReceive と MllpSend) をインストールしていないとします。  
  
## <a name="tool-usage"></a>ツールの使用方法  
 このコマンド ライン ツールの起動に使用する構文を次に示します。  
  
```  
mllpreceive.exe [/?] [/I <IP>] [/P <PORT>] [/SPLIT] [/D <DIRECTORY>] [/STATICACK "ACKTEXT" | /HL7ACK <FILENAME>] /SB nn /EB nn /CR nn  
```  
  
 次の表では、MllpReceive ツールを使用して、構文の各部について説明します。  
  
|構文|意味|  
|------------|-------------|  
|/?|このヘルプを表示します。|  
|/I \<IP >|リッスンするアドレスを表します。 既定では使用可能なすべての ip アドレスです。|  
|/P\<ポート >|リッスンするポート番号を表します。 既定値は、12000 です。|  
|/D\<ディレクトリ >|内のディレクトリに受信したすべてのメッセージを格納\<ディレクトリ >。 指定しない場合\<ディレクトリ >、既定のディレクトリは %temp% です。|  
|/分割|区切り記号に基づいて個別のメッセージに、受信したデータを分割します。 SB と EB 必要です。 CR はオプションです。|  
|/STATICACK|静的な受信確認は、送信者に返されます。 分割モードが適用されます。|  
|/HL7ACK|HL7 受信確認は、送信者に返されます。 ファイル名は、HL7 ACK を含むファイルの名前を表します 分割モードが適用されます。|  
|/SB|ブロックの区切り記号のバイトの開始の ASCII 値を設定します。 既定値は none です。|  
|/EB|終了ブロックの区切り記号のバイトの ASCII 値を設定します。 既定値は none です。|  
|/CR|復帰を返す区切り文字のバイトの ASCII 値を設定します。 既定値は none です。|  
  
## <a name="example-of-tool-use"></a>ツールの使用方法の例  
 Localhost、ポート 10000 にリッスンするように、次のコマンドを使用して、C:\TEMP 上のファイルを区切るためのメッセージを保存できます。  
  
```  
mllpreceive.exe /P 10000 /SPLIT /SB 11 /EB 28 /CR 13 /D C:\TEMP  
```  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)