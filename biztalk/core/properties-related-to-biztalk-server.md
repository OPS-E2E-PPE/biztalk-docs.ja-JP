---
title: BizTalk Server 関連のプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], properties
- CompleteMessage property [MQSeries adapters]
- SSOAffiliateApplication property [MQSeries adapters]
- Ordered property [MQSeries adapters]
- TransactionSupported property [MQSeries adapters]
- BizTalk_CorrelationID property [MQSeries adapters]
- SegmentationAllowed property [MQSeries adapters]
- DynamicReceive property [MQSeries adapters]
- MQSeries adapters, properties
- DataConversion property [MQSeries adapters]
ms.assetid: c27d7f9c-8198-4624-9952-054ba8ea1c7c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2259a0bed420fdaf9c8b0dbe3f07d27cd8bbc454
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398503"
---
# <a name="properties-related-to-biztalk-server"></a>BizTalk Server に関連するプロパティ
MQSeries アダプターは、MQSeries に直接関連していないものの、アプリケーションの場合にも役立ちますされているいくつかのコンテキスト プロパティに値を割り当てます。  
  
 すべてのプロパティ以外の送受信中に値を受け取る**BizTalk_CorrelationID**します。 **BizTalk_CorrelationID**プロパティでは、値を持つ受信中のみです。  
  
|名前|型|説明|  
|----------|----------|-----------------|  
|**BizTalk_CorrelationID**|string|このプロパティを使用して、MQSeries サーバーが、メッセージで使用するための関連付け識別子を生成します。<br /><br /> 詳細については、次を参照してください。[関連付けメッセージを使用して要求/応答](../core/correlating-messages-using-request-reply.md)します。|  
|**dataConversion**|string|Windows のメッセージを MQSeries Server の ANSI コード ページに変換します。 送信の場合は、MQFMT_STRING メッセージ形式が変換はありません。<br /><br /> 選択**はい**Unicode から ANSI に変換を実行します。<br /><br /> **既定値:** いいえ|  
|**順序付け**|string|MQSeries から受信したか、または、MQSeries キューに送信するように、メッセージの順序を維持するために設定します。<br /><br /> プロパティには、異なる送受信するための値のセットがあります。 値の詳細についてを参照してください。 [MQSeries を構成するアダプターの受信場所と送信ポート方法](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)します。<br /><br /> **既定値:** いいえ|  
|**segmentationAllowed**|string|MQSeries をセグメント化されたメッセージをアセンブルはメッセージを取得または設定します。 プロパティには、異なる送受信するための値のセットがあります。<br /><br /> 受信のとき**No Action** ; のセグメント化を有効にすることがなく、MQSeries キューからメッセージを読み取る使用**完了メッセージ**に渡す前にセグメント化されたメッセージをアセンブルして、アダプター。<br /><br /> **既定値:** 操作はありません。<br /><br /> 送信する場合、選択**はい**、mqseries がセグメント化されたメッセージをキューに配置します。<br /><br /> **既定値:** いいえ|  
|**SSOAffiliateApplication**|string|シングル サインオン (SSO) 関連アプリケーションを設定します。 ユーザー ID とパスワードの SSO からを使用する、 **MQMD_UserIdentifier**、および**MQIIH_Authenticator** (または**MQCIH_Authenticator**) プロパティそれぞれします。<br /><br /> メッセージを送信する場合にのみを使用します。<br /><br /> **既定値:** 空白|  
|**CompleteMessage**|string|「完全なメッセージ」を取得するかどうかを指定するときに、キューからメッセージをセグメント化を取得します。<br /><br /> これを設定**はい**セグメント化されたキューにメッセージを「完全なメッセージ」を取得します。<br /><br /> **既定値:** いいえ|  
|**DynamicReceive**|string|キューから動的にメッセージを受信するかどうかを指定します。<br /><br /> これを設定**はい**キューから動的にメッセージを受信するときにします。 この機能は、送信請求-応答の送信ポートと組み合わせて使用されます。<br /><br /> 一致オプション (MessageID、CorrelationID、または GroupID) を指定する場合、一致条件に関連するメッセージのみが取得されます。|  
|**transactionSupported**|string|アダプターでは、BizTalk Server と MQSeries Server 間の Microsoft 分散トランザクション コーディネーター (DTC) トランザクションを開始します。 設定すると**いいえ**、メッセージ配信の保証はありません。<br /><br /> **既定値:** はい|  
|**WaitInterval**|string|MQ システムが適切なメッセージが到着するを待機する秒単位で表す、おおよその時間を指定します。 この時点で適切なメッセージが到着したなし、呼び出しが失敗します。 **注:** これは、のみ、オーケストレーション内で設定できます。 <br /><br /> **既定値:** 3|  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md)   
 [プロパティのデータ型変換](../core/data-type-conversion-of-properties.md)   
 [MQSeries コンテキスト プロパティ](../core/mqseries-context-properties.md)