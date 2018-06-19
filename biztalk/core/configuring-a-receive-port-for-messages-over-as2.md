---
title: 構成、AS2 経由でメッセージの受信ポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01d4d897-d12b-4de4-a86b-e6d2718470c2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 324d8a7faf3ce21630502f219d033fb797aa3fc6
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968992"
---
# <a name="configuring-a-receive-port-for-messages-over-as2"></a>AS2 経由でのメッセージの受信ポートの構成
EDI または非 EDI ペイロードを持つ AS2 メッセージを受信するには、メッセージを受信してパーティに応答を返すための HTTP 受信ポートを作成します。  
  
 MDN が同期的に返される場合、受信ポートは双方向の要求 - 応答受信ポートである必要があります。 受信ポートの受信場所は AS2 メッセージを受信し、双方向受信ポートに関連付けられた送信ポートは同期 MDN を送信します。  
  
 MDN が非同期で返される場合、受信ポートは一方向受信ポートにすることができます。これは、MDN を個別の動的送信ポート経由で返す必要があるためです。 HTTP 応答は、一方向ポートか双方向ポートかにかかわらず、受信ポートによって返されます。 AS2 メッセージを受信するように双方向受信ポートを設定し、非同期 MDN を返すと、双方向受信場所の送信ポートを経由して HTTP 応答が返されます。  
  
> [!NOTE]
>  AS2 メッセージの受信に使用される双方向受信ポートを、MDN メッセージの受信に使用しないでください。 MDN メッセージは、静的な一方向の受信ポートで受信する必要があります。 MDN に要求/応答受信ポートを使用すると、着信 MDN に応答して 200OK メッセージが返されなくなるため、MDN 送信の不要な再試行が行われます。  
  
 次の構成を使用して受信ポートを作成します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**受信ポートのプロパティ: 全般**|[ポートの種類]|要求-応答|  
|**受信場所のプロパティ: 全般**|トランスポートの種類|HTTP**注:** EDIINT/AS2 でエンコードされたメッセージを転送するため、HTTP アダプタのみを使用できます。 このトランスポートは、HTTP アダプタ以外のアダプタでは使用できません。|  
|**受信場所のプロパティ: 全般**|[受信ハンドラー]|BizTalkServerIsolatedHost|  
|**受信場所のプロパティ: 全般**|受信パイプライン。|-AS2EdiReceive (ペイロードが場合 EDI でエンコードされた)<br />-AS2Receive (ペイロードが EDI でエンコードされた) 場合**注:** AS2EdiReceive パイプラインを使用する場合は、BizTalk Application Users グループで、BizTalk 分離ホスト インスタンス プロセスを実行しているユーザー アカウントを追加する必要があります。 AS2EdiReceive パイプラインは、BizTalk 分離ホスト インスタンス プロセスで実行されます。 AS2EdiReceive パイプラインは SSO ストアにアクセスします。この場合、ユーザーは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Application Users グループに属している必要があります。|  
|**受信場所のプロパティ: 全般**|[送信パイプライン]|AS2Send|  
|**HTTP トランスポートのプロパティ**|仮想ディレクトリと ISAPI 拡張|/\<仮想ディレクトリの名前\>>/btshttpreceive.dll|  
|**HTTP トランスポートのプロパティ**|要求 - 応答の返すコンテンツの種類|text/xml|  
  
## <a name="functionality-of-the-receive-location-in-synchronous-and-asynchronous-modes"></a>同期モードおよび非同期モードでの受信場所の機能  
 双方向の受信ポートは次の処理を実行して、EDI/AS2 メッセージを受信および処理し、応答を返します。  
  
-   HTTP 経由で AS2 メッセージを受信します。  
  
-   AS2EDIReceive 受信パイプライン (EDI エンコード メッセージの場合) または AS2Receive 受信パイプライン (EDI でエンコードされていないメッセージの場合) を使用して、AS2 メッセージを処理します。 このプロセスの詳細については、次を参照してください。[受信 AS2 メッセージを処理](../core/processing-an-incoming-as2-message.md)です。  
  
-   受信メッセージの次のコンテキスト プロパティを設定します。  
  
    -   `IsAS2PayloadMessage == True` (ペイロード メッセージのため)  
  
    -   `IsEmptyMDNResponse == False` (空の MDN ではないため)  
  
-   メッセージが EDI エンコードの場合、EDI ファイルを逆アセンブルし、XML ファイルを生成して MessageBox にドロップします。 各 XML ファイルの `BTS.MessageType` のコンテキスト プロパティを、名前空間を持つスキーマ名に設定します。  
  
-   メッセージが EDI エンコードではない場合は、ネイティブ形式のメッセージを MessageBox にドロップします。  
  
-   AS2EdiReceive 受信パイプラインを使用して MDN ファイルを生成します (有効になっている場合)。 このプロセスの詳細については、次を参照してください。[送信 MDN の生成](../core/generating-an-outgoing-mdn.md)です。 メッセージの次のコンテキスト プロパティを設定します。  
  
    -   `EdiIntAS.IsAS2AsynchronousMdn == False` (同期モードの場合)  
  
    -   `EdiIntAS.IsAS2AsynchronousMdn== True` (非同期モードの場合)  
  
-   同期モードの場合、AS2Send 送信パイプラインを使用して MDN ファイルを送信します (有効になっている場合)。 このプロセスの詳細については、次を参照してください。 [、送信 MDN を送信する](../core/sending-an-outgoing-mdn.md)です。  
  
-   非同期モードの場合、MDN ファイルが有効な場合は、そのファイルを MessageBox にルーティングします (MDN ファイルの取得および送信に使用される個別の動的送信ポート)。  
  
-   非同期モードの場合、非同期で返される完全な MDN 以外に空の MDN を生成します。 メッセージの次のコンテキスト プロパティを設定します。  
  
    -   `IsAS2PayloadMessage == False`  
  
    -   `IsEmptyMDNResponse == True`  
  
-   非同期モードの場合、受信ポートと送信パーティ間の HTTP 接続を経由して元の送信者に HTTP 応答を返し、元の送信者がその接続を閉じます。 これは、同期接続は完全な MDN によって切断されないためです。  
  
-   確認メッセージを生成し (有効になっている場合)、MessageBox にドロップします。 `BTS.MessageType` のコンテキスト プロパティを、確認管理スキーマに設定します。  
  
## <a name="see-also"></a>参照  
 [AS2 ソリューションのポートを構成します。](../core/configuring-ports-for-an-as2-solution.md)   
 [入力方向の AS2 メッセージの処理](../core/processing-an-incoming-as2-message.md)   
 [送信 MDN の生成](../core/generating-an-outgoing-mdn.md)   
 [送信 MDN の送信](../core/sending-an-outgoing-mdn.md)