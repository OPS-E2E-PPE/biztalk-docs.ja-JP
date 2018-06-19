---
title: 受信側 AS2 経由で受信した非 EDI メッセージの処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fee10cba-8b1a-4d2c-b9d9-efbb74c3f461
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a313c7351f40ba3dbdaf33d15008598dac2ad73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269450"
---
# <a name="receive-side-processing-of-an-incoming-non-edi-message-over-as2"></a>AS2 経由で受信した非 EDI メッセージの受信側の処理
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属の AS2 パイプラインを使用すると、AS2 トランスポート経由の EDI メッセージまたは非 EDI メッセージを処理できます。 この 2 つの種類のペイロードで使用されるパイプラインは異なります。 AS2 経由の受信 EDI メッセージの処理には、AS2EdiReceive パイプラインを使用し、関連する MDN (有効になっている場合) を返すときには AS2Send パイプラインを使用します。 AS2 経由で受信した非 EDI メッセージの処理には、AS2Receive パイプラインを使用し、関連する MDN (有効になっている場合) を返すときには AS2Send パイプラインを使用します。 非 EDI メッセージは、任意のバイナリ ペイロードです。  
  
 AS2Receive 受信パイプラインは、AS2 メッセージをデコードした後、AS2 メッセージの逆アセンブルを実行します。 AS2Send 送信パイプラインは、MDN をエンコードします。 AS2Receive パイプラインと AS2Send パイプラインは、双方向の送信請求 - 応答の HTTP 送信ポート (MDN が同期の場合) か、一方向の HTTP 送信ポートと一方向の HTTP 受信ポート (MDN が非同期の場合) に含めることができます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では 1 つの受信パイプラインで実行できる逆アセンブルは 1 つだけであるため、非 EDI ペイロードの逆アセンブルを実行する必要がある場合、この処理は別のパイプラインで行うことが必要になります。 これは、ループバック送信ポートを必要とし、受信場所 (を参照してください、[受信した非 EDI ペイロードの処理](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md#BKMK_NonEDI)以下のセクション)。  
  
 AS2 経由で非 EDI インターチェンジを受信するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の手順を実行します。  
  
-   受信した AS2 メッセージの処理  
  
-   MDN の送信  
  
-   受信した非 EDI ペイロードの処理  
  
## <a name="processing-the-received-as2-message"></a>受信した AS2 メッセージの処理  
 AS2Receive 受信パイプラインの AS2 デコーダーは、受信 AS2 メッセージを処理します。 この処理は、HTTP アダプターが AS2 メッセージの HTTP ヘッダーから作成する、`InboundHTTPHeaders` コンテキスト プロパティを使用して行われます。 これらのヘッダーには、次の AS2 ヘッダーが含まれます。  
  
-   AS2-To  
  
-   AS2-From  
  
-   AS2-Version  
  
-   MessageID  
  
-   OriginalMessageID (MDN のみ)  
  
-   Disposition-Notification-To (MDN が要求されている場合)  
  
-   Receipt-Delivery-Option (MDN が要求されている場合)  
  
-   Signed-Receipt-MICalg (MDN が要求されている場合)  
  
 AS2 デコーダーは、これらのヘッダーをメッセージのコンテキストに昇格させます。 これは、後は、次の:  
  
-   アグリーメントの解決を実行して、受信メッセージの処理に使用するパーティのプロパティを特定します。 詳細については、次を参照してください。[受信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-incoming-as2-messages.md)です。  
  
-   AS2-From プロパティと AS2-To プロパティを使用して送信者を認証します。  
  
    > [!NOTE]
    >  AS2 受信パイプライン処理の詳細については、受信 AS2 メッセージに対して実行しを参照してください[受信 AS2 メッセージを処理](../core/processing-an-incoming-as2-message.md)です。  
  
## <a name="sending-an-mdn"></a>MDN の送信  
 MDN が有効にされている場合、AS2Receive パイプラインは MDN を生成し、メッセージボックスにドロップします。 最初のメッセージの送信者に MDN が返される方法は、AS2 トランスポートが同期であるか非同期であるかによって異なります。  
  
> [!NOTE]
>  送信 Mdn に対して行う AS2 受信パイプライン処理の詳細についてを参照してください[送信 MDN の生成](../core/generating-an-outgoing-mdn.md)です。  
  
 **同期モード**  
  
 非 EDI メッセージが AS2 経由で同期モードで送信される場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はその同期接続を経由して MDN を返し、接続を閉じます。 MDN は AS2Receive パイプラインによって生成され、メッセージ ボックスにルーティングされた後、要求 - 応答の受信ポートの一部である AS2Send パイプラインによって自動的に取得されます。  
  
 **非同期モード**  
  
 非 EDI メッセージが HTTP/HTTPS トランスポート経由で非同期モードで送信される場合は、MDN を個別に返すための送信ポートを作成する必要があります。 これが動的送信ポートである場合は、メッセージのヘッダーの Receipt-Delivery-Notification 行にあるアドレスを使用してメッセージを取引先にルーティングします。 静的送信ポートである場合は、ポート プロパティで定義されたアドレスを使用します。 この送信ポートは、`EdiIntAS.IsAS2AsynchronousMDN==True` フィルター式を使用して非同期 MDN をサブスクライブします。 非同期処理では、AS2Receive パイプラインが MDN だけでなく HTTP 応答も生成します。 受信ポートは、受信ポートと送信パーティ間の HTTP 接続を経由して元の送信者に HTTP 応答を返し、元の送信者がその接続を閉じます。 これが必要なのは、同期接続が MDN によって閉じられないためです。  
  
##  <a name="BKMK_NonEDI"></a>受信した非 EDI ペイロードの処理  
 EDI エンコードでないメッセージを AS2 経由で受信し、ペイロードの逆アセンブルを実行する必要がある場合、その処理は AS2Receive パイプライン以外の受信パイプラインで行う必要があります。 これは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では 1 つの受信パイプラインで実行できる逆アセンブルは 1 つだけであるためです。 このシナリオでは、送信ポートと受信場所を使用するループバック メカニズムが必要になります。 最初の受け渡しでは、EDIReceive パイプラインは AS2 メッセージを処理し、メッセージをネイティブ形式でメッセージ ボックスに送信します。 2 番目の受け渡しでは、受信パイプラインはメッセージのネイティブ形式から XML を生成します。  
  
 BizTalk Server は、AS2 BizTalk Server 経由で受け取った非 EDI メッセージに対して、次のような受信側の処理を実行します。  
  
-   要求 - 応答の双方向の受信場所に関連付けられている AS2Receive 受信パイプラインは、非 EDI メッセージの AS2 ヘッダーを解析し、このメッセージを BizTalk メッセージ ボックスにルーティングします。  
  
-   BizTalk のプロパティで `IsAS2PayloadMessage == True` が設定されているため、ループバック送信ポート (FILE または MSMQ) はメッセージ ボックスからこの非 EDI メッセージを取得します。 この送信ポートに関連付けられている PassThruTransmit 送信パイプラインは、フォルダーまたは MSMQ キューにメッセージをルーティングするときに、メッセージを非 EDI 形式で渡します。  
  
-   ループバック受信場所がメッセージを取得します。 ループバック受信場所に関連付けられている受信パイプラインは、非 EDI メッセージから XML メッセージを生成し、それをメッセージ ボックスにルーティングします。  
  
-   メッセージをバックエンド アプリケーションにルーティングする必要がある場合は、送信ポートが XML メッセージを取得してアプリケーションにルーティングします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)   
 [AS2 経由で送信 EDI メッセージの送信側の処理](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)