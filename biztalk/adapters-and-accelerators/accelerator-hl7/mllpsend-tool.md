---
title: MllpSend ツール |Microsoft Docs
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
ms.openlocfilehash: f86f814710f48aa0c8795e00bcf5c2f9be8e1a14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290199"
---
# <a name="mllpsend-tool"></a>MllpSend ツール
MllpSend ツールを使用して、データを MLLP 受信場所を送信することができます。  
  
 使用してこのツールをインストールする、[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]カスタム インストール手順。 コード型の BTAHL7 をインストールする一般的なインストールを実行した場合、カスタム インストールを実行テスト ツールを正常に動作するには、このチュートリアルの順序でインストールし、する必要があります。 カスタム セットアップ 画面で選択**MLLP テスト ツール**から、**アダプター**フォルダー、および選択**テスト インスタンス**から、**成果物**フォルダー。 詳細については、次を参照してください。[カスタム インストールを実行する](http://msdn.microsoft.com/library/e55c86e1-af63-49ba-8510-d177e1b96692)します。  
  
 BTAHL7 セットアップでは、このツールをインストールする*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\MLLP ユーティリティのアクセラレータです。  
  
 このツールで使用する、[エンド ツー エンド チュートリアル](../../adapters-and-accelerators/accelerator-hl7/end-to-end-tutorial1.md)、 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)、[バッチ処理のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)、および[メッセージ強化のチュートリアル](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md). インストールした場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]既定のインストールで、チュートリアルの結果をテストすることはできません MLLP Testtools (含む MllpSend および MllpReceive) をインストールしていないとします。  
  
## <a name="tool-usage"></a>ツールの使用方法  
 使用してこのコマンド ライン ツールを呼び出す構文を次に示します。  
  
```  
mllpsend.exe [/?] [/I <IP>] [/P <PORT>] [/TWOWAY] [/REPEAT <n>] [/F <FILENAME> | "TEXT"] /SB nn /EB nn /CR nn  
```  
  
 次の表では、MllpSend ツールを使用して、構文の各部について説明します。  
  
|構文|説明|  
|------------|-----------------|  
|**/?**|コマンド プロンプト ウィンドウでヘルプを表示します。|  
|**/I \<IP\>**|送信するアドレスを表します。 既定値は、localhost です。|  
|**/P\<ポート\>**|送信するポート番号を表します。 既定値は**11000**します。|  
|**/F**|ファイル名のファイルの内容を送信します。|  
|**/REPEAT \<n\>**|同じメッセージを送信*n*時間。 ラッパーの文字は、各メッセージに適用されます。|  
|**/TWOWAY**|送信者、受信者からの応答を待機します。 SB と EB を指定する必要があります。 CR は省略可能です。 ファイル モードでは、応答は、ファイルのファイルに格納されます。応答です。|  
|**/SB**|ブロックの区切り記号の開始バイトの ASCII 値を設定します。 既定では none です。|  
|**/EB**|終了ブロックの区切り記号のバイトの ASCII 値を設定します。 既定では none です。|  
|**/CR**|復帰返す区切り記号のバイトの ASCII 値を設定します。 既定では none です。|  
  
## <a name="examples-of-tool-use"></a>ツールの使用方法の例  
 次の例では、MllpSend ツールを使用する方法を示します。  
  
 **例 1** 次のコマンドを使用して、サーバー"myserver"上のポート 13000 でリッスンしている一方向のアダプターにメッセージを送信することができます。 SB 11、EB 28、CR 13、ラッパーの文字の ASCII 値。  
  
```  
mllpsend.exe /I myserver /P 13000 /SB 11 /EB 28 /CR 13 "A short message"  
```  
  
 **例 2** 次のコマンドを使用して、ポート 11000"localhost"をサーバー上でリッスンして双方向アダプターに 100 回のメッセージを送信することができます。 SB 11、EB 28、CR 13、ラッパーの文字の ASCII 値。  
  
```  
mllpsend.exe /SB 11 /EB 28 /CR 13 /TWOWAY /REPEAT 100 "A short message"  
```  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-hl7/utilities2.md)