---
title: MllpReceive ツール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- MllpReceive tool
- MLLP-encoded messages, MllpReceive tool
ms.assetid: 7069444b-1412-40bf-b567-fa86f76cd007
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e2684ef0d2ae7ee678e11f7b03541499b5f4c7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290296"
---
# <a name="mllpreceive-tool"></a>MllpReceive ツール
MLLP 送信ポートからデータを受信するのに MllpReceive ツールを使用することができます。  
  
 使用してこのツールをインストールする、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]カスタム インストール手順。 コード型の BTAHL7 をインストールする一般的なインストールを実行した場合、カスタム インストールを実行テスト ツールを正常に動作するには、このチュートリアルの順序でインストールし、する必要があります。 カスタム セットアップ 画面で選択**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダー。 詳細については、次を参照してください。[カスタム インストールを実行する](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)します。  
  
 BTAHL7 セットアップでは、このツールをインストールする*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータです。  
  
 このツールで使用する、[エンド ツー エンド チュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)、 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)、[バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)、および[メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md). インストールした場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]既定のインストールをインストールしていない、MLLPTest ツール (含む MllpReceive および MllpSend)、チュートリアルの結果をテストすることはできません。  
  
## <a name="tool-usage"></a>ツールの使用方法  
 使用してこのコマンド ライン ツールを呼び出す構文を次に示します。  
  
```  
mllpreceive.exe [/?] [/I <IP>] [/P <PORT>] [/SPLIT] [/D <DIRECTORY>] [/STATICACK "ACKTEXT" | /HL7ACK <FILENAME>] /SB nn /EB nn /CR nn  
```  
  
 次の表では、MllpReceive ツールを使用して、構文の各部について説明します。  
  
|構文|説明|  
|------------|-------------|  
|/?|このヘルプを表示します。|  
|/I \<IP\>|リッスンするアドレスを表します。 既定では使用可能なすべての ip アドレスです。|  
|/P\<ポート\>|リッスンするポート番号を表します。 既定値は、12000 です。|  
|/D\<ディレクトリ\>|内のディレクトリにすべての受信メッセージを格納\<ディレクトリ\>します。 指定しない場合\<ディレクトリ\>既定のディレクトリは %temp% です。|  
|/分割|区切り記号に基づいて個別のメッセージには、受信したデータを分割します。 SB と EB 必要です。 CR は省略可能です。|  
|/STATICACK|静的受信確認の送信者に返されます。 分割モードが適用されます。|  
|/HL7ACK|HL7 の受信確認は、送信者に返されます。 ファイル名は、HL7 ACK を含むファイルの名前を表します 分割モードが適用されます。|  
|/SB|開始ブロックの区切り記号のバイトの ASCII 値を設定します。 既定では none です。|  
|/EB|終了ブロックの区切り記号のバイトの ASCII 値を設定します。 既定では none です。|  
|/CR|復帰返す区切り文字のバイトの ASCII 値を設定します。 既定では none です。|  
  
## <a name="example-of-tool-use"></a>ツールの使用方法の例  
 ポート 10000、localhost 上でリッスンするように、次のコマンドを使用し、メッセージを別のファイルを C:\TEMP に保存することができます。  
  
```  
mllpreceive.exe /P 10000 /SPLIT /SB 11 /EB 28 /CR 13 /D C:\TEMP  
```  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)