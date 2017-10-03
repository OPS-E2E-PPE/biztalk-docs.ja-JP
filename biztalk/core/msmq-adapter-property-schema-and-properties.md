---
title: "MSMQ アダプター プロパティ スキーマおよびプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AcknowledgeType property [MSMQ adapters]
- MSMQ adapters, schemas
- AppSpecific property [MSMQ adapters]
- SegmentationSupport property [MSMQ adapters]
- SourceMachine property [MSMQ adapters]
- Label property, MSMQ adapters
- MSMQ adapters, properties
- TimeOut property [MSMQ adapters]
- BodyType property [MSMQ adapters]
- CorrelationId property [MSMQ adapters]
- Recoverable property [MSMQ adapters]
- Authenticated property [MSMQ adapters]
- EncryptionAlgorithm property [MSMQ adapters]
- ResponseQueue property [MSMQ adapters]
- configuring [MSMQ adapters], properties
- MaximumMessageSize property [MSMQ adapters]
- UseAuthentication property [MSMQ adapters]
- UseDeadLetterQueue property [MSMQ adapters]
- SentTime property [MSMQ adapters]
- schemas, MSMQ adapters
- TimeOutUnits property [MSMQ adapters]
- CertificateThumbPrint property [MSMQ adapters]
- Id property [MSMQ adapters]
- UseJournalQueue property [MSMQ adapters]
- MessageType property [MSMQ adapters]
- ArrivedTime property [MSMQ adapters]
- Transactional property [MSMQ adapters]
- configuring [MSMQ adapters], schemas
- Acknowledgement property [MSMQ adapters]
- Priority property [MSMQ adapters]
- AdministrationQueue property [MSMQ adapters]
ms.assetid: 9de29341-db8e-4d50-8f1d-3b7397afb58d
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb2d74848353c5c520a9a17d5a6d897d6a4dce1f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="msmq-adapter-property-schema-and-properties"></a>MSMQ アダプター プロパティ スキーマおよびプロパティ
MSMQ アダプターは、アプリケーションで使用するコンテキスト プロパティに値を割り当てます。 送信の一覧については、MSMQ アダプターのプロパティを受信しを参照してください[、MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)と[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)です。  
  
## <a name="context-properties"></a>コンテキスト プロパティ  
 MSMQ アダプターが値を割り当てるコンテキスト プロパティを次の表に示します。  
  
|**名前**|**型**|**Description**|**昇格**|  
|--------------|--------------|---------------------|------------------|  
|**受信確認**|int|このメッセージが表す受信確認の分類を指定の値を使用して、 **System.Messaging.Acknowledgment**列挙します。|不可|  
|**AcknowledgeType**|int|送信アプリケーションが要求する受信確認メッセージの種類を指定します。|不可|  
|**AdministrationQueue**|string|受信確認メッセージを受け取るキューの名前を指定します。|不可|  
|**AppSpecific**|int|さまざまな種類のメッセージを整理するために使用できるアプリケーション固有の情報を指定します。|はい|  
|**ArrivedTime**|dateTime|メッセージが送信先キューに到着した時刻を指定します。|不可|  
|**認証**|boolean|メッセージが認証されたかどうかを指定します。|不可|  
|**BodyType**|int|メッセージ本文に含まれるデータの型を指定します。|不可|  
|**CertificateThumbPrint**|string|メッセージの認証に使用するクライアント証明書の拇印を指定します。|はい|  
|**関連付け Id**|string|元のメッセージを参照するために、受信確認メッセージ、レポート メッセージ、および応答メッセージによって使用されたメッセージ識別子を指定します。|はい|  
|**[EncryptionAlgorithm]**|int|メッセージの本文を暗号化するために使用された暗号化アルゴリズムを指定します。|不可|  
|**Id**|string|メッセージ識別子を指定します。|不可|  
|**ラベル**|string|メッセージを記述するアプリケーション定義の Unicode 文字列を指定します。|はい|  
|**MaximumMessageSize**|unsignedint|指定したキューに送信するメッセージをキロバイト単位でメッセージの最大サイズを指定します。|不可|  
|**[MessageType]**|int|メッセージの種類を指定します。 メッセージ キューのメッセージには、次のいずれかの種類を指定できます。<br /><br /> -通常は、アプリケーションからキューに送信される一般的なメッセージまたは送信アプリケーションに返される応答メッセージのいずれか。<br />-受信確認: 送信元アプリケーションによって要求されるたびにメッセージ キューが生成されます。 たとえば、メッセージ キューは受信確認メッセージまたは否定応答メッセージを生成して、元のメッセージが着信したことや読み取られたことを示すことができます。 メッセージ キューは、送信アプリケーションによって指定された管理キューに、適切な受信確認メッセージを返します。<br />-このレポートをレポート キューは送信元キュー マネージャーで定義されるたびにメッセージ キューが生成されます。 トレースを有効にすると、メッセージ キュー送信レポート メッセージ、メッセージ キュー レポート キューにたびに、元のメッセージの入力またはメッセージ キュー サーバーを出力します。|不可|  
|**[Priority]**|int|定義されている値を使用してメッセージの優先度を指定します、 **System.Messaging.MessagePriority**列挙します。|はい|  
|**回復可能です**|boolean|コンピューターに障害が発生したりネットワークの問題が発生した場合に、メッセージを確実に配信するかどうかを指定します。|不可|  
|**ResponseQueue**|string|アプリケーションで生成された応答メッセージを受け取るキューを指定します。|不可|  
|**SegmentationSupport**|boolean|4 MB を超えるメッセージのセグメント化をサポートするかどうかを指定します。|不可|  
|**SentTime**|dateTime|送信元のキュー マネージャーからメッセージが送信された際の、送信先コンピューターの日時を指定します。|不可|  
|**SourceMachine**|string|メッセージの送信元であるコンピューターを指定します。|不可|  
|**[TimeOut]**|int|メッセージが送信先のキューに到着するまでにタイムアウトが発生する期間 (時間) を指定します。|不可|  
|**TimeOutUnits**|string|単位を指定、**タイムアウト**プロパティです。 このプロパティは、Days (日)、Hours (時間)、Minutes (分)、または Seconds (秒) に設定できます。|不可|  
|**トランザクション**|boolean|送信ポートと受信場所がトランザクションである場合とそうでない場合の動作を指定します。|不可|  
|**UseAuthentication**|boolean|メッセージを送信前に認証したかどうか (または認証する必要があるかどうか) を指定します。|不可|  
|**UseDeadLetterQueue**|boolean|配信できなかったメッセージのコピーを、配信不能メッセージ キューに送信する必要があるかどうかを指定します。|不可|  
|**UseJournalQueue**|boolean|発信元コンピューターの履歴にメッセージのコピーを保持するかどうかを指定します。|不可|  
  
> [!NOTE]
>  **受信確認**、 **AcknowledgeType**、 **EncryptionAlgorithm**、および**MessageType**プロパティに相当する整数を使用します。列挙の値、 **System.Messaging**名前空間。 これらの値の詳細については、.NET Framework クラス ライブラリ ヘルプの「System.Messaging 名前空間」を参照してください。  
  
> [!NOTE]
>  MSMQ アダプタのコンテキスト プロパティの使用して構成する BizTalk プロジェクトを開発する必要がある場合は、BizTalk プロジェクトは、ファイルへの参照を含める必要があります**Microsoft.BizTalk.Adapter.MSMQ.MsmqAdapterProperties.dll**にある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール ディレクトリです。  
  
## <a name="message-labels"></a>メッセージ ラベル  
 メッセージ キューを使用することができます**ラベル**プロパティへの参照を追加することで、フィルターに**Microsoft.BizTalk.Adapter.MSMQ.MsmqAdapterProperties.dll**でプロパティを選択して、 **フィルター**  ダイアログ ボックス。 MSMQ アダプターは自動的にプロパティをメッセージ コンテキストに追加するため、他のコンテキストでこのプロパティを使用することもできます。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)