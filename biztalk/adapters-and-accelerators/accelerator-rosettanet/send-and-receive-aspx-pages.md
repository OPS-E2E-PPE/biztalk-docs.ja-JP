---
title: 送信および受信 ASPX ページ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, ASPX pages
- ASPX pages, initiator
- HTTP adapters
- connections, HTTP adapters
- connections, single-action
- ASPX pages, responder
- single-action connections
- RNIFSend.aspx
- connections, asynchronous
- ASPX pages, about ASPX pages
- double-action connections
- connections, synchronous
- connections, double-action
- ASPX pages
- HTTP adapters, connections
- asynchronous connections
- RNIFReceive.aspx
- synchronous connections
ms.assetid: 21e52390-35d8-44b1-a5cd-1cd60cfe6e61
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e688686e8bd787e22d7e5a246e0cce62f469649c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982051"
---
# <a name="send-and-receive-aspx-pages"></a>送信および受信 ASPX ページ
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX ページは、直接結ぶインターフェイス[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]とインターネットです。 受信ページ (RNIFReceive.aspx) と送信ページ (RNIFSend.aspx) の 2 つの ASPX ページで構成されています。 各 ASPX ページは、対応する [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] パイプラインを拡張したものです。 パイプラインは ASPX ページに対して、RNIF (RosettaNet Implementation Framework) ヘッダーの処理を要求します。 ほとんどの HTTP 処理はパイプラインが実行しますが、RNIF ヘッダーの HTTP 処理は各 ASPX ページが実行します。 ASPX ページは、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP アダプタの機能を強化します。  
  
 各 ASPX ページは、ユーザー インターフェイスを持たない ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web アプリケーションです。 ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web セキュリティを使用して、外部パーティとの安全な接続を確立します。 フォールト トレランス、スケーラビリティ、可用性の高いサービスを実装できるレイヤを備えています。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] のセットアップ プログラムによって、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] の展開ごとに RNIFSend.aspx ページと RNIFReceive.aspx ページがインストールされます。 開始側または応答側が取引先とメッセージを交換する場合、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] は ASPX ページを使用して、取引先の URL との間でメッセージの送受信を行います。 開始側と応答側の両方で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を使用する場合は、開始側の 2 つの ASPX ページが応答側の 2 つの ASPX ページとメッセージを交換します。 詳細については、下の「開始側と応答側の ASPX ページの相互作用」を参照してください。  
  
## <a name="send-aspx-page"></a>送信 ASPX ページ  
 RNIFSend.aspx ページは、BizTalk HTTP アダプターからメッセージを受信します。 作成し、メッセージを RNIF ヘッダーを追加し、インターネット経由でパートナーにメッセージを送信します。 HTTP アダプターは、次のコマンドを使用して RNIFSend.aspx を呼び出します。  
  
```  
http://localhost:<port number>/RNIFSend.aspx?<query string>  
```  
  
 クエリ文字列には、以下に示すように、送信ページがメッセージをパートナーに送信するために必要なデータ、およびパートナーがメッセージを処理するために必要なデータが含まれます。  
  
- 取引先 URL: http://www.\<*アドレス*\>.com/RNIFReceive.aspx  
  
- 応答タイプ : 同期または非同期  
  
- RNIF バージョン : 1.1 または 2.0  
  
  BizTalk HTTP アダプタは、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 送信パイプラインによって生成された MIME メッセージを開始側の RNIFSend.aspx ページに送信します。 RNIFSend.aspx では、次のようにメッセージが処理されます。  
  
1.  送信ページがメッセージを検証します。  
  
2.  コンテンツ タイプ、長さ、ID、MIME バージョンに基づいて、送信ページが MIME (Multipurpose Internet Mail Extensions) ヘッダーを作成します。 さらに、MIME ヘッダー、および MIME の上位と下位の境界をメッセージに追加します。  
  
3.  RNIF 2.01 では、送信ページは次のように HTTP ヘッダーのプロパティを設定します。  
  
    1.  X-RN-Version プロパティを、プロセス構成設定のバージョン プロパティに入力されているバージョンに設定します。  
  
    2.  X-RN-ResponseType プロパティを、プロセス構成設定の IsSynchronous プロパティの設定に基づいて sync または async のいずれかに設定します。  
  
    3.  Content-Length プロパティを、メッセージ全体のサイズに設定します。  
  
4.  送信ページは HTTP Post を使用して、取引先アグリーメント内のアクション URL またはシグナル URL の設定に基づいて、パートナーの送信先 URL にメッセージを送信します。  
  
5.  送信ページは、HTTP 応答を待ちます。 送信ページは応答を受信すると、HTTP アダプターにルーティングします。  
  
6.  接続が非同期の場合、送信ページは接続を閉じて処理を終わらせます。  
  
7.  接続が同期の場合、送信ページは返信メッセージ用に接続を開いたままにしておきます。 送信ページはメッセージを受け取ると、RNIFReceive.aspx ページが受信メッセージに対して実行する処理と同じ処理を実行して、受信メッセージを HTTP アダプターに送信してから接続を閉じます。  
  
## <a name="receive-aspx-page"></a>受信 ASPX ページ  
 RNIFReceive.aspx ページは、インターネット経由でパートナーから HTTP メッセージを受信します。 RNIF ヘッダーの処理、検証、削除を行った後で、メッセージを HTTP アダプターに送信します。 受信ページが受け取るメッセージは、RNIF HTTP トランスポートに準拠している必要があります。 受信ページでは、次のようにメッセージが処理されます。  
  
1.  応答側の RNIFReceive.aspx ページが開始側からメッセージを受信します。 メッセージには、MIME ヘッダーと上位および下位の境界が含まれます。  
  
2.  受信ページが MIME ヘッダーを検証します。  
  
3.  受信ページが MIME ヘッダーと境界をメッセージから削除します。  
  
4.  受信ページが HTTP の受信場所を使用して、HTTP アダプターにメッセージを送信します。 受信ページが HTTP 応答を受信し、開始側の送信ページに HTTP 応答を返します。  
  
5.  接続が非同期の場合、受信ページは接続を閉じます。  
  
6.  接続が同期の場合、受信ページは接続を開いたまま返信メッセージを待ちます。  
  
7.  HTTP アダプターから返信メッセージを受け取ると、受信ページが RNIFSend.aspx ページと同じ処理を実行して、返信メッセージを開始側の送信ページに送信します。 HTTP 応答を受信した後で接続を閉じます。  
  
## <a name="how-initiator-and-responder-aspx-pages-interact"></a>開始側と応答側の ASPX ページの相互作用  
 開始側と応答側の両方で [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] を使用する場合、双方合わせて 4 つの ASPX ページの動作は、接続が同期か非同期かに応じて、およびメッセージがシングル アクションかダブル アクションかに応じて変わります。 以下に、それぞれの場合の動作について説明します。  
  
 **非同期のダブル アクション**  
  
 このシナリオでは、手順ごとに異なる HTTP 接続 (つまり合計で 4 つの HTTP 接続) を使用します。  
  
1. 開始側の送信ページがアクション要求メッセージを応答側の受信ページに送信します。  
  
   > [!NOTE]
   >  システムの負荷によっては、手順 2. と 3. の順序が入れ替わる場合があります。  
  
2. 応答側の送信ページが要求シグナル メッセージを開始側の受信ページに送信します。  
  
3. 応答側の送信ページがアクション応答メッセージを開始側の受信ページに送信します。  
  
4. 開始側の送信ページが応答シグナル メッセージを応答側の受信ページに送信します。  
  
   **非同期のシングル アクション**  
  
   このシナリオでは、手順ごとに異なる HTTP 接続 (つまり合計で 2 つの HTTP 接続) を使用します。 このシナリオは、非同期のダブル アクションのシナリオの手順 1. と 2. から構成されています。  
  
5. 開始側の送信ページがアクション要求メッセージを応答側の受信ページに送信します。  
  
6. 応答側の送信ページが要求シグナル メッセージを開始側の受信ページに送信します。  
  
   **同期のダブル アクション**  
  
   このシナリオでは、1 つの HTTP 接続を使用します。  
  
7. 開始側の送信ページがアクション要求メッセージを応答側の受信ページに送信します。  
  
8. 応答側の受信ページは手順 1. と同じ接続を使用して、アクション応答メッセージ (問題がある場合は例外) を開始側の送信ページに送信します。  
  
   **シングル アクションの同期**  
  
   このシナリオでは、1 つの HTTP 接続を使用します。  
  
9. 開始側の送信ページがアクション要求メッセージを応答側の受信ページに送信します。  
  
10. 応答側の受信ページは同じ接続を使用して、要求シグナル メッセージ (問題がある場合は例外) を開始側の送信ページに送信します。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)   
 [BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)   
 [BTARN 送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)