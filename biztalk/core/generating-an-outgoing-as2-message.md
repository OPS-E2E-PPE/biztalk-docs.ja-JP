---
title: 送信 AS2 メッセージを生成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 288c8101-9a96-4f98-ae18-df43c7cdb3a0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90a0b1e37e96086de7d8901b61afa8dea859a388
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246546"
---
# <a name="generating-an-outgoing-as2-message"></a>送信 AS2 メッセージの生成
AS2EDISend および AS2Send の各送信パイプラインは、次に示すように送信メッセージを生成します。 各パイプラインの一方向アグリーメント タブでプロパティを使用して、**アグリーメントのプロパティ** ダイアログ ボックスを送信 AS2 メッセージを生成します。  
  
## <a name="agreement-destination-and-messageid-determination"></a>アグリーメント、送信先、および MessageID の決定  
 AS2 メッセージの送信に使用されるアグリーメントおよび送信先は、AS2 送信パイプラインによって次のように決定されます。  
  
-   送信メッセージの処理に使用するアグリーメントを決定する場合、AS2 エンコーダーは、メッセージ内の AS2-To プロパティとパーティのビジネス プロファイルの AS2Identity の照合、またはメッセージをサブスクライブしている送信ポートアグリーメントに関連付けられた送信ポートの照合を行います。 このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージのアグリーメントの解決](../core/agreement-resolution-for-outgoing-as2-messages.md)です。  
  
-   メッセージの送信先を決定する場合、動的送信ポート内の送信パイプラインは、OutboundTransportLocation プロパティを使用します。このプロパティを使用するには、動的送信ポートのバックエンド アプリケーションを使用してコンテキストに書き込むか、コンテキストに昇格させる必要があります。 静的送信パイプライン内の送信パイプラインは、AS2 アグリーメント プロパティ内の AS2-From プロパティ、およびビジネス プロファイル プロパティの ID から送信先を決定します。  
  
-   AS2 エンコーダーは、送信 AS2 メッセージの MessageId ヘッダーを設定する必要があります。 送信パイプラインは、`EdiIntAS.MessageId` コンテキスト プロパティまたは `HTTP.UserHttpHeaders` コンテキスト プロパティから MessageId を決定します。 どちらのコンテキスト プロパティも設定されている場合、AS2 エンコーダーは `HTTP.UserHttpHeaders` コンテキスト プロパティの値を使用します。 どちらのコンテキスト プロパティも設定されていない場合は、送信パイプラインが MessageID の値を自動生成します。  
  
## <a name="outgoing-message-processing"></a>送信メッセージの処理  
 AS2 送信パイプラインは、次の手順により送信 AS2 メッセージを処理します。  
  
-   ネイティブ形式のメッセージのコピーを作成し、否認不可データベースに保存します (AS2 メッセージの否認不可がアグリーメント プロパティで有効になっている場合)。  
  
-   AS2 エンコーダーは、HTTP (および AS2) ヘッダーを `HTTP.UserHttpHeaders` コンテキスト プロパティに構築します。 このプロセスの詳細については、次を参照してください。 [AS2 経由で送信 EDI メッセージの送信側の処理](../core/send-side-processing-of-an-outgoing-edi-message-over-as2.md)です。  
  
-   `HTTP.UserHttpHeaders` をコンテキストに書き込みます。  
  
-   送信メッセージを圧縮します (有効になっている場合)。  
  
-   メッセージの暗号化を含む MIME 処理を実行します (有効な場合に、**メッセージを暗号化する**アグリーメント プロパティ) デジタル署名を適用して (で有効になっている場合、**メッセージは署名付きをする必要があります**アグリーメントのプロパティ)。 AS2Send パイプラインは、SHA1 または MD5 を使用してアグリーメント設定に基づき署名を適用します。  
  
-   指定された値を含む Content-Disposition MIME ヘッダーを作成します (送信ファイル名がアグリーメント プロパティで有効になっている場合)。  
  
-   (ワイヤ形式)、暗号化されたメッセージのコピーを作成し、保存、否認不可データベース内で有効になっている場合、**エンコードされた送信の AS2 メッセージに対して有効な NRR**アグリーメント プロパティです。  
  
-   MDN が必要な場合は、MIC 値を計算してデータ ストアに保存します。  
  
-   メッセージを HTTP アダプターに配信します。HTTP アダプターは、UserHTTPHeaders コンテキスト プロパティから送信 AS2 メッセージにヘッダーを書き込みます。  
  
-   信頼できるメッセージ処理が必要な場合は、MDN が受信するまでメッセージを再送信します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server が AS2 メッセージを送信する方法](../core/how-biztalk-server-sends-as2-messages.md)   
 [AS2 送信コンポーネント](../core/as2-send-components.md)