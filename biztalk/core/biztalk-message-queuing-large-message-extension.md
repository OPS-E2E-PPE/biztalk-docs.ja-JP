---
title: BizTalk メッセージ キューの大きいメッセージ用拡張機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Message Queuing Large Message Extension
- utilities, BizTalk Message Queuing Large Message Extension
ms.assetid: 5d6892d3-fda8-41a3-8111-d28c11bd71fb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fee132b78756554dace25319d41193f89e00aebd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357977"
---
# <a name="biztalk-message-queuing-large-message-extension"></a>BizTalk メッセージ キューの大きいメッセージ用拡張機能
4megabytes よりも大きい本文と共にメッセージを処理できないネイティブのメッセージ キュー (MB)。 ただし、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 4 MB を超えるメッセージを処理できるようにするネイティブのメッセージ キュー用のアドオンが含まれています。 このアドオンは、Mqrtlarge.dll ファイルとして配信し、公開、 **MQSendLargeMessage**と**MQReceiveLargeMessage**アプリケーション プログラミング インターフェイス (Api)、および COM 類似モデル。 これらの関数は、標準メッセージ キュー Api として実装されます**MQSendMessage**と**MQReceiveMessage**それぞれします。  

 サイズの大きいメッセージの交換に参加するに、メッセージ キュー コンピュータする必要がありますに Mqrtlarge.dll ファイルをインストールし、メッセージ キュー アプリケーションでアドオン Api を使用する必要があります。 それ以外の場合、完全なメッセージをフラグメント化されます。  

 **SDK の場所**  

 \<*インストール パス*\>\SDK\ Mqrtlarge.dll  

 **ファイルのインベントリ**  

 このユーティリティを使用し、その目的について説明します、次の表は、ファイルを示します。  


|    ファイル    |                                                                                                                                                                                              説明                                                                                                                                                                                               |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mqrtlarge.dll | 公開する Win32 ダイナミック リンク ライブラリ**MQSendLargeMessage**と**MQReceiveLargeMessage**します。<br /><br /> ヘッダー ファイルにある、 *\<インストール パス\>* \SDK\Include ディレクトリ。 **注:** インストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を 64 ビット版の Mqrtlarge.dll にアクセスするために Windows の 64 ビット バージョン。 |

 **このユーティリティの使用**  

 Mqrtlarge.dll ファイルを実行するのにには、次の手順を使用します。  

### <a name="to-use-the-mqrtlargedll-file"></a>Mqrtlarge.dll ファイルを使用するには  

1. > [!NOTE]
   >  BizTalk Server なしの MSMQ ソリューションでは、可能性があります、まだ、MQRTLarge.dll から正常に機能します。 ただし、これは Microsoft がサポートしている推奨構成ではありませんし、BizTalk Server 環境の外部で使用されている場合に、予期しない結果が発生する可能性があります。  

    BizTalk Server のインストールが含まれていないコンピューターに Mqrtlarge.dll ファイルを追加します。 メッセージ キューは、BizTalk Server からのメッセージを送受信する Mqrtlarge.dll を使用します。  

2. Mqrtlarge.dll ファイルの Api にアクセスするには、送信または別のコンピュータに BizTalk メッセージ キュー エンドポイントからメッセージを受信するアプリケーションで Mqrtlarge.dll ファイルへの参照を追加します。  

   **解説**  

   サイズの大きいメッセージは、標準メッセージ キュー (MSMQ とも呼ばれます) のキューに送信されます。 これは適用されませんが、これらのキューでサイズの大きいメッセージ Api のみを使用してください。  

   使用することもできます**MQSendMessage**サイズの大きいメッセージを送信したキューにメッセージを送信します。 同様に、使用**MQReceiveMessage**のパフォーマンスに影響を与える可能性があるためにお勧めしませんが、これらのキューからメッセージを受信する、 **MQReceiveLargeMessage** API。  

   回復のために、お勧めを使用すること**DEAD_LETTER**ジャーナリングです。  

   **断片化**  

   一般に、それぞれ、4 MB より小さい多数のメッセージにサイズの大きいメッセージをフラグメント化されます。 本文のみが断片化していることを理解しておく必要があります。 プロパティの残りの部分は、各フラグメントと共に送信されます。  

   フラグメントの数は、メッセージのサイズとフラグメントのサイズによって定義されます。 フラグメント サイズ ファイル Mqrtlarge.dll または BizTalk メッセージ キューの適切な部分によって自動的に決定されます。 アプリケーションは、フラグメント サイズを明示的に指定できます。  

   サイズの大きいメッセージの拡張機能は、一定のサイズの他の内部データを追加して、メッセージを拡張する必要がありますに注意してください。  

   **PROPID_M_EXTENSION**  

   使用することができます、 **PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN**プロパティをメッセージに署名します。 署名には、40 バイト (B) が構成されています。 次の表では、署名のフラグメントを示します。  

|説明|サイズ|  
|-----------------|----------|  
|グローバル一意識別子 (GUID) を使用してこのメッセージが送信されたことを示す**MQSendLargeMessage**|16 B|  
|メッセージの GUID: メッセージのすべての部分に共通するあたりサイズの大きいメッセージの一意の ID|16 B|  
|サイズの大きいメッセージの合計サイズ|4 B|  
|部品番号|2 B|  
|メッセージ部分の数|2 B|  

 使用するか**PROPID_M_EXTENSION**がその他の暗黙的です。 Microsoft ホスト Integration Server の Msmq-mqseries ブリッジでは、このプロパティを使用して、MQSeries とメッセージ キューのメッセージの間で直接マップされていないプロパティを格納する構造体を渡します。 明示的または暗黙的にして、MQSeries からメッセージを送信するアプリケーションでは、この構造体を使用します。 受信側アプリケーション キューからメッセージを受け取ったときに、メッセージ キューは受信確認を生成できます。 受信確認は、送信元アプリケーションによって指定されたキューに送信されます。 サイズの大きいメッセージの場合は、サイズの大きいメッセージの最後の部分に対してのみこの受信確認を送信します。  

## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)