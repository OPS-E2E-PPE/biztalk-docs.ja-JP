---
title: "AS2 のイベント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9de140d-8961-4c19-a2e5-14631016541f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 824fda0d49ddfd9c5d6f6c12a379568775b8d160
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="as2-events"></a>AS2 のイベント
次の表に、AS2 処理時にイベント ログに送信される可能性のあるイベント メッセージの一覧を示します。  
  
> [!NOTE]
>  次の表に示す AS2 エラーの詳細については、次を参照してください。 [EDI および AS2 のイベント](../core/edi-and-as2-events.md)です。  
  
|エラー コード|条件|  
|----------------|---------------|  
|AS2DecoderMissingDispositionNotificationOptionsHTTPHeaderError|AS2 デコーダは、MDN の生成に必要な Disposition-Notification-Options HTTP ヘッダーを見つけられませんでした。|  
|SynchronousMdnRequestedOnOneWayReceivePortError|構成エラー。  一方向の HTTP 受信ポートで同期 MDN が要求されました。|  
|SynchronousMdnRequestedOnOneWaySendPortError|構成エラー。  一方向の HTTP 送信ポートで同期 MDN が要求されました。|  
|EncryptionCertNotConfiguredError|AS2 パーティに暗号化証明書が構成されていません。  AS2-から: {0} AS2-を: {1}|  
|AS2DecoderPartySigningConfigurationError|構成エラー。  メッセージの署名が予期された値と一致しません。  送信元パートナーに問い合わせて、使用された署名を確認してください。  AS2-から:"{0}"AS2-を:"\ "MessageID:"\ {2 \}"|  
|AS2DecoderExceptionEncounteredDuringProcessing|AS2 デコーダで、処理中に例外が発生しました。  メッセージと例外の詳細については次のようには: AS2-から:"{0}"AS2-を:「\ 」MessageID:「\ {2 \}」MessageType:「{3}」例外:「\ {4\}」|  
|AS2DecoderMdnMicFailureDuringProcessing|AS2 デコーダで、MDN に返された MIC 値の検証中に処理が失敗しました。  MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:「\ 」MessageID:「\ {2 \}」OriginalMessageID:「\ {3\}」|  
|AS2DecoderMdnSigningMismatchFailureDuringProcessing|MDN の署名が要求と一致しなかったため、AS2 デコーダの処理は失敗しました。  MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:「\ 」MessageID:「\ {2 \}」OriginalMessageID:「\ {3\}」|  
|AS2DecoderMdnProcessingFailureReturned|AS2 メッセージを処理できなかったことが MDN によって示されたため、AS2 デコーダの処理は失敗しました。  MDN メッセージの詳細は次のとおり: AS2-から:"{0}"AS2-を:「\ 」MessageID:「\ {2 \}」OriginalMessageID:「\ {3\}」|  
|AS2InvalidQuotedStringHeaderError|引用符で囲まれた無効な HTTP ヘッダーが検出されました。  詳細については次のようにしますヘッダー名:"{0}"ヘッダーの値:"{1}"。|  
|AS2MicDataStoreDuplicateMicError|エラー - Mic エントリは既に存在します。|  
|AS2StreamingNonSeekableStreamError|これは、シーク可能ではないストリームです。|  
|AS2StreamingSetLengthError|このストリームの長さを設定できません。|  
|AS2StreamingWriteToReadonlyStreamError|これは、読み取り専用ストリームです。|  
|AS2StreamingMethodNotImplementedError|メソッドまたは操作が実装されていません。|  
|BtsMimeExceptionEncounteredDuringMessageDecoding|AS2 メッセージをデコードしようとしたときに BTS MIME エラーが発生しました。  AS2-から: {0}、AS2-を: {1}、MessageId: {2}、エラー: {3}|  
|AS2DecoderPartyEncryptionConfigurationError|構成エラー。  メッセージの暗号化が予期された値と一致しません。  送信元パートナーに問い合わせて、使用された暗号化を確認してください。  AS2-から:"{0}"AS2-を:"\ "MessageID:"\ {2 \}"|  
|AS2DecoderPartySignatureError|構成エラー。  メッセージの署名がこのパーティ用に構成された署名と一致しません。  送信元パートナーに問い合わせて、使用された証明書を確認してください。  AS2-から:"{0}"AS2-を:"\ "MessageID:"\ {2 \}"|  
|InvalidAgreementAS2FromName|この AS2 インターチェンジのパーティには、AS2-From の値が含まれている必要があります。|  
|InvalidAgreementAS2ToName|この AS2 インターチェンジのパーティには、AS2-To の値が含まれている必要があります。|  
|UnsupportedAS2HashAlgorithmError|AS2 メッセージに指定されたハッシュ アルゴリズムがサポートされていません。|  
|UnableToLocateAS2PartyError|できません。 パーティにアクセス修飾子を使用して: {0} パーティ: {1} です。  エラー: {2}|  
|UnableToLocateAS2PartyByPartyNameError|パーティ {0} を使用してパーティにアクセスできません。|  
|UnableToLocateAS2PartyBySendPortNameError|パーティにアクセスできません。 を使用して送信ポート: {0} エラー: {1} です。|  
|InvalidAS2FromNameConfiguredError|無効な AS2-パーティ用に構成された名前から: {0} 値: {1}|  
|InvalidAS2ToNameConfiguredError|無効な AS2-名前のパーティに構成する: {0} 値: {1}|  
|InvalidAS2FromNameHeaderReceivedError|無効な AS2-From ヘッダーを受信しました。  値: {0}|  
|InvalidAS2ToNameHeaderReceivedError|無効な AS2-To ヘッダーを受信しました。  値: {0}|  
|MissingAS2FromHeaderError|AS2-From ヘッダーが含まれていない AS2 メッセージを受信しました。|  
|MissingAS2ToHeaderError|AS2-To ヘッダーが含まれていない AS2 メッセージを受信しました。|  
|InvalidDispositionNotificationOptionToError|廃棄-通知-オプションの値:"{0}"が無効です。  {1}|  
|InvalidReceiptDeliveryOptionError|Receipt-delivery-option の値:"{0}"が無効です。  {1}|  
|InvalidOrMissingASN1DataLengthHeader|圧縮解除処理中に無効な ASN.1 データ長フィールドが検出されたか、ASN.1 データ長フィールドが見つかりませんでした。|  
|InvalidOrMissingASN1TrailingBytes|圧縮解除処理中に ASN.1 CMS 圧縮構造の末尾に無効なバイトが検出されたか、バイトが見つかりませんでした。|  
|InvalidASN1CompressedStructureEncountered|圧縮解除処理中に無効な ASN.1 圧縮構造が検出されました。|  
|InvalidOrMissingDataHeaderEncountered|圧縮解除処理中に無効な ASN.1 圧縮ヘッダーが検出されたか、ASN.1 圧縮ヘッダーが見つかりませんでした。|  
|InvalidOptionalZLibFieldEncountered|圧縮解除処理中に無効な ASN.1 ZLib 圧縮フィールドが検出されました。|  
|InvalidOrMissingDataOIDEncountered|圧縮解除処理中に無効な ASN.1 データ OID が検出されたか、ASN.1 データ OID が見つかりませんでした。|  
|InvalidOrMissingZLibOIDEncountered|圧縮解除処理中に無効な ASN.1 ZLib データ OID が検出されたか、ASN.1 ZLib データ OID が見つかりませんでした。|  
|InvalidOrMissingCompressedDataOIDEncountered|圧縮解除処理中に無効な ASN.1 圧縮データ OID が検出されたか、ASN.1 圧縮データ OID が見つかりませんでした。|  
|InvalidAdler32ChecksumInCompressedMessageError|無効な Adler32 チェックサムが検出されました。|  
|UnsupportedOctetStringLengthEncountered|オクテット文字列がサポートされていない長さになりました。  サポートされているオクテットの最大長は 4 です。|  
|DecompressionFailedError|圧縮された AS2 メッセージの処理中に圧縮解除が失敗しました。  エラー: {0}|  
|DecryptionFailedError|AS2 メッセージの解読中にエラーが発生しました。|  
|IntegrityCheckFailedError|AS2 メッセージの検証中にエラーが発生しました。  使用した証明書の有効期限が切れていないこと、および失効していないことを確認してください。|  
|EncryptionCertificateHasBeenRevokedError|メッセージの暗号化に使用する証明書は失効しています。 証明書の拇印: {0}|  
|DecryptionCertificateHasBeenRevokedError|メッセージの解読に使用する証明書は失効しています。 証明書の拇印: {0}|  
|SigningCertificateHasBeenRevokedError|メッセージの署名に使用する証明書は失効しています。 証明書の拇印: {0}|  
|SignatureCertificateHasBeenRevokedError|メッセージの署名に使用する証明書は失効しています。 証明書の拇印: {0}|  
|CertificateMissingError|メッセージの署名に使用される証明書を、ローカルの証明書ストアに配置できません。 証明書の拇印: {0}|  
|EmptyContentOnAS2MessageEncountered|空の AS2 メッセージを受信しました。  メッセージは中断されます。|  
|AS2FromMatchesAS2ToError|AS2-From の値が AS2-To の値と同じです。|  
|GenericEdiIntException|EdiInt 例外が発生しました。|  
|BtsMimeExceptionEncounteredDuringMessageEncoding|メッセージをエンコードしようとしたときに BTS MIME エラーが発生しました。  エラー: {0}、HResult: \ |  
|BtsMimeGeneralExceptionEncounteredDuringMessageEncoding|メッセージをエンコードしようとしたときに BTS MIME エラーが発生しました。  エラー: {0}|  
|AS2StatusReportingExceptionEncountered|AS2 状態レポートを生成しようとしたときにエラーが発生しました。  エラー: {0}|