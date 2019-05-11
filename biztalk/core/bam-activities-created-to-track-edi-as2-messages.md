---
title: EDI AS2 メッセージの追跡を BAM アクティビティの作成 |Microsoft Docs
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
ms.openlocfilehash: 1a3760513c79cb6fc006c29276b73b8b475e64ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358993"
---
# <a name="bam-activities-created-to-track-edi-as2-messages"></a>EDI AS2 メッセージの追跡に作成された BAM アクティビティ
BizTalk Server には、EDI および AS2 状態レポート用に作成された BAM アクティビティが含まれています。 これらのアクティビティは、状態レポートに表示されるデータを決定します。 このトピックでは、BAM アクティビティと、定義されているフィールドについて説明し、BAM アクティビティの特定のフィールドに対して定義されている列挙値について説明します。  
  
 カスタム状態レポートを作成するには、カスタム BAM アクティビティを作成します。 カスタム アクティビティは、標準活動のいずれかに基づくことができます。 BizTalkDTADb データベースの EdiMessageContent テーブルにクエリを実行して、カスタム状態レポートからのメッセージの内容を表示することもできます。 詳細については、以下の「the EdiMessageContent テーブル クエリを実行する」セクションを参照してください。  
  
> [!CAUTION]
>  BAM アクティビティを変更すると、アクティビティに依存する BizTalk の EDI および AS2 ランタイムの処理が影響する可能性があります。  
  
## <a name="bam-activities-used-in-status-reporting"></a>状態レポートで使用される BAM アクティビティ  
 EDI および AS2 メッセージを追跡するために作成された BAM アクティビティは、BAMPrimaryImport データベースのビューとして含まれています。 次の表は、BAM アクティビティおよびそれらに含まれる列を示します。  
  
|BAM アクティビティ|フィールド|  
|------------------|------------|  
|AS2InterchangeActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> MessageID<br /><br /> AS2From<br /><br /> AS2To<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|AS2MdnActivity|RecordID<br /><br /> ActivityID<br /><br /> AS2PartyRole<br /><br /> AS2From<br /><br /> AS2To<br /><br /> MessageID<br /><br /> MdnDateTime<br /><br /> MdnDispositionType<br /><br /> DispositionModifierExtType<br /><br /> DispositionModifierExtDescription<br /><br /> MdnEncryptionType<br /><br /> MdnSignatureType<br /><br /> MdnPayloadContentKey<br /><br /> MdnWireContentKey<br /><br /> MdnMicValue<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|AS2MessageActivity|RecordID<br /><br /> ActivityID<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> AS2PartyRole<br /><br /> AS2From<br /><br /> AS2To<br /><br /> MessageID<br /><br /> MessageDateTime<br /><br /> BTSInterchangeID<br /><br /> BTSMessageID<br /><br /> MdnProcessingStatus<br /><br /> MessageEncryptionType<br /><br /> IsMdnExpected<br /><br /> MicAlgorithmType<br /><br /> MessageSignatureType<br /><br /> MessagePayloadContentKey<br /><br /> MessageWireContentKey<br /><br /> MessageMicValue<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> IsAS2MessageDuplicate<br /><br /> DaysToCheckDuplicate<br /><br /> FileName<br /><br /> TrackingActivityID<br /><br /> LastModified|  
|BatchingActivity|RecordID<br /><br /> ActivityID<br /><br /> BatchStatus<br /><br /> DestinationPartyID<br /><br /> DestinationPartyName<br /><br /> ActivationTime<br /><br /> BatchOccurrenceCount<br /><br /> EdiEncodingType<br /><br /> BatchType<br /><br /> TargetedBatchCount<br /><br /> ScheduledReleaseTime<br /><br /> BatchElementCount<br /><br /> RejectedBatchElementCount<br /><br /> BatchSize<br /><br /> LastBatchAction<br /><br /> CreationTime<br /><br /> ReleaseTime<br /><br /> BatchReleaseType<br /><br /> BatchServiceID<br /><br /> ActivationMessageID<br /><br /> ReleaseMessageID<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> BatchCorrelationID<br /><br /> BatchName<br /><br /> バッチ Id<br /><br /> LastModified|  
|BatchInterchangeActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> BatchCorrelationID<br /><br /> LastModified|  
|BusinessMessageJournal|RecordID<br /><br /> ActivityID<br /><br /> MessageTrackingID<br /><br /> ActionType<br /><br /> ContainerActivityID<br /><br /> フィルター処理します<br /><br /> BTSInterchangeID<br /><br /> BTSMessageId<br /><br /> BTSServiceInstanceId<br /><br /> BTSHostName<br /><br /> RoutedToPartyName<br /><br /> LinkedMessageTrackingID<br /><br /> TimeCreated<br /><br /> LastModified|  
|FunctionalAckActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeActivityID<br /><br /> GroupControlNo<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> AckProcessingStatus<br /><br /> AckStatusCode<br /><br /> DeliveredTSCount<br /><br /> AcceptedTSCount<br /><br /> AckIcn<br /><br /> AckIcnDate<br /><br /> AckIcnTime<br /><br /> ErrorCode1<br /><br /> ErrorCode2<br /><br /> ErrorCode3<br /><br /> ErrorCode4<br /><br /> ErrorCode5<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> LastModified|  
|FunctionalGroupInfo|RecordID<br /><br /> ActivityID<br /><br /> InterchangeActivityID<br /><br /> GroupControlNo<br /><br /> FunctionalIDCode<br /><br /> TSCount<br /><br /> LastModified|  
|InterchangeAckActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> AckProcessingStatus<br /><br /> AckStatusCode<br /><br /> AckIcn<br /><br /> AckIcnDate<br /><br /> AckIcnTime<br /><br /> AckNoteCode1<br /><br /> AckNoteCode2<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> AckCorrelationId<br /><br /> LastModified|  
|InterchangeStatusActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> AckStatusCode<br /><br /> GroupCount<br /><br /> EdiMessageType<br /><br /> ポート Id<br /><br /> IsInterchangeAckExpected<br /><br /> IsFunctionalAckExpected<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> AckCorrelationId<br /><br /> TsCorrelationId<br /><br /> LastModified|  
|ResendJournalActivity|RecordID<br /><br /> ActivityID<br /><br /> TrackingActivityId<br /><br /> ResendIndex<br /><br /> ResendStatus<br /><br /> BTSInterchangeID<br /><br /> LastModified|  
|ResendTrackingActivity|RecordID<br /><br /> ActivityID<br /><br /> 関連付け Id<br /><br /> AdapterPrefix<br /><br /> ResendCount<br /><br /> MaxResendCount<br /><br /> ResendInterval<br /><br /> MaxRetryCount<br /><br /> RetryInterval<br /><br /> MessageContentID<br /><br /> ResendTimeout<br /><br /> RetryTimeout<br /><br /> BTSInterchangeID<br /><br /> LastModified|  
|TransactionSetActivity|RecordID<br /><br /> ActivityID<br /><br /> InterchangeControlNo<br /><br /> ReceiverID<br /><br /> SenderID<br /><br /> ReceiverQ<br /><br /> SenderQ<br /><br /> InterchangeDateTime<br /><br /> Direction<br /><br /> ReceiverPartyName<br /><br /> SenderPartyName<br /><br /> ApplicationSender<br /><br /> ApplicationReceiver<br /><br /> GroupDateTime<br /><br /> GroupControlNo<br /><br /> TransactionSetId<br /><br /> DocType<br /><br /> TransactionSetControlNo<br /><br /> AckStatusCode<br /><br /> BatchProcessing<br /><br /> ProcessingDateTime<br /><br /> GroupOrdinal<br /><br /> TransactionSetOrdinal<br /><br /> MessageContentKey<br /><br /> TimeCreated<br /><br /> RowFlags<br /><br /> TsCorrelationId<br /><br /> LastModified|  
  
## <a name="data-enumerations-in-the-bamprimaryimport-database"></a>BAMPrimaryImport データベースのデータ列挙  
 一部の EDI および AS2 データは、BAMPrimaryImport データベースのテーブルに列挙として保存されます。 状態レポートに表示される場合は、データがテキストとして表示されます。 これらの値は次のとおりです。  
  
|フィールド|列挙型の値|  
|-----------|-----------------|  
|AckProcessingStatus|NotExpected = -1<br /><br /> 予想 = 0<br /><br /> 受信した = 1<br /><br /> 送信 = 2<br /><br /> 生成された 3 を =|  
|AS2PartyRole|すべて = 0<br /><br /> 受信者 = 1<br /><br /> 送信者 = 2|  
|BatchAction|作成 = 0<br /><br /> アクティブ化 = 1<br /><br /> ElementReference = 2<br /><br /> リリース 3 を =<br /><br /> オーバーライド = 4<br /><br /> 終了 = 5<br /><br /> 送信された 6 を =<br /><br /> ToBeReleased 7 を =|  
|BatchStatus|すべて =-1<br /><br /> 定義 = 0<br /><br /> Active<br /><br /> Released<br /><br /> [完了]|  
|BatchType|ScheduleBased = 0<br /><br /> MessagesCountInGroup = 1<br /><br /> MessagesCountIn<br />インターチェンジ = 2<br /><br /> CharacterCount 3 を =<br /><br /> ExternalTrigger = 4|  
|Direction|すべて = 0<br /><br /> 受信 1 を =<br /><br /> 送信 = 2|  
|DisplayAckStatusCode|すべて 100 を =<br /><br /> 受け入れられる = 0<br /><br /> PartiallyAccepted = 1<br /><br /> 拒否 =-1<br /><br /> AckExpected = 500<br /><br /> AckNotExpected 600|  
|DispositionModifierExt<br />説明|Not Valued = 1<br /><br /> 認証に失敗しました = 2<br /><br /> 解読に失敗しました = 3<br /><br /> メッセージが不足しています<br />セキュリティ = 4<br /><br /> 整合性チェックに失敗しました = 5<br /><br /> 予期しない処理 <br />エラー = 6|  
|DispositionModifierExt<br />型|Not Valued = 1<br /><br /> エラー = 2<br /><br /> 警告 3 を =|  
|EdiMessageType|X12 の場合、<br /><br /> Edifact では、<br /><br /> Unknown|  
|IsMdnExpected|MDN は不要 = 0<br /><br /> MDN が予測されて = 1|  
|MdnDispositionType|処理 = 1<br /><br /> 失敗 = 2|  
|MdnProcessingStatus|すべて = 0<br /><br /> 処理 = 1<br /><br /> 失敗 = 2<br /><br /> 予想 3 を =<br /><br /> 予期しない = 4|  
|MessageEncryptionType|メッセージが暗号化されていない 0 を =<br /><br /> メッセージが暗号化されて 1 を =|  
|MessageSignatureType|メッセージが署名されていない 0 を =<br /><br /> メッセージが署名されて = 1|  
|MicAlgorithmType|不明な型 =-1<br /><br /> SHA1 = 1<br /><br /> MD5 = 2|  
  
## <a name="businessmessagejournal-bam-activity"></a>BusinessMessageJournal BAM アクティビティ  
 BusinessMessageJournal BAM アクティビティにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、トランザクション セットを持つ受信 EDI インターチェンジを、同じトランザクション セットを持つ送信バッチ インターチェンジと関連付けることができます。 詳細については、次を参照してください。[送信バッチで受信トランザクション セットの関連付け](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)します。  
  
##  <a name="BKMK_Query"></a> EdiMessageContent テーブルは、クエリを実行します。  
 BizTalkDTADb データベースの EdiMessageContent テーブルは、メッセージのメタデータと共に、メッセージ ペイロードを格納します。 カスタム状態レポートでは、メッセージの内容を表示する EdiMessageContent テーブルを照会できます。 これは、どのメッセージの内容を表示できるようにいくつかの製品の状態レポートに似ています、たとえば、AS2 メッセージおよび関連する MDN 状態レポートの有効方法、メッセージを表示することのワイヤ形式。  
  
 カスタム BAM アクティビティから EdiMessageContent テーブルに使用してリンクする EdiMessageContent テーブルで ContentKey 列に対応する BAM アクティビティ内のキー列。 たとえば、AS2MessageActivity BAM アクティビティから EdiMessageContent テーブルへのリンクには使用する、MessagePayloadContentKey 列か MessageWireContentKey 列のいずれか ContentKey 列にリンクします。  
  
|テーブル|[列]|  
|-----------|-------------|  
|EdiMessageContent<br /><br /> (BizTalkDTADb データベース内)|ContentKey<br /><br /> MessageFormat<br /><br /> ContentType<br /><br /> 文字セット<br /><br /> TimeCreated<br /><br /> TimeInserted<br /><br /> IsOrphaned<br /><br /> [Contentbinary]|  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 状態レポートのデータを格納する方法](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)   
 [受信トランザクション セットと送信パッチの関連付け](../core/correlating-an-incoming-transaction-set-with-an-outgoing-batch.md)