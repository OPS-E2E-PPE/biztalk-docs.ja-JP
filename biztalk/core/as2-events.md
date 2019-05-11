---
title: AS2 のイベント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9de140d-8961-4c19-a2e5-14631016541f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08b37ca35d0b91455234035b8611abae6dc2af1d
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530637"
---
# <a name="as2-events"></a>AS2 のイベント
次の表では、イベント メッセージの AS2 処理中にイベント ログに送信される可能性を一覧表示します。  
  
> [!NOTE]
>  次の表に示す AS2 エラーの詳細については、次を参照してください。 [EDI および AS2 のイベント](../core/edi-and-as2-events.md)します。  
  
|エラー コード|条件|  
|----------------|---------------|  
|AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError|AS2 デコーダは、MDN の生成に必要な Disposition-Notification-Options HTTP ヘッダーを見つけられませんでした。|  
|SynchronousMdnRequestedOnOneWayReceivePortError|構成エラー。  同期 MDN が一方向の HTTP の要求は受信ポートです。|  
|SynchronousMdnRequestedOnOneWaySendPortError|構成エラー。  一方向の HTTP 送信ポートで同期 MDN が要求されました。|  
|EncryptionCertNotConfiguredError|AS2 パーティの暗号化証明書が構成されていません。  AS2-から。{0} AS2 にします。 {1}|  
|AS2DecoderPartySigningConfigurationError|構成エラー。  メッセージの署名と、予期される値と一致しません。  送信元パートナーに連絡し、署名の使用を確認します。  AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"|  
|AS2DecoderExceptionEncounteredDuringProcessing|AS2 デコーダーでは、処理中に例外が発生しました。  メッセージと例外の詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"MessageType:"{3}"例外:"{4}"|  
|AS2DecoderMdnMicFailureDuringProcessing|AS2 デコーダーで、MDN に返された MIC 値の検証に処理できませんでした。  MDN メッセージの詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"|  
|AS2DecoderMdnSigningMismatchFailureDuringProcessing|AS2 デコーダー処理は失敗しました、MDN の署名要求が一致しないためです。  MDN メッセージの詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"|  
|AS2DecoderMdnProcessingFailureReturned|AS2 デコーダー、MDN が AS2 メッセージを示すため、処理されているエラー処理に失敗しました。  MDN メッセージの詳細は次のとおりです。AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"OriginalMessageID:"{3}"|  
|AS2InvalidQuotedStringHeaderError|無効な引用符で囲まれた HTTP ヘッダーが発生しました。  詳細は次のとおりです。ヘッダー名:"{0}"ヘッダーの値:"{1}"|  
|AS2MicDataStoreDuplicateMicError|エラー-Mic エントリは既に存在します。|  
|AS2StreamingNonSeekableStreamError|これは、シーク可能ではないストリームです。|  
|AS2StreamingSetLengthError|このストリームの長さを設定することはできません。|  
|AS2StreamingWriteToReadonlyStreamError|これは、読み取り専用ストリームです。|  
|AS2StreamingMethodNotImplementedError|メソッドまたは操作が実装されていません。|  
|BtsMimeExceptionEncounteredDuringMessageDecoding|AS2 メッセージをデコードしようとしています。 BTS MIME エラーが発生しました。  AS2-から: {0}、AS2-を: {1}、MessageId:{2}エラー。 {3}|  
|AS2DecoderPartyEncryptionConfigurationError|構成エラー。  メッセージの暗号化は、予期される値と一致しません。  送信元パートナーに連絡し、暗号化の使用を確認します。  AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"|  
|AS2DecoderPartySignatureError|構成エラー。  メッセージの署名は、このパーティ用に構成された署名と一致しません。  送信元パートナーに連絡し、使用する証明書を確認します。  AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}"|  
|InvalidAgreementAS2FromName|この AS2 インターチェンジのパーティには、AS2-From の値が含まれている必要があります。|  
|InvalidAgreementAS2ToName|この AS2 インターチェンジのパーティが AS2 の値を含める必要があります-にします。|  
|UnsupportedAS2HashAlgorithmError|AS2 メッセージに指定されたハッシュ アルゴリズムがサポートされていません。|  
|UnableToLocateAS2PartyError|できません。 パーティにアクセス修飾子を使用して:{0}パーティ:{1}します。  エラー: {2}|  
|UnableToLocateAS2PartyByPartyNameError|アクセスできません。 パーティを使用してパーティ:{0}します。|  
|UnableToLocateAS2PartyBySendPortNameError|パーティにアクセスできません。 を使用してポートを送信します。{0}  エラー:{1}します。|  
|InvalidAS2FromNameConfiguredError|無効な AS2、パーティ用に構成された名前から。{0}   値: {1}|  
|InvalidAS2ToNameConfiguredError|無効な AS2-名前のパーティ用に構成します。{0}   値: {1}|  
|InvalidAS2FromNameHeaderReceivedError|無効な AS2 のヘッダーを受信しました。  値: {0}|  
|InvalidAS2ToNameHeaderReceivedError|無効な AS2 のヘッダーを受信しました。  値: {0}|  
|MissingAS2FromHeaderError|AS2 が含まれていない AS2 メッセージを受信-ヘッダーから。|  
|MissingAS2ToHeaderError|AS2 が含まれていない AS2 メッセージを受信-ヘッダー。|  
|InvalidDispositionNotificationOptionToError|ディス ポジション-通知-オプションの値:"{0}"が無効です。  {1}|  
|InvalidReceiptDeliveryOptionError|Receipt-delivery-option の値:"{0}"が無効です。  {1}|  
|InvalidOrMissingASN1DataLengthHeader|無効か見つかりません ASN.1 データ長フィールドの圧縮解除処理中に発生します。|  
|InvalidOrMissingASN1TrailingBytes|無効な末尾に ASN.1 CMS 圧縮構造のバイト圧縮解除処理中に。|  
|InvalidASN1CompressedStructureEncountered|無効な ASN.1 圧縮構造の圧縮解除処理中に発生しました。|  
|InvalidOrMissingDataHeaderEncountered|無効か見つかりません ASN.1 圧縮ヘッダー圧縮解除処理中に発生します。|  
|InvalidOptionalZLibFieldEncountered|無効な ASN.1 ZLib 圧縮フィールドが圧縮解除処理中に発生します。|  
|InvalidOrMissingDataOIDEncountered|無効な ASN.1 データ oid OID が見つかりません圧縮解除処理中に発生します。|  
|InvalidOrMissingZLibOIDEncountered|無効な ASN.1 ZLib oid OID が見つかりません圧縮解除処理中に発生します。|  
|InvalidOrMissingCompressedDataOIDEncountered|無効な ASN.1 圧縮データ oid OID が見つかりません圧縮解除処理中に発生します。|  
|InvalidAdler32ChecksumInCompressedMessageError|無効な Adler32 チェックサムが発生しました。|  
|UnsupportedOctetStringLengthEncountered|サポートされていないオクテット文字列長が発生しました。  サポートされているオクテットの最大長は 4 です。|  
|DecompressionFailedError|圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。  エラー: {0}|  
|DecryptionFailedError|AS2 メッセージの解読中にエラーが発生しました。|  
|IntegrityCheckFailedError|AS2 メッセージを検証するときにエラーが発生しました。  使用する証明書がないタイムアウトまたは失効を確認してください。|  
|EncryptionCertificateHasBeenRevokedError|メッセージの暗号化に使用する証明書は失効しています。 証明書の拇印: {0}|  
|DecryptionCertificateHasBeenRevokedError|メッセージの解読に使用する証明書が失効しています。 証明書の拇印: {0}|  
|SigningCertificateHasBeenRevokedError|メッセージの署名に使用する証明書は失効しています。 証明書の拇印: {0}|  
|SignatureCertificateHasBeenRevokedError|メッセージの署名に使用する証明書は失効しています。 証明書の拇印: {0}|  
|CertificateMissingError|メッセージの署名に使用される証明書を、ローカルの証明書ストアに配置できません。 証明書の拇印: {0}|  
|EmptyContentOnAS2MessageEncountered|空の AS2 メッセージを受信しました。  メッセージは中断されます。|  
|AS2FromMatchesAS2ToError|AS2 の値から、AS2 と一致-の値にします。|  
|GenericEdiIntException|EdiInt 例外が発生しました。|  
|BtsMimeExceptionEncounteredDuringMessageEncoding|しようとすると、メッセージのエンコードに BTS MIME エラーが発生しました。  エラー: {0}HResult:{1}|  
|BtsMimeGeneralExceptionEncounteredDuringMessageEncoding|しようとすると、メッセージのエンコードに BTS MIME エラーが発生しました。  エラー: {0}|  
|AS2StatusReportingExceptionEncountered|AS2 状態レポートを生成中にエラーが発生しました。  エラー: {0}|