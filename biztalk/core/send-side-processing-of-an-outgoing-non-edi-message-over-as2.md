---
title: 送信側の AS2 経由で送信非 EDI メッセージの処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f19b7df-fe6d-4105-8a44-3d6db0bba451
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47b4f553d5f16812958addab8082b5e0c79d7f0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254467"
---
# <a name="send-side-processing-of-an-outgoing-non-edi-message-over-as2"></a>AS2 経由での送信非 EDI メッセージの送信側の処理
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属の AS2 パイプラインを使用すると、AS2 トランスポート経由の EDI メッセージまたは非 EDI メッセージを処理できます。 この 2 つの種類のペイロードで使用されるパイプラインは異なります。 AS2 経由の送信 EDI メッセージの処理には、AS2EdiSend 送信パイプラインを使用し、関連する MDN (有効になっている場合) の受信には AS2Receive パイプラインを使用します。 AS2 経由の送信非 EDI メッセージの処理には、AS2Send 送信パイプラインを使用し、関連する MDN (有効になっている場合) の受信には AS2Receive パイプラインを使用します。 非 EDI メッセージは、任意のバイナリ ペイロードです。  
  
 AS2Send 送信パイプラインは、非 EDI ペイロードをアセンブルし、AS2 メッセージをエンコードします。 AS2Receive 受信パイプラインは、MDN 応答をデコードします。 これらのパイプラインは、双方向の送信請求 - 応答の HTTP 送信ポート (MDN が同期の場合) か、一方向の HTTP 送信ポートと一方向の HTTP 受信ポート (MDN が非同期の場合) に含めることができます。  
  
 AS2 経由で EDI インターチェンジを送信するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は次の手順を実行します。  
  
-   非 EDI ペイロードを送信するための処理  
  
-   AS2 メッセージの送信  
  
-   返された MDN の受信  
  
## <a name="processing-the-non-edi-payload-for-sending"></a>送信するための非 EDI ペイロードの処理  
 AS2 メッセージを作成する前に、送信ポートは、メッセージをサブスクライブするための適切なフィルター式を使用して非 EDI ペイロードを取得する必要があります。 MDN が同期型か非同期型かに応じて、双方向または一方向の送信ポートを使用できます。 次に、AS2Send パイプラインは、非 EDI ペイロードを処理して AS2 メッセージを作成します。  
  
## <a name="sending-the-as2-message"></a>AS2 メッセージを送信します。  
 AS2 送信パイプラインの AS2 エンコーダーは、最初にアグリーメントの解決を実行して、送信メッセージの処理に使用するアグリーメントのプロパティを特定します。 詳細については、次を参照してください。[送信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-outgoing-as2-messages.md)します。  
  
 AS2 エンコーダーは、AS2 メッセージを送信するために必要な一連の HTTP ヘッダーを構築します。 これらのヘッダーは `HTTP.UserHttpHeaders` コンテキスト プロパティに追加されます。このコンテキスト プロパティは、複数のヘッダー値から成る単一の文字列です。 AS2 エンコーダーは、次の AS2 ヘッダーを HTTP.UserHttpHeaders 内に構築します。 AS2 メッセージには、これらのヘッダーが含まれている必要があります。  
  
- AS2-To  
  
- AS2-From  
  
- AS2-Version  
  
- MessageID  
  
- OriginalMessageID (MDN のみ)  
  
  場合、 **mdn を要求する**プロパティがチェックされ、パイプラインはメッセージの対応するプロパティとその値に廃棄で通知を確認メッセージの配信オプション、およびの Signed-receipt-micalg AS2 ヘッダーを設定場合に「pcks7 署名」に署名済みの受信プロトコルの AS2 ヘッダーを設定、**署名付き MDN を要求**プロパティがチェックされます。  
  
  `HTTP.UserHttpHeaders` コンテキスト プロパティが存在しない場合は、AS2 エンコーダーによって作成されます。 `HTTP.UserHttpHeaders` コンテキスト プロパティが既に存在する場合、新規作成はされず、AS2 エンコーダーはそのプロパティを使用します。 ユーザーが `HTTP.UserHttpHeaders` を作成し、ヘッダーを書き込んで、メッセージのコンテキストに書き込んだ場合、AS2 エンコーダーではこれらのヘッダーが使用され、他のソースからのヘッダーよりも優先されます。 ただし、AS2-From ヘッダーは例外で、常にアグリーメントのプロパティから取得されます。  
  
  `HTTP.UserHttpHeaders` に AS2 ヘッダーが存在しない場合は、AS2 エンコーダーによって単一のコンテキスト プロパティから追加されます。 これは、ユーザーがメッセージのコンテキストに AS2 ヘッダーを昇格させるか書き込むことによって、AS2 ヘッダーを追加できることを意味します (AS2 ヘッダーが `HTTP.UserHttpHeaders` に存在しない場合)。 `HTTP.UserHttpHeaders`に AS2 ヘッダーが存在せず、コンテキストのプロパティとしても存在しない場合、AS2 エンコーダーは、アグリーメントのプロパティから AS2 ヘッダーを `HTTP.UserHttpHeaders` に追加します。  
  
  AS2 エンコーダーは、`HTTP.UserHttpHeaders` プロパティでヘッダーを構築した後、そのヘッダーをメッセージのコンテキストに書き込みます。 HTTP アダプターは `HTTP.UserHttpHeaders` を取得し、`HTTP.UserHttpHeaders` のヘッダー値をメッセージの前に付加します。  
  
> [!NOTE]
>  AS2 トランスポートは、HTTP アダプターと共に使用することだけが想定されています。 ただし、適切なコンテキスト プロパティを手動で設定すると、FILE アダプターを使用して AS2 メッセージを送信できます。 詳細については、次を参照してください。 [FILE 送信ポートを経由で AS2 メッセージの送信](../core/sending-an-as2-message-over-a-file-send-port.md)します。  
  
## <a name="processing-the-returned-mdn"></a>返された MDN の処理  
 MDN が有効になっている場合、双方向送信ポートに関連付けられた受信パイプラインは、AS2 メッセージの受信側パーティから MDN を受信します。  
  
> [!NOTE]
>  受信 mdn メッセージに対して、AS2 送信パイプラインを実行する処理の詳細については、次を参照してください。[送信 MDN の送信](../core/sending-an-outgoing-mdn.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)