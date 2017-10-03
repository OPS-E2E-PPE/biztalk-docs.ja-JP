---
title: "BizTalk Server に関連するプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f729e4ab359471e002029efc04c0c8ad21e0d99b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="properties-related-to-biztalk-server"></a>BizTalk Server に関連するプロパティ
MQSeries アダプタが値を割り当てるコンテキスト プロパティの中には、MQSeries に直接関係しなくても、他のアプリケーションに役立つものがあります。  
  
 すべてのプロパティは、以外の送受信中に値を受け取る**BizTalk_CorrelationID**です。 **BizTalk_CorrelationID**プロパティでは、値を持つ受信中のみです。  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|**BizTalk_CorrelationID**|string|メッセージで使用する関連付け識別子を MQSeries サーバーで生成するには、このプロパティを使用します。<br /><br /> 詳細については、次を参照してください。[を相互に関連付けるメッセージを使用して要求/応答](../core/correlating-messages-using-request-reply.md)です。|  
|**DataConversion**|string|MQSeries Server for Windows の ANSI コード ページにメッセージを変換します。 送信時のメッセージ形式が MQFMT_STRING でない場合、変換は行われません。<br /><br /> 選択**はい**Unicode から ANSI に変換を実行します。<br /><br /> **既定値:**なし|  
|**順序付け**|string|MQSeries を設定して、メッセージの順序を保ったまま MQSeries キューとの間でメッセージを送受信するようにします。<br /><br /> このプロパティの値のセットは、送信と受信で異なります。 値についてを参照してください。 [アダプター受信場所と送信ポートを MQSeries を構成する方法](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)です。<br /><br /> **既定値:**なし|  
|**SegmentationAllowed**|string|MQSeries を設定し、セグメント化されたメッセージをアセンブルするか、メッセージをそのまま取得します。 このプロパティの値のセットは、送信と受信で異なります。<br /><br /> 受信するときを使用して**No Action** ; のセグメント化を有効にせず、MQSeries キューからメッセージの読み取りを使用して**完全なメッセージ**に渡す前にセグメント化されたメッセージをアセンブルして、アダプター。<br /><br /> **既定値:**操作はありません<br /><br /> 送信する場合、選択**はい**、mqseries キューにセグメント化されたメッセージを配置します。<br /><br /> **既定値:**なし|  
|**SSOAffiliateApplication**|string|シングル サインオン (SSO) 関連のアプリケーションを設定します。 ユーザー ID と SSO からパスワードを使用する、 **MQMD_UserIdentifier**、および**MQIIH_Authenticator** (または**MQCIH_Authenticator**) プロパティそれぞれします。<br /><br /> メッセージを送信するときにのみ使用します。<br /><br /> **既定値:**空白|  
|**CompleteMessage**|string|キューからセグメント化されたメッセージを取得するときに、"完全なメッセージ" を取得するかどうかを指定します。<br /><br /> これを設定して**はい**セグメント化されたキューにメッセージを「完全なメッセージ」を取得します。<br /><br /> **既定値:**なし|  
|**DynamicReceive**|string|キューから動的にメッセージを受信するかどうかを指定します。<br /><br /> これを設定して**はい**キューから動的にメッセージを受信するときにします。 動的受信は、送信請求 - 応答の送信ポートと併せて使用します。<br /><br /> 一致オプション (MessageID、CorrelationID、または GroupID) を指定している場合、一致条件に関連するメッセージのみが取得されます。|  
|**TransactionSupported**|string|アダプターは、BizTalk Server と MQSeries Server 間の Microsoft 分散トランザクション コーディネーター (DTC) トランザクションを開始します。 設定すると**いいえ**、メッセージ配信の保証はありません。<br /><br /> **既定値:** [はい]|  
|**WaitInterval**|string|MQ システムが、処理対象メッセージの到着を待機する概算の時間 (秒) を指定します。 処理対象のメッセージが時間内に到着しなかった場合、呼び出しは失敗します。 **注:**のみ、オーケストレーション内で設定できます。 <br /><br /> **既定値:** 3|  
  
## <a name="see-also"></a>参照  
 [MQSeries アダプターのプロパティ](../core/mqseries-adapter-properties.md)   
 [プロパティのデータ型の変換](../core/data-type-conversion-of-properties.md)   
 [MQSeries コンテキスト プロパティ](../core/mqseries-context-properties.md)