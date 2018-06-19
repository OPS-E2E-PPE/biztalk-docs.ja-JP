---
title: BizTalk メッセージ キューの大きいメッセージ用拡張機能 |Microsoft ドキュメント
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
ms.openlocfilehash: 399c8e02d59a931dbf30bfa31ca28980dfa312be
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006403"
---
# <a name="biztalk-message-queuing-large-message-extension"></a>BizTalk メッセージ キューのサイズの大きいメッセージ用拡張機能
4megabytes よりも大きい本体を持つメッセージを処理できないネイティブのメッセージ キュー (MB)。 ただし、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、4 MB を超えるメッセージを処理できるようにする、ネイティブのメッセージ キュー用のアドオンが用意されています。 このアドオンは、Mqrtlarge.dll ファイルとして提供され、公開、 **MQSendLargeMessage**と**MQReceiveLargeMessage**アプリケーション プログラミング インターフェイス (Api)、および COM 類似モデル。 これらの関数は、標準メッセージ キュー Api として実装されて**MQSendMessage**と**MQReceiveMessage**それぞれします。  
  
 サイズの大きいメッセージの交換に参加するには、メッセージ キュー コンピューターに Mqrtlarge.dll ファイルをインストールし、メッセージ キュー アプリケーションでアドオン API を使用する必要があります。 それ以外の場合、完全なメッセージをフラグメント化されます。  
  
 **SDK 内の場所**  
  
 \<*インストール パス*\>\SDK\ Mqrtlarge.dll  
  
 **ファイルのインベントリ**  
  
 次の表は、このユーティリティで使用するファイルとその目的を示しています。  
  
|ファイル|Description|  
|---------------|-----------------|  
|Mqrtlarge.dll|公開する Win32 ダイナミック リンク ライブラリ**MQSendLargeMessage**と**MQReceiveLargeMessage**です。<br /><br /> ヘッダー ファイルに配置されます、 *\<インストール パス\>* \SDK\Include ディレクトリ。 **注:** インストールする必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]64 ビット版の Mqrtlarge.dll にアクセスするために Windows の 64 ビット バージョンにします。|  
  
 **このユーティリティの使用**  
  
 Mqrtlarge.dll ファイルを実行するには、次の操作を行います。  
  
### <a name="to-use-the-mqrtlargedll-file"></a>Mqrtlarge.dll ファイルを使用するには  
  
1.  > [!NOTE]
    >  BizTalk Server なしの MSMQ ソリューションでは、引き続き、MQRTLarge.dll から正常に機能します。 ただし、これは Microsoft がサポートするための推奨構成ではありません、BizTalk Server 環境の外部で使用されている場合に、予期しない結果が発生する可能性があります。  
  
     ファイル Mqrtlarge.dll を BizTalk Server がインストールされていないコンピューターに追加します。 メッセージ キューで Mqrtlarge.dll を使用して、BizTalk Server との間でメッセージを送受信します。  
  
2.  Mqrtlarge.dll ファイルの API にアクセスするには、他のコンピューターへのメッセージの送信や他のコンピューターから BizTalk メッセージ キューのエンドポイントへのメッセージの受信を行うアプリケーションに、Mqrtlarge.dll ファイルへの参照を追加します。  
  
 **「解説」**  
  
 サイズの大きいメッセージは、標準メッセージ キュー (MSMQ とも呼ばれます) のキューに送信されます。 サイズの大きいメッセージ API はこれらのキューでのみ使用することをお勧めしますが、強制されるわけではありません。  
  
 使用することもできます**MQSendMessage**サイズの大きいメッセージを送信したキューにメッセージを送信します。 同様に、使用することができます**MQReceiveMessage**のパフォーマンスに影響を与える可能性があるために推奨されませんが、このようなキューからメッセージを受信する、 **MQReceiveLargeMessage** API です。  
  
 回復用に、お勧めを使用すること**DEAD_LETTER**履歴。  
  
 **断片化**  
  
 一般に、それぞれ 4 MB より小さい多数のメッセージにサイズの大きいメッセージをフラグメント化されます。 フラグメント化されるのは本文だけであることを理解することが重要です。 残りのプロパティは各フラグメントと共に送信されます。  
  
 フラグメントの数は、メッセージのサイズとフラグメントのサイズによって定義されます。 フラグメント サイズは、ファイル Mqrtlarge.dll または BizTalk メッセージ キューの適切な部分によって自動的に決まることもあります。 アプリケーションでフラグメント サイズを明示的に指定することもできます。  
  
 サイズの大きいメッセージ用拡張機能では、一定サイズの追加内部データを追加することでメッセージを拡張する必要があることに注意してください。  
  
 **PROPID_M_EXTENSION**  
  
 使用することができます、 **PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN**プロパティをメッセージに署名します。 署名は 40 バイト (B) で構成します。 次の表に、署名のフラグメントを示します。  
  
|Description|サイズ|  
|-----------------|----------|  
|グローバル一意識別子 (GUID) を使用してこのメッセージが送信することを示す**MQSendLargeMessage**|16 B|  
|メッセージの guid を指定しますメッセージのすべての部分に共通する一意の各サイズの大きいメッセージ ID。|16 B|  
|サイズの大きいメッセージの合計サイズ|4 B|  
|部分番号|2 B|  
|メッセージ部分の数|2 B|  
  
 使用するか**PROPID_M_EXTENSION**追加なくなります。 Microsoft Host Integration Server の MSMQ-MQSeries ブリッジでは、このプロパティを使用して、MQSeries とメッセージ キューのメッセージの間では直接マップされないプロパティを含む構造体を渡します。 メッセージを MQSeries に、または MQSeries から送信するアプリケーションは、この構造体を明示的または暗黙的に使用します。 メッセージが受信側アプリケーションでキューから受信されたとき、メッセージ キューでは受信確認を生成することができます。 受信確認は、送信アプリケーションによって指定されたキューに送信されます。 サイズの大きいメッセージの場合は、サイズの大きいメッセージの最後の部分についてのみこの受信確認を送信します。  
  
## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)