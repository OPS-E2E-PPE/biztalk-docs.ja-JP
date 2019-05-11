---
title: AS2 コンテキスト プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d63104-f31e-4ed2-b294-ba3ea8a39ae6
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a2685a9547d71d3e6fad4b2f81c0c9d2d7d35b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358943"
---
# <a name="as2-context-properties"></a>AS2 のコンテキスト プロパティ
5 つの種類のコンテキスト プロパティは、BizTalk Server の AS2 メッセージに適用されます。  

-   EdiIntProperties.xsd スキーマ内のコンテキスト プロパティ  

-   BizTalk Server に内部のコンテキスト プロパティ  

-   BizTalk mime 内部のコンテキスト プロパティ  

-   AS2 内部のコンテキスト プロパティ  

-   AS2 状態レポート内部のコンテキスト プロパティ  

## <a name="context-properties-in-the-ediintpropertiesxsd-schema"></a>EdiIntProperties.xsd スキーマ内のコンテキスト プロパティ  
 メッセージのルーティングなどの操作で使用することができます、EDI/INT グローバル プロパティ スキーマのメッセージ コンテキスト プロパティがパブリックに公開します。 これらのコンテキスト プロパティが ediintproperties.xsd で定義されている、`Microsoft.BizTalk.Edi.BaseArtifacts`アセンブリ。 プロパティの名前空間は`http://schemas.microsoft.com/BizTalk/2006/as2-properties`します。 これらのメッセージ コンテキスト プロパティとして利用可能な場合は、昇格される`EdiIntAS.<Property Name>`で、**フィルター**のページ、**送信ポートのプロパティ** ダイアログ ボックス。  

|名前|型|説明|  
|----------|----------|-----------------|  
|AS2From|string|AS2 が含まれています-送信者の名前を表すから AS2 ヘッダー値。|  
|AS2PayloadContentType|string|ペイロード メッセージのコンテンツの種類が含まれています。|  
|AS2To|string|AS2 が含まれています-受信者の名前を表すに AS2 ヘッダー値。|  
|DispositionMode|string|MDN 配置モード値が含まれています。<br /><br /> このコンテキスト プロパティと DispositionType コンテキスト プロパティの両方は、MDN を生成するために昇格する必要があります。|  
|DispositionType|string|MDN のディス ポジション タイプ値が含まれています。<br /><br /> このコンテキスト プロパティと DispositionMode コンテキスト プロパティの両方は、MDN を生成するために昇格する必要があります。|  
|IsAS2AsynchronousMdn|boolean|メッセージが非同期の MDN であることを示します。|  
|IsAS2FailedMessage|boolean|受信 AS2 メッセージの AS2 での処理を中断するペイロード メッセージの原因が失敗したことを示します。|  
|IsAS2Http200OKResponse|boolean|HTTP 200 OK の応答メッセージとして生成されるメッセージに設定します。 AS2 メッセージまたは MDN を非同期に送信されるときに、MDN が生成されないときに使用されます。|  
|IsAS2MdnResponseMessage|boolean|メッセージが MDN 応答メッセージであることを示します。|  
|IsAS2MessageDuplicate|boolean|受信 AS2 メッセージが受信されていたことを示します。|  
|IsAS2MessageCompressed|boolean|受信 AS2 メッセージが圧縮されたことを示します。|  
|IsAS2MessageEncrypted|boolean|受信 AS2 メッセージが暗号化されたことを示します。|  
|IsAS2MessageSigned|boolean|受信 AS2 メッセージが署名されたことを示します。|  
|IsAS2PayloadMessage|boolean|このメッセージがデコードされた AS2 メッセージの内容を含むペイロードとして処理する必要があることを示します。|  
|MDNAsyncURI|string|含まれています、 **- Receipt-delivery-option**非同期 MDN 応答メッセージの送信に使用される値。|  
|メッセージ Id|string|AS2 メッセージのヘッダーに含まれている AS2 メッセージ ID が含まれています。|  
|OriginalMessageId|string|元の AS2 メッセージのメッセージ ID が含まれています。 このコンテキスト プロパティは、MDN メッセージの一部であるし、AS2 メッセージとその MDN 応答を関連付けるために使用されます。|  
|PreservedFileName|string|メッセージの元のファイル名が含まれています。 このコンテキスト プロパティは、受信メッセージに Content-disposition MIME ヘッダーの一部としてファイル名の情報が含まれている場合にのみ設定されます。|  
|SendMDN|boolean|MDN メッセージを生成する場合は true に設定します。|  

## <a name="context-properties-internal-to-biztalk-server"></a>BizTalk Server に内部のコンテキスト プロパティ  
 次のメッセージ コンテキスト プロパティはパブリックに公開されません、ため、メッセージのルーティングなどの操作に使用することはできません。 ただし、一時停止、追跡対象のメッセージで表示できます。 これらのコンテキスト プロパティの名前空間は`http://schemas.microsoft.com/BizTalk/2006/system-properties`します。  


|                  名前                  |  型   |                                                                                            説明                                                                                             |
|----------------------------------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IgnoreSslCertificateNameMismatchErrors | boolean |                  指示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]処理中に SSL 名の不一致エラーを無視する HTTP 処理します。                  |
|               KeepAlive                | ブール値 |                                                                    HTTP Keep Alive 機能の動作を制御します。                                                                     |
|        TreatEPMSuspendAsSuccess        | boolean | 指示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]双方向の http 処理は受信接続時に成功したメッセージとして保留メッセージを処理します。 |
|           IsSolicitResponse            | boolean |                      によって設定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]し、メッセージが送信請求-応答メッセージであることを示します。                       |

## <a name="context-properties-internal-to-biztalk-mime"></a>BizTalk MIME 内部のコンテキスト プロパティ  
 次のメッセージ コンテキスト プロパティはパブリックに公開されません、ため、メッセージのルーティングなどの操作に使用することはできません。 ただし、一時停止、追跡対象のメッセージで表示できます。 これらのコンテキスト プロパティの名前空間は`http://schemas.microsoft.com/BizTalk/2006/system-properties`します。  


|                  名前                   |  型   |                                                                                     説明                                                                                     |
|-----------------------------------------|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|            IsMultipartReport            | boolean |                 により、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MIME エンコーダーがマルチパート/レポート メッセージを生成します。                  |
| SuppressMimeVersionFromMultiPartMessage | boolean | により、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MIME エンコーダーがマルチパート メッセージの各部分において MIME Version ヘッダーを抑制します。 |

## <a name="context-properties-internal-to-as2"></a>AS2 内部のコンテキスト プロパティ  
 次のメッセージ コンテキスト プロパティはパブリックに公開されません、ため、メッセージのルーティングなどの操作に使用することはできません。 ただし、一時停止、追跡対象のメッセージで表示できます。 これらのコンテキスト プロパティの名前空間は`http://schemas.microsoft.com/BizTalk/2006/as2-properties`します。  

|名前|型|説明|  
|----------|----------|-----------------|  
|MicHashAlgorithm|string|MIC ハッシュ値を計算するときに使用するハッシュ アルゴリズムが含まれています。|  
|ReceivedContentMic|string|計算された MIC ハッシュ値が含まれています。|  

## <a name="context-properties-internal-to-as2-status-reporting"></a>AS2 内部のコンテキスト プロパティの状態レポート  
 次のメッセージ コンテキスト プロパティはパブリックに公開されません、ため、メッセージのルーティングなどの操作に使用することはできません。 ただし、一時停止、追跡対象のメッセージで表示できます。 これらのコンテキスト プロパティの名前空間は`http://schemas.microsoft.com/BizTalk/2006/edi-properties`します。  

|名前|型|説明|  
|----------|----------|-----------------|  
|InterchangeControlNo|string|EDI インターチェンジのインターチェンジ制御番号。 このプロパティは、AS2 のエンコード中にメッセージから読み取らし、AS2 のインターチェンジ アクティビティを報告するために使用します。|  
|InterchangeDate|string|EDI インターチェンジからのインターチェンジ日付。 このプロパティは、AS2 のエンコード中にメッセージから読み取らし、AS2 のインターチェンジ アクティビティを報告するために使用します。|  
|InterchangeTime|string|EDI インターチェンジからのインターチェンジ時刻。 このメッセージ コンテキスト プロパティは、AS2 のエンコード中にメッセージから読み取らし、AS2 のインターチェンジ アクティビティを報告するために使用します。|  
|ReceiverID|string|EDI インターチェンジからのインターチェンジ受信者 ID です。 このプロパティは、AS2 のエンコード中にメッセージから読み取らし、AS2 のインターチェンジ アクティビティを報告するために使用します。|  
|ReceiverQualifier|string|EDI インターチェンジからのインターチェンジ受信者の修飾子。 このプロパティは、AS2 のエンコード中にメッセージから読み取らし、AS2 のインターチェンジ アクティビティを報告するために使用します。|  
|SenderID|string|EDI インターチェンジからのインターチェンジの送信者 ID です。 このプロパティは、AS2 のエンコード中にメッセージから読み取らし、AS2 のインターチェンジ アクティビティを報告するために使用します。|  
|SenderQualifier|string|EDI インターチェンジからのインターチェンジ送信者の修飾子。 このプロパティは、AS2 のエンコード中にメッセージから読み取らし、AS2 のインターチェンジ アクティビティを報告するために使用します。|  

## <a name="see-also"></a>参照  
 [BizTalk Server AS2 ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)