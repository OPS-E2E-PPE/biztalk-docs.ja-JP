---
title: MllpSend ツール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MllpSend tool
- MLLP-encoded messages, receive adapters
- MLLP-encoded messages, MllpSend tool
ms.assetid: b1723d52-4909-4543-8215-4f73802b6c4f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed9b666b019fe7dc415f28c0dd01522b728b149c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25960728"
---
# <a name="mllpsend-tool"></a>MllpSend ツール
MllpSend ツールを使用すると、データを MLLP の受信場所を送信します。  
  
 使用してこのツールをインストールする、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]カスタム インストール手順です。 BTAHL7 をインストールする標準的なインストールを実行した場合必要があります、カスタム インストールを実行し、このチュートリアルでは正常に動作する順序でテスト ツールをインストールします。 カスタム セットアップ 画面で、次のように選択します**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**。フォルダーです。 詳細については、次を参照してください。[カスタム インストールを実行する](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)です。  
  
 BTAHL7 セットアップでこのツールをインストールする*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータです。  
  
 このツールを使用する、[エンド ツー エンド チュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)、 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)、[バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)、および[メッセージ強化チュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md). インストールした場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]して、既定のインストールが、チュートリアルの結果をテストすることはできません MLLP Testtools (含む MllpSend と MllpReceive) がインストールされていないとします。  
  
## <a name="tool-usage"></a>ツールの使用方法  
 このコマンド ライン ツールの起動に使用する構文を次に示します。  
  
```  
mllpsend.exe [/?] [/I <IP>] [/P <PORT>] [/TWOWAY] [/REPEAT <n>] [/F <FILENAME> | "TEXT"] /SB nn /EB nn /CR nn  
```  
  
 次の表では、MllpSend ツールを使用して、構文の各部について説明します。  
  
|構文|Description|  
|------------|-----------------|  
|**/?**|コマンド プロンプト ウィンドウでヘルプを表示します。|  
|**/I \<IP\>**|送信するアドレスを表します。 既定値は localhost です。|  
|**/P\<ポート\>**|送信するポート番号を表します。 既定値は**11000**です。|  
|**/F**|ファイル名、ファイルの内容を送信します。|  
|**/繰り返し\<n\>**|同じメッセージを送信*n*回です。 ラッパーの文字は、各メッセージに適用されます。|  
|**/TWOWAY**|送信者、受信者からの応答を待機します。 SB と EB を指定する必要があります。 CR はオプションです。 ファイル モードでは、応答は、ファイルに格納されます。応答です。|  
|**/SB**|ブロックの区切り記号の開始バイトの ASCII 値を設定します。 既定値は none です。|  
|**/EB**|終了ブロックの区切り記号のバイトの ASCII 値を設定します。 既定値は none です。|  
|**/CR**|復帰を返す区切り文字バイトの ASCII 値を設定します。 既定値は none です。|  
  
## <a name="examples-of-tool-use"></a>ツールの使用方法の例  
 次の例では、MllpSend ツールを使用する方法を示します。  
  
 **例 1** 次のコマンドを使用すると、"myserver"をサーバー上のポート 13000 でリッスンしている一方向のアダプターにメッセージを送信します。 ラッパーの文字の ASCII 値は SB 11、EB 28 および CR 13 です。  
  
```  
mllpsend.exe /I myserver /P 13000 /SB 11 /EB 28 /CR 13 "A short message"  
```  
  
 **例 2 です。** 11000"localhost"をサーバー上のポートでリッスンしている、双方向アダプターに 100 回のメッセージを送信するのに、次のコマンドを使用することができます。 ラッパーの文字の ASCII 値は SB 11、EB 28 および CR 13 です。  
  
```  
mllpsend.exe /SB 11 /EB 28 /CR 13 /TWOWAY /REPEAT 100 "A short message"  
```  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)