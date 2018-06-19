---
title: EDI、AS2 メッセージの追跡を BAM アクティビティが作成された |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a10ab846-0fbb-46f5-920e-cb2b5be75814
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7da7ac08a8f26e21b2c648670730db136392471
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008899"
---
# <a name="bam-activities-created-to-track-edi-as2-messages"></a>EDI、AS2 メッセージの追跡に作成された BAM アクティビティ
BizTalk Server には、EDI および AS2 状態レポート用に作成された BAM アクティビティが含まれています。 これらのアクティビティによって、状態レポートに表示するデータが決定されます。 このトピックでは、BAM アクティビティとそこで定義されるフィールド、および BAM アクティビティの特定のフィールドで定義される列挙値について説明します。  
  
 カスタム BAM アクティビティを作成して、カスタム状態レポートを作成することができます。 カスタム アクティビティは、標準のアクティビティの 1 つを基にすることができます。 また、BizTalkDTADb データベースの EdiMessageContent テーブルにクエリを実行して、カスタム状態レポートからメッセージの内容を表示することもできます。 詳細については、後述の「EdiMessageContent テーブルへのクエリの実行」を参照してください。  
  
> [!CAUTION]
>  BAM アクティビティを変更すると、アクティビティに依存する BizTalk EDI ランタイム、および AS2 ランタイムの処理に影響が出る場合があります。  
  
## <a name="bam-activities-used-in-status-reporting"></a>状態レポートで使用される BAM アクティビティ  
 EDI/AS2 メッセージの追跡用に作成された BAM アクティビティは、ビューとして BAMPrimaryImport データベースに含まれています。 次の表に、BAM アクティビティとその中の列を示します。  
  
|BAM アクティビティ|フィールド|  
|------------------|------------|  
|AS2InterchangeActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> MessageID<br /><br /> AS2From<br /><br /> AS2To<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|AS2MdnActivity|RecordID<br /><br /> ActivityID<br /><br /> AS2PartyRole<br /><br /> AS2From<br /><br /> AS2To<br /><br /> MessageID<br /><br /> MdnDateTime<br /><br /> MdnDispositionType<br /><br /> DispositionModifierExtType<br /><br /> DispositionModifierExtDescription<br /><br /> MdnEncryptionType<br /><br /> MdnSignatureType<br /><br /> MdnPayloadContentKey<br /><br /> MdnWireContentKey<br /><br /> MdnMicValue<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|AS2MessageActivity|RecordID<br /><br /> ActivityID<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> AS2PartyRole<br /><br /> AS2From<br /><br /> AS2To<br /><br /> MessageID<br /><br /> MessageDateTime<br /><br /> BTSInterchangeID<br /><br /> BTSMessageID<br /><br /> MdnProcessingStatus<br /><br /> MessageEncryptionType<br /><br /> IsMdnExpected<br /><br /> MicAlgorithmType<br /><br /> MessageSignatureType<br /><br /> MessagePayloadContentKey<br /><br /> MessageWireContentKey<br /><br /> MessageMicValue<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> IsAS2MessageDuplicate<br /><br /> DaysToCheckDuplicate<br /><br /> FileName<br /><br /> TrackingActivityID<br /><br /> LastModified|  
|BatchingActivity|RecordID<br /><br /> ActivityID<br /><br /> BatchStatus<br /><br /> DestinationPartyID<br /><br /> DestinationPartyName<br /><br /> ActivationTime<br /><br /> BatchOccurrenceCount<br /><br /> EdiEncodingType<br /><br /> BatchType<br /><br /> TargetedBatchCount<br /><br /> ScheduledReleaseTime<br /><br /> BatchElementCount<br /><br /> RejectedBatchElementCount<br /><br /> BatchSize<br /><br /> LastBatchAction<br /><br /> CreationTime<br /><br /> ReleaseTime<br /><br /> BatchReleaseType<br /><br /> BatchServiceID<br /><br /> ActivationMessageID<br /><br /> ReleaseMessageID<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> BatchCorrelationID<br /><br /> BatchName<br /><br /> BatchID<br /><br /> LastModified|  
|BatchInterchangeActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> BatchCorrelationID<br /><br /> LastModified|  
|BusinessMessageJournal|RecordID<br /><br /> ActivityID<br /><br /> MessageTrackingID<br /><br /> ActionType<br /><br /> ContainerActivityID<br /><br /> ContainerType<br /><br /> BTSInterchangeID<br /><br /> BTSMessageId<br /><br /> BTSServiceInstanceId<br /><br /> BTSHostName<br /><br /> RoutedToPartyName<br /><br /> LinkedMessageTrackingID<br /><br /> TimeCreated<br /><br /> LastModified|  
|FunctionalAckActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeActivityID<br /><br /> GroupControlNo<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> AckProcessingStatus<br /><br /> AckStatusCode<br /><br /> DeliveredTSCount<br /><br /> AcceptedTSCount<br /><br /> AckIcn<br /><br /> AckIcnDate<br /><br /> AckIcnTime<br /><br /> ErrorCode1<br /><br /> ErrorCode2<br /><br /> ErrorCode3<br /><br /> ErrorCode4<br /><br /> ErrorCode5<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|FunctionalGroupInfo|RecordID<br /><br /> ActivityID<br /><br /> InterchangeActivityID<br /><br /> GroupControlNo<br /><br /> FunctionalIDCode<br /><br /> TSCount<br /><br /> LastModified|  
|InterchangeAckActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> AckProcessingStatus<br /><br /> AckStatusCode<br /><br /> AckIcn<br /><br /> AckIcnDate<br /><br /> AckIcnTime<br /><br /> AckNoteCode1<br /><br /> AckNoteCode2<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> AckCorrelationId<br /><br /> LastModified|  
|InterchangeStatusActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> AckStatusCode<br /><br /> GroupCount<br /><br /> EdiMessageType<br /><br /> PortID<br /><br /> IsInterchangeAckExpected<br /><br /> IsFunctionalAckExpected<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> AckCorrelationId<br /><br /> TsCorrelationId<br /><br /> LastModified|  
|ResendJournalActivity|RecordID<br /><br /> ActivityID<br /><br /> TrackingActivityId<br /><br /> ResendIndex<br /><br /> ResendStatus<br /><br /> BTSInterchangeID<br /><br /> LastModified|  
|ResendTrackingActivity|RecordID<br /><br /> ActivityID<br /><br /> CorrelationId<br /><br /> AdapterPrefix<br /><br /> ResendCount<br /><br /> MaxResendCount<br /><br /> ResendInterval<br /><br /> MaxRetryCount<br /><br /> RetryInterval<br /><br /> MessageContentID<br /><br /> ResendTimeout<br /><br /> RetryTimeout<br /><br /> BTSInterchangeID<br /><br /> LastModified|  
|TransactionSetActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> ApplicationSender<br /><br /> ApplicationReceiver<br /><br /> GroupDateTime<br /><br /> GroupControlNo<br /><br /> TransactionSetId<br /><br /> DocType<br /><br /> TransactionSetControlNo<br /><br /> AckStatusCode<br /><br /> BatchProcessing<br /><br /> ProcessingDateTime<br /><br /> GroupOrdinal<br /><br /> TransactionSetOrdinal<br /><br /> MessageContentKey<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> TsCorrelationId<br /><br /> LastModified|  
  
## <a name="data-enumerations-in-the-bamprimaryimport-database"></a>BAMPrimaryImport データベースのデータ列挙  
 一部の EDI データおよび AS2 データは、BAMPrimaryImport データベースのテーブルに列挙として保存されます。 状態レポートに表示した場合は、データがテキスト表示されます。 これらの値は次のとおりです。  
  
|フィールド|列挙値|  
|-----------|-----------------|  
|AckProcessingStatus|NotExpected = -1<br /><br /> Expected = 0<br /><br /> Received = 1<br /><br /> 送信 = 2<br /><br /> Generated = 3|  
|AS2PartyRole|すべて 0 を =<br /><br /> Receiver = 1<br /><br /> Sender = 2|  
|BatchAction|Creation = 0<br /><br /> Activation = 1<br /><br /> ElementReference = 2<br /><br /> Release = 3<br /><br /> Override = 4<br /><br /> Termination = 5<br /><br /> Sent = 6<br /><br /> ToBeReleased = 7|  
|BatchStatus|All = -1<br /><br /> Defined = 0<br /><br /> Active<br /><br /> Released<br /><br /> [完了]|  
|BatchType|ScheduleBased = 0<br /><br /> MessagesCountInGroup = 1<br /><br /> MessagesCountIn<br />インターチェンジ 2 を =<br /><br /> CharacterCount = 3<br /><br /> ExternalTrigger = 4|  
|Direction|すべて 0 を =<br /><br /> Receive = 1<br /><br /> Send = 2|  
|DisplayAckStatusCode|すべて = 100<br /><br /> Accepted = 0<br /><br /> PartiallyAccepted = 1<br /><br /> Rejected = -1<br /><br /> AckExpected = 500<br /><br /> AckNotExpected = 600|  
|DispositionModifierExt<br />Description|Not Valued = 1<br /><br /> Authentication Failed = 2<br /><br /> Decryption Failed = 3<br /><br /> メッセージが不足しています<br />セキュリティ 4 を =<br /><br /> Integrity Check Failed = 5<br /><br /> 予期しない処理 <br />エラー 6 を =|  
|DispositionModifierExt<br />型|Not Valued = 1<br /><br /> Error = 2<br /><br /> Warning = 3|  
|EdiMessageType|X12,<br /><br /> Edifact,<br /><br /> Unknown|  
|IsMdnExpected|MDN is not expected = 0<br /><br /> MDN is expected = 1|  
|MdnDispositionType|Processed = 1<br /><br /> Failed = 2|  
|MdnProcessingStatus|すべて 0 を =<br /><br /> Processed = 1<br /><br /> Failed = 2<br /><br /> 予想 3 を =<br /><br /> Not Expected = 4|  
|MessageEncryptionType|Message is not encrypted = 0<br /><br /> Message is encrypted = 1|  
|MessageSignatureType|Message is not signed = 0<br /><br /> Message is signed = 1|  
|MicAlgorithmType|Unknown type = -1<br /><br /> SHA1 = 1<br /><br /> MD5 = 2|  
  
## <a name="businessmessagejournal-bam-activity"></a>BusinessMessageJournal BAM アクティビティ  
 BusinessMessageJournal BAM アクティビティにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、トランザクション セットを持つ受信 EDI インターチェンジを、同じトランザクション セットを持つ送信バッチ インターチェンジと関連付けることができます。 詳細については、次を参照してください。[送信バッチで受信トランザクション セットを相互に関連付ける](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)です。  
  
##  <a name="BKMK_Query"></a>EdiMessageContent テーブルを照会します。  
 BizTalkDTADb データベースの EdiMessageContent テーブルには、メッセージのペイロードがメッセージのメタデータと一緒に保存されています。 カスタム状態レポートで、EdiMessageContent テーブルに対してクエリを実行して、メッセージの内容を表示することができます。 これは、製品の状態レポートの一部でメッセージの内容を表示できるのに似ています。たとえば、AS2 メッセージおよび関連する MDN 状態レポートで、メッセージのワイヤ形式を表示できます。  
  
 EdiMessageContent テーブルで ContentKey 列に対応する BAM アクティビティのキー列を使用して、カスタム BAM アクティビティから EdiMessageContent テーブルにリンクできます。 たとえば、AS2MessageActivity BAM アクティビティから EdiMessageContent テーブルにリンクするには、MessagePayloadContentKey 列か MessageWireContentKey 列のいずれかを使用して ContentKey 列にリンクします。  
  
|テーブル|列|  
|-----------|-------------|  
|EdiMessageContent<br /><br /> (BizTalkDTADb データベース内)|ContentKey<br /><br /> MessageFormat<br /><br /> ContentType<br /><br /> Charset<br /><br /> TimeCreated<br /><br /> TimeInserted<br /><br /> IsOrphaned<br /><br /> ContentBinary|  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 状態レポートのデータを格納する方法](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)   
 [受信トランザクション セットと送信パッチの関連付け](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)