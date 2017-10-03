---
title: "AS2 コンテキスト プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4d63104-f31e-4ed2-b294-ba3ea8a39ae6
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f66fa78b1efb8bd6850e64ba002ecd8e1cb91f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="as2-context-properties"></a>AS2 のコンテキスト プロパティ
次の 5 種類のコンテキスト プロパティが [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の AS2 メッセージに適用されます。  
  
-   EdiIntProperties.xsd スキーマ内のコンテキスト プロパティ  
  
-   [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 内部のコンテキスト プロパティ  
  
-   BizTalk MIME 内部のコンテキスト プロパティ  
  
-   AS2 内部のコンテキスト プロパティ  
  
-   AS2 状態レポート内部のコンテキスト プロパティ  
  
## <a name="context-properties-in-the-ediintpropertiesxsd-schema"></a>EdiIntProperties.xsd スキーマ内のコンテキスト プロパティ  
 EDI/INT グローバル プロパティ スキーマのメッセージ コンテキスト プロパティは公開されるため、メッセージ ルーティングなどの操作で使用できます。 これらのコンテキスト プロパティは、`Microsoft.BizTalk.Edi.BaseArtifacts` アセンブリの EdiIntProperties.xsd で定義されています。 これらのプロパティの名前空間は `http://schemas.microsoft.com/BizTalk/2006/as2-properties` です。 昇格は、これらのメッセージ コンテキスト プロパティとして利用可能な`EdiIntAS.<Property Name>`で、**フィルター**のページ、**送信ポートのプロパティ** ダイアログ ボックス。  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|AS2From|string|送信者の名前を表す AS2-From AS2 ヘッダー値を含んでいます。|  
|AS2PayloadContentType|string|ペイロード メッセージのコンテンツの種類を含んでいます。|  
|AS2To|string|受信者の名前を表す AS2-To AS2 ヘッダー値を含んでいます。|  
|DispositionMode|string|MDN 配置モード値を含んでいます。<br /><br /> MDN が生成されるようにするには、このコンテキスト プロパティと DispositionType コンテキスト プロパティの両方を昇格させる必要があります。|  
|DispositionType|string|MDN 配置の種類の値を含んでいます。<br /><br /> MDN が生成されるようにするには、このコンテキスト プロパティと DispositionMode コンテキスト プロパティの両方を昇格させる必要があります。|  
|IsAS2AsynchronousMdn|boolean|メッセージが非同期 MDN であることを示します。|  
|IsAS2FailedMessage|boolean|受信 AS2 メッセージの AS2 での処理が失敗し、ペイロード メッセージが中断されたことを示します。|  
|IsAS2Http200OKResponse|boolean|HTTP 200 OK 応答メッセージとして生成されるメッセージで設定します。 これは、MDN が AS2 メッセージに対して生成されないか、MDN が非同期に送信される場合に使用されます。|  
|IsAS2MdnResponseMessage|boolean|メッセージが MDN 応答メッセージであることを示します。|  
|IsAS2MessageDuplicate|boolean|受信 AS2 メッセージが以前に受信されていることを示します。|  
|IsAS2MessageCompressed|boolean|受信 AS2 メッセージが圧縮されたことを示します。|  
|IsAS2MessageEncrypted|boolean|受信 AS2 メッセージが暗号化されたことを示します。|  
|IsAS2MessageSigned|boolean|受信 AS2 メッセージが署名されたことを示します。|  
|IsAS2PayloadMessage|boolean|このメッセージにはデコードされた AS2 メッセージ コンテンツが含まれており、ペイロードとして処理する必要があることを示します。|  
|MDNAsyncURI|string|含まれています、 **- Receipt-delivery-option**非同期 MDN 応答メッセージを送信する際に使用される値。|  
|MessageId|string|AS2 メッセージのヘッダーに含められる AS2 メッセージ ID を含んでいます。|  
|OriginalMessageId|string|元の AS2 メッセージのメッセージ ID を含んでいます。 このコンテキスト プロパティは、MDN メッセージの一部であり、AS2 メッセージとその MDN 応答を関連付けるために使用されます。|  
|PreservedFileName|string|メッセージの元のファイル名です。 このコンテキスト プロパティは、受信メッセージに Content-Disposition MIME ヘッダーの一部としてファイル名情報が含まれる場合のみ設定されます。|  
|SendMDN|boolean|MDN メッセージを生成する必要がある場合は true に設定します。|  
  
## <a name="context-properties-internal-to-biztalk-server"></a>BizTalk Server 内部のコンテキスト プロパティ  
 以下のメッセージ コンテキスト プロパティは公開されないため、メッセージ ルーティングなどの操作で使用できません。 ただし、中断されたメッセージおよび追跡メッセージで表示することはできます。 これらのコンテキスト プロパティの名前空間は、`http://schemas.microsoft.com/BizTalk/2006/system-properties` です。  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|IgnoreSslCertificateNameMismatchErrors|boolean|処理中の SSL 名の不一致エラーを無視するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の HTTP 処理に指示します。|  
|KeepAlive|ブール値|HTTP の接続保持機能の動作を制御します。|  
|TreatEPMSuspendAsSuccess|boolean|双方向の HTTP 受信接続での処理時に中断されたメッセージを成功したメッセージとして取り扱うように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に指示します。|  
|IsSolicitResponse|boolean|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] により設定され、メッセージが送信請求 - 応答メッセージであることを示します。|  
  
## <a name="context-properties-internal-to-biztalk-mime"></a>BizTalk MIME 内部のコンテキスト プロパティ  
 以下のメッセージ コンテキスト プロパティは公開されないため、メッセージ ルーティングなどの操作で使用できません。 ただし、中断されたメッセージおよび追跡メッセージで表示することはできます。 これらのコンテキスト プロパティの名前空間は、`http://schemas.microsoft.com/BizTalk/2006/system-properties` です。  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|IsMultipartReport|boolean|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の MIME エンコーダーがマルチパート/レポート メッセージを生成するようにします。|  
|SuppressMimeVersionFromMultiPartMessage|boolean|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の MIME エンコーダーがマルチパート メッセージの各部分において MIME Version ヘッダーを非表示にするようにします。|  
  
## <a name="context-properties-internal-to-as2"></a>AS2 内部のコンテキスト プロパティ  
 以下のメッセージ コンテキスト プロパティは公開されないため、メッセージ ルーティングなどの操作で使用できません。 ただし、中断されたメッセージおよび追跡メッセージで表示することはできます。 これらのコンテキスト プロパティの名前空間は、`http://schemas.microsoft.com/BizTalk/2006/as2-properties` です。  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|MicHashAlgorithm|string|MIC ハッシュ値の計算時に使用されるハッシュ アルゴリズムを含んでいます。|  
|ReceivedContentMic|string|計算された MIC ハッシュ値を含んでいます。|  
  
## <a name="context-properties-internal-to-as2-status-reporting"></a>AS2 内部のコンテキスト プロパティの状態レポート  
 以下のメッセージ コンテキスト プロパティは公開されないため、メッセージ ルーティングなどの操作で使用できません。 ただし、中断されたメッセージおよび追跡メッセージで表示することはできます。 これらのコンテキスト プロパティの名前空間は、`http://schemas.microsoft.com/BizTalk/2006/edi-properties` です。  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|InterchangeControlNo|string|EDI インターチェンジのインターチェンジ制御番号です。 このプロパティは、AS2 のエンコード中にメッセージから読み取られ、AS2 のインターチェンジ アクティビティを報告するために使用されます。|  
|InterchangeDate|string|EDI インターチェンジからのインターチェンジ日付です。 このプロパティは、AS2 のエンコード中にメッセージから読み取られ、AS2 のインターチェンジ アクティビティを報告するために使用されます。|  
|InterchangeTime|string|EDI インターチェンジからのインターチェンジ時刻です。 このメッセージ コンテキスト プロパティは、AS2 のエンコード中にメッセージから読み取られ、AS2 のインターチェンジ アクティビティを報告するために使用されます。|  
|ReceiverID|string|EDI インターチェンジからのインターチェンジ受信者 ID です。 このプロパティは、AS2 のエンコード中にメッセージから読み取られ、AS2 のインターチェンジ アクティビティを報告するために使用されます。|  
|ReceiverQualifier|string|EDI インターチェンジからのインターチェンジ受信者修飾子です。 このプロパティは、AS2 のエンコード中にメッセージから読み取られ、AS2 のインターチェンジ アクティビティを報告するために使用されます。|  
|SenderID|string|EDI インターチェンジからのインターチェンジ送信者 ID です。 このプロパティは、AS2 のエンコード中にメッセージから読み取られ、AS2 のインターチェンジ アクティビティを報告するために使用されます。|  
|SenderQualifier|string|EDI インターチェンジからのインターチェンジ送信者修飾子です。 このプロパティは、AS2 のエンコード中にメッセージから読み取られ、AS2 のインターチェンジ アクティビティを報告するために使用されます。|  
  
## <a name="see-also"></a>参照  
 [開発と BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)