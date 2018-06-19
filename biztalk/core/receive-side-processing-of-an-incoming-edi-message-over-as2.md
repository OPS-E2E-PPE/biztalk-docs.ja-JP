---
title: 受信側の処理、受信 EDI メッセージの AS2 経由で |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 118451ab-d847-4f87-80ab-3cf812d71ac3
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fc9069dddf8a8b58ad439ed915fc9afa539c2a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270066"
---
# <a name="receive-side-processing-of-an-incoming-edi-message-over-as2"></a>AS2 経由での受信 EDI メッセージの受信側の処理
AS2 経由の EDI メッセージの受信側の処理では、AS2 メッセージの受信、MDN の送信、EDI ペイロードの処理、および EDI 受信確認の送信 (有効になっている場合) が行われます。  
  
 AS2EdiReceive 受信パイプラインは、AS2 メッセージを受信し、AS2 メッセージ内の EDI ペイロードを逆アセンブルします。 AS2EDISend 送信パイプラインは、AS2 メッセージへの応答としての MDN と、EDI メッセージへの応答として返される EDI 受信確認を送信します。 これらを含めることができます双方向 http パイプラインに送信請求応答の送信ポート (MDN が同期の場合)、または一方向の HTTP 送信ポートと一方向の HTTP 受信ポート (MDN が非同期の場合)。  
  
 AS2 経由で EDI インターチェンジを受信するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の手順を実行します。  
  
-   受信した AS2 メッセージの処理  
  
-   MDN の送信  
  
-   受信した EDI ペイロードの処理  
  
-   EDI 受信確認を送信します。  
  
## <a name="processing-the-received-as2-message"></a>受信した AS2 メッセージの処理  
 AS2EdiReceive 受信パイプラインの AS2 デコーダーが受信 AS2 メッセージを処理します。 この処理は、HTTP アダプターが AS2 メッセージの HTTP ヘッダーから作成する、`InboundHTTPHeaders` コンテキスト プロパティを使用して行われます。 これらのヘッダーには、次の AS2 ヘッダーが含まれます。  
  
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
  
-   使用して送信者の認証、 **AS2-から**プロパティです。  
  
    > [!NOTE]
    >  AS2 受信パイプライン処理の詳細については、受信 AS2 メッセージに対して実行しを参照してください[受信 AS2 メッセージを処理](../core/processing-an-incoming-as2-message.md)です。  
  
## <a name="sending-an-mdn"></a>MDN の送信  
 MDN が有効にされている場合、AS2EdiReceive パイプラインは MDN を生成し、メッセージボックスにドロップします。  
  
> [!NOTE]
>  送信 Mdn に対して行う AS2 受信パイプライン処理の詳細についてを参照してください[送信 MDN の生成](../core/generating-an-outgoing-mdn.md)です。  
  
 **同期モード**  
  
 EDI メッセージが AS2 経由で同期モードで送信される場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はその同期接続を経由して MDN を返し、接続を閉じます。 接続が閉じられているので、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はその接続経由で EDI 受信確認 (997、TA1、または CONTRL) を返信できません。 EDI 受信確認は、AS2 経由で常に非同期に送信されます。  
  
 MDN は AS2EDIReceive パイプラインによって生成され、メッセージ ボックスにルーティングされた後、要求 - 応答の受信ポートの一部である AS2Send パイプラインによって自動的に取得されます。  
  
 **非同期モード**  
  
 EDIINT/AS2 でエンコードされたメッセージが HTTP/HTTPS トランスポート経由で非同期モードで送信される場合は、MDN を個別に返すための送信ポートを作成する必要があります。 この送信ポートは、非同期の MDN および EDI 受信確認の両方を返すように構成できます。 これが動的送信ポートである場合は、メッセージのヘッダーの Receipt-Delivery-Notification 行にあるアドレスを使用してメッセージを取引先にルーティングします。 静的送信ポートである場合は、ポート プロパティで設定されたアドレスを使用します。 この送信ポートは、`EdiIntAS.IsAS2AsynchronousMDN==True` フィルター式を使用して非同期 MDN をサブスクライブします。  
  
 非同期処理では、AS2EdiReceive パイプラインは MDN だけでなく HTTP 応答も生成します。 受信ポートは、受信ポートと送信パーティ間の HTTP 接続を経由して元の送信者に HTTP 応答を返し、元の送信者がその接続を閉じます。 これが必要なのは、同期接続が MDN によって閉じられないためです。  
  
 BizTalk が EDIINT/AS2 でエンコードされたメッセージを HTTP/HTTPS 経由で送受信できても、EDI でエンコードされたペイロードの処理が失敗する場合、元のメッセージの送信者は、AS2 の処理が成功したことを示す MDN と EDI の処理が失敗したことを示す EDI 受信確認の両方を受け取ります。 EDI でエンコードされたペイロードは中断され、エラーが通知されます。  
  
## <a name="processing-the-received-edi-payload"></a>受信した EDI ペイロードの処理  
 場合、**受信バッチ処理オプション**に設定されているアグリーメントの EDI**分割されたインターチェンジ**、AS2EdiReceive 受信パイプラインは、双方向に関連付けられている要求の応答の受信場所の解析、EDI メッセージを EDI トランザクションごとに個別の XML メッセージに設定します。 場合、**受信バッチ処理オプション**に設定されている**インターチェンジの保存**、受信パイプラインは EDI メッセージを解析できません。  
  
 受信パイプラインは、XML トランザクション セットまたは保存された EDI インターチェンジを、BizTalk のメッセージ ボックスにルーティングします。  
  
 メッセージをバックエンド アプリケーションにルーティングする必要がある場合は、送信ポートが XML メッセージを取得してアプリケーションにルーティングします。  
  
> [!NOTE]
>  この送信ポートの種類は任意で決定できます。  
  
## <a name="sending-the-edi-acknowledgment"></a>EDI 受信確認の送信  
 EDI 受信確認が有効にされている場合、AS2EdiReceive 受信パイプラインの EDI 逆アセンブラーによって EDI 受信確認が生成されます (有効になっている場合)。 EDI 受信確認は、AS2EdiSend 送信パイプラインによって、別の一方向送信ポートで送信される必要があります。  
  
 双方向の要求-応答を設定した場合の受信ポートの EDI および AS2 メッセージを応答として同期 MDN または (非同期 MDN の場合)、HTTP 応答を返す、**要求-応答で送信パイプラインに確認をルーティングの受信ポート**プロパティ (設定、**ローカル ホストの設定**で一方向 EDI アグリーメントのページ、**アグリーメントのプロパティ** ダイアログ ボックス) は無視されます。 このプロパティがオンになっていても、送信パイプラインは EDI 受信確認ではなく同期 MDN または HTTP 応答を返します。  
  
 詳細については、次を参照してください。 [EDI 受信確認を送信する](../core/sending-an-edi-acknowledgment.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを受信する方法](../core/how-biztalk-server-receives-as2-messages.md)