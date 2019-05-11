---
title: MSMQ アダプター プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f0c0132da7718fd635e58b173ffcdc12b9f32c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323634"
---
# <a name="msmq-adapter-property-schema-and-properties"></a>MSMQ アダプター プロパティ スキーマおよびプロパティ
MSMQ アダプターは、アプリケーションで使用するコンテキスト プロパティに値を割り当てます。 送信の一覧については、MSMQ アダプターのプロパティを受信したりを参照してください[、MSMQ 受信場所を構成する方法](../core/how-to-configure-an-msmq-receive-location.md)と[MSMQ 送信ポートを構成する方法](../core/how-to-configure-an-msmq-send-port.md)します。  
  
## <a name="context-properties"></a>コンテキスト プロパティ  
 次の表では、MSMQ アダプターが値を割り当てます、コンテキスト プロパティを示します。  
  
|**名前**|**型**|**[説明]**|**昇格**|  
|--------------|--------------|---------------------|------------------|  
|**受信確認**|ssNoversion|このメッセージを表す受信確認の分類を指定の値を使用して、 **System.Messaging.Acknowledgment**列挙体。|いいえ|  
|**AcknowledgeType**|ssNoversion|送信元のアプリケーション要求の受信確認メッセージの種類を指定します。|いいえ|  
|**AdministrationQueue**|string|受信確認メッセージを受信するキュー名の名前を指定します。|いいえ|  
|**AppSpecific**|ssNoversion|さまざまな種類のメッセージを整理するために使用できるアプリケーション固有の情報を指定します。|はい|  
|**ArrivedTime**|dateTime|送信先キューにメッセージが到着した時刻を指定します。|いいえ|  
|**認証**|boolean|メッセージが認証されたかどうかを指定します。|いいえ|  
|**BodyType**|Int|メッセージ本文に含まれるデータの種類を指定します。|いいえ|  
|**CertificateThumbPrint**|string|メッセージの認証に使用するクライアント証明書の拇印を指定します。|はい|  
|**関連付け Id**|string|元のメッセージを参照する受信確認、レポート、および応答メッセージで使用するメッセージ識別子を指定します。|はい|  
|**[EncryptionAlgorithm]**|ssNoversion|メッセージの本文を暗号化するために使用する暗号化アルゴリズムを指定します。|いいえ|  
|**Id**|string|メッセージの識別子を指定します。|いいえ|  
|**Label**|string|メッセージを記述するアプリケーションで定義された Unicode 文字列を指定します。|はい|  
|**MaximumMessageSize**|unsignedint|指定したキューに送信するメッセージをキロバイト単位では、メッセージの最大サイズを指定します。|いいえ|  
|**[MessageType]**|ssNoversion|メッセージの種類を指定します。 メッセージ キューのメッセージには、次の種類のいずれかを指定できます。<br /><br /> 通常、アプリケーションからキューに送信される一般的なメッセージまたは送信元アプリケーションに返される応答メッセージのいずれかであります。<br />-受信確認: 送信側アプリケーションから要求されるたびにメッセージ キューが生成されます。 たとえば、メッセージ キューを元のメッセージが到着したかまたは読み取られたことを示すために、正または負のメッセージを生成できます。 メッセージ キューは、送信元アプリケーションによって指定された管理キューに、適切な受信確認メッセージを返します。<br />-レポート、レポート キューは送信元キュー マネージャーで定義されるたびにメッセージ キューが生成されます。 トレースを有効にすると、メッセージ キュー、レポート メッセージを送信メッセージ キュー レポート キューたびに、元のメッセージに入るか出るメッセージ キュー サーバー。|いいえ|  
|**[Priority]**|ssNoversion|定義されている値を使用してメッセージの優先度を指定します、 **System.Messaging.MessagePriority**列挙体。|はい|  
|**回復可能です**|boolean|コンピューターの障害やネットワークの問題が発生した場合に配信されるメッセージが保証されるかどうかを指定します。|いいえ|  
|**ResponseQueue**|string|アプリケーションによって生成される応答メッセージを受信するキューを指定します。|いいえ|  
|**SegmentationSupport**|boolean|4 MB を超えるメッセージのセグメント化がサポートされているかどうかを指定します。|いいえ|  
|**SentTime**|dateTime|メッセージが送信元キュー マネージャーによって送信された送信元コンピューター上の日付と時刻を指定します。|いいえ|  
|**SourceMachine**|string|メッセージの送信元コンピューターを指定します。|いいえ|  
|**[TimeOut]**|ssNoversion|メッセージが送信先キューをタイムアウトが発生する前に到達するまでの時間を指定します。|いいえ|  
|**TimeOutUnits**|string|単位を指定します、**タイムアウト**プロパティ。 プロパティは、日、時間、分、または秒に設定できます。|いいえ|  
|**トランザクション**|boolean|トランザクションとトランザクション以外の送信ポートし、受信場所の動作を指定します。|いいえ|  
|**UseAuthentication**|boolean|指定するかどうか、メッセージが (または必要があります) 送信される前に認証されました。|いいえ|  
|**UseDeadLetterQueue**|boolean|配信不能キューに配信できなかったメッセージのコピーを送信するかどうかを指定します。|いいえ|  
|**UseJournalQueue**|boolean|メッセージのコピーを元のコンピューターの履歴に保持するかどうかを指定します。|いいえ|  
  
> [!NOTE]
>  **受信確認**、 **AcknowledgeType**、 **EncryptionAlgorithm**、および**MessageType**プロパティと等価の整数を使用します。列挙の値、 **System.Messaging**名前空間。 これらの値の詳細については、.NET Framework クラス ライブラリ ヘルプの「System.Messaging Namespace」を参照してください。  
> 
> [!NOTE]
>  BizTalk プロジェクトを使用して、MSMQ アダプタのコンテキスト プロパティの開発に必要な場合は、BizTalk プロジェクト ファイルへの参照を含める必要があります**Microsoft.BizTalk.Adapter.MSMQ.MsmqAdapterProperties.dll**内にある、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール ディレクトリ。  
  
## <a name="message-labels"></a>メッセージ ラベル  
 メッセージ キューを使用する**ラベル**への参照を追加することで、フィルター プロパティ**Microsoft.BizTalk.Adapter.MSMQ.MsmqAdapterProperties.dll**でプロパティを選択して、 **フィルター**  ダイアログ ボックス。 MSMQ アダプターに自動的に追加されているため、メッセージ コンテキストには、他のコンテキストで、プロパティを使用することもできます。  
  
## <a name="see-also"></a>参照  
 [MSMQ アダプターの構成](../core/configuring-the-msmq-adapter.md)