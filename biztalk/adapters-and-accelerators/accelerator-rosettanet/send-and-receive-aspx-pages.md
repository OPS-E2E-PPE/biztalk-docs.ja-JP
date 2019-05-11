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
ms.openlocfilehash: d93c41a87465a75adc2047889ff6cb80cdf629fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281962"
---
# <a name="send-and-receive-aspx-pages"></a>送信および受信 ASPX ページ
Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX ページは、直接結ぶインターフェイス[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]とインターネットです。 2 つの ASPX ページは、受信ページ (RNIFReceive.aspx) と、送信ページ (RNIFSend.aspx) です。 各 ASPX ページは、対応する拡張子[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]パイプライン。 パイプラインでは、RosettaNet Implementation Framework (RNIF) ヘッダーを処理する ASPX ページが必要です。 パイプライン処理です。 HTTP のほとんどを実行します。ただし、各 ASPX ページは、RNIF ヘッダーの HTTP 処理を実行します。 ページの機能を補完する、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP アダプター。  
  
 各 ASPX ページは、ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web ユーザー インターフェイスを持たないアプリケーション。 ASP を使用する[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]Web セキュリティを外部関係者とセキュリティで保護された接続を確認します。 フォールト トレランス、スケーラビリティ、および可用性の高いサービスを実装できるレイヤを備えています。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] セットアップの展開ごとに RNIFSend.aspx ページと RNIFReceive.aspx ページのインストール[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]します。 応答側か相手側が取引先パートナーとメッセージを交換するとき[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]ASPX ページを使用して、メッセージを送信または取引先の URL からメッセージを受信します。 場合は、イニシエーターとレスポンダーの両方を使用して、 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]、発信側の 2 つの ASPX ページが応答側の 2 つの ASPX ページとメッセージを交換します。 詳細については、「イニシエーターとレスポンダー ASPX ページの対話方法」の下のサブセクションを参照してください。  
  
## <a name="send-aspx-page"></a>送信 ASPX ページ  
 RNIFSend.aspx ページは、BizTalk HTTP アダプターからメッセージを受信します。 作成し、メッセージを RNIF ヘッダーを追加し、インターネット経由でパートナーにメッセージを送信します。 HTTP アダプターは、次のコマンドを使用して RNIFSend.aspx を呼び出します。  
  
```  
http://localhost:<port number>/RNIFSend.aspx?<query string>  
```  
  
 クエリ文字列には、次のデータ送信ページが、パートナーにメッセージを送信する必要があると、パートナーがメッセージの処理に必要なデータが含まれています。  
  
- 取引先 URL: http://www.\<*アドレス*\>.com/RNIFReceive.aspx  
  
- 応答タイプ: 同期または非同期  
  
- RNIF バージョン:1.1 または 2.0。  
  
  BizTalk HTTP アダプターによって生成された MIME メッセージの送信、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]開始側の RNIFSend.aspx ページに送信パイプラインです。 RNIFSend.aspx では、としては、次のように、メッセージを処理します。  
  
1.  送信ページは、メッセージの検証を実行します。  
  
2.  送信ページは、コンテンツの種類、長さ、ID、および MIME バージョンに基づいて、Multipurpose Internet Mail Extensions (MIME) ヘッダーを作成します。 MIME ヘッダー、および上限と下限の MIME 境界をメッセージに追加します。  
  
3.  RNIF 2.01 は、送信ページは、HTTP ヘッダーのプロパティとしては、次のように設定されます。  
  
    1.  プロセス構成設定のバージョンのプロパティに入力されているバージョンに X-RN バージョン プロパティを設定します。  
  
    2.  同期または非同期にプロセス構成設定の IsSynchronous プロパティの設定に応じてのいずれかに X-RN-ResponseType プロパティを設定します。  
  
    3.  完全なメッセージのサイズをコンテンツの長さのプロパティを設定します。  
  
4.  HTTP Post を使用して、送信ページにメッセージを送信パートナーの送信先の URL、取引先アグリーメントでアクションの URL またはシグナル URL の設定で設定されています。  
  
5.  送信ページは、HTTP 応答を待機します。 応答を受信した場合、HTTP アダプターにルーティングします。  
  
6.  接続が非同期の場合は、送信ページは、接続を閉じます、その処理が完了します。  
  
7.  接続が同期の場合、送信ページ接続を開いたまま返信メッセージ用。 メッセージを受信した後は、RNIFReceive.aspx ページに受信したメッセージに対して実行しますし、HTTP アダプターに受信したメッセージを送信し、接続を閉じますことと同じ処理を実行します。  
  
## <a name="receive-aspx-page"></a>受信 ASPX ページ  
 RNIFReceive.aspx ページは、インターネット経由でパートナーからの HTTP メッセージを受信します。 処理、検証、および、RNIF ヘッダーを削除し、HTTP アダプターにメッセージを送信します。 受信ページが受信したメッセージは、RNIF HTTP トランスポートに準拠していませんである必要があります。 受信ページは、としては、次のようにメッセージを処理します。  
  
1.  応答側の RNIFReceive.aspx ページは、発信側からメッセージを受信します。 メッセージには、MIME ヘッダーと上限と下限の境界が含まれています。  
  
2.  受信ページが MIME ヘッダーを検証します。  
  
3.  受信ページは、メッセージから MIME ヘッダーと境界を削除します。  
  
4.  受信ページは、HTTP の受信場所を使用して、HTTP アダプターにメッセージを投稿します。 受信ページは、HTTP 応答を受信し、発信側の送信ページに HTTP 応答を返します。  
  
5.  接続が非同期の場合、受信ページは、接続を閉じます。  
  
6.  接続が同期の場合、受信ページ接続を開いたまま、返されたメッセージを待機しています。  
  
7.  HTTP アダプターから返されたメッセージを受信した後、受信ページ実行と同じ処理を RNIFSend.aspx ページは、開始側の送信ページに、返されたメッセージを送信します。 HTTP 応答を受信した後は、接続を閉じます。  
  
## <a name="how-initiator-and-responder-aspx-pages-interact"></a>イニシエーターとレスポンダーの ASPX ページの相互作用  
 場合は、イニシエーターとレスポンダーの両方を使用して、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]イニシエーターとレスポンダーの 4 つの ASPX ページは、接続が非同期または同期がかどうかと、メッセージがシングル アクションかダブル アクションのかどうかに応じて異なる方法で対話. 次のサブセクションでは、相互作用の完全なセットについて説明します。  
  
 **非同期のダブル アクション**  
  
 このシナリオには、ステップごとに 1 つの 4 つの異なる HTTP 接続が含まれます。  
  
1. アクション要求メッセージ、応答側を発信側の送信ページはページが表示されます。  
  
   > [!NOTE]
   >  手順 2. および 3. 下のシステムの負荷に応じて、逆の順序で発生します。  
  
2. 要求シグナル メッセージの発信側に応答側の送信ページはページが表示されます。  
  
3. アクションの応答メッセージの発信側に応答側の送信ページはページが表示されます。  
  
4. 開始側の送信ページは応答シグナルが応答側にメッセージの受信ページ。  
  
   **非同期のシングル アクション**  
  
   このシナリオには、各手順のいずれか 2 つの異なる HTTP 接続が含まれます。 このシナリオでは手順 1. および 2. 非同期ダブル アクション シナリオのことに注意してください。  
  
5. アクション要求メッセージ、応答側を発信側の送信ページはページが表示されます。  
  
6. 要求シグナル メッセージの発信側に応答側の送信ページはページが表示されます。  
  
   **同期のダブル アクション**  
  
   このシナリオには、1 つの HTTP 接続が含まれます。  
  
7. アクション要求メッセージ、応答側を発信側の送信ページはページが表示されます。  
  
8. 応答側の受信ページは、アクション応答メッセージ (または問題がある場合は例外) を手順 1. で使用する同じ接続上でイニシエーターの送信ページ。  
  
   **シングル アクションの同期**  
  
   このシナリオには、1 つの HTTP 接続が含まれます。  
  
9. アクション要求メッセージ、応答側を発信側の送信ページはページが表示されます。  
  
10. 応答側の受信ページは、要求シグナル メッセージ (または問題がある場合は例外) を同じ接続上でイニシエーターの送信ページ。  
  
## <a name="see-also"></a>参照  
 [BTARN でのメッセージ処理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)   
 [BTARN 受信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)   
 [BTARN 送信パイプライン](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)