---
title: BizTalk Framework スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8986e4a7-0c0a-415f-8a74-4fca71d3f1b5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75bbb67410f320cc566871f987f58ec3bae216b4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013059"
---
# <a name="biztalk-framework-schema-and-properties"></a>BizTalk Framework スキーマおよびプロパティ
**http://schemas.microsoft.com/BizTalk/2003/btf2-properties**名前空間には、BizTalk Framework 逆アセンブラー パイプライン コンポーネントのメッセージおよび部分コンテキスト プロパティを設定するために使用できるプロパティが含まれています。 BizTalk Framework 逆アセンブラー パイプライン コンポーネントは、これらのプロパティを使用して、作成されるメッセージの適切なヘッダーを生成します。 次の表は、BizTalk Framework のプロパティを示しています。  

## <a name="properties-list"></a>[プロパティ]  

|名前|型|説明|  
|----------|----------|-----------------|  
|**IsReliable**|xs:boolean|送信先から受信確認が送られるまで BizTalk Framework メッセージを再送するかどうかを示します。 このプロパティは、BizTalk Framework コンポーネントによって内部的に設定され、エンジンによって使用されます。 コードのこのプロパティの値を変更しないでください。|  
|**PassAckThrough**|xs:boolean|破棄せずに BizTalk Framework 逆アセンブラー パイプライン コンポーネントを通じて受信確認のメッセージを渡すかどうかを示します。|  
|**eps_to_address**|xs:string|送信先アドレスを指定します。|  
|**eps_to_address_type**|xs:string|送信先アドレスの種類を指定します。|  
|**eps_from_address**|xs:string|送信元アドレスを指定します。|  
|**eps_from_address_type**|xs:string|送信元アドレスの種類を指定します。|  
|**prop_identity**|xs:string|ログ記録、追跡、エラー処理、または他のドキュメントの処理や関連する要件のために BizTalk フレームワーク ドキュメントを一意に識別する URI 参照です。|  
|**prop_sentAt**|xs:string|BizTalk フレームワーク ドキュメントの送信タイムスタンプです。|  
|**prop_topic**|xs:string|BizTalk フレームワーク ドキュメントの全体目的を一意に識別する URI 参照です。|  
|**svc_deliveryRctRqt_sendTo_address**|xs:string|BizTalk フレームワーク ドキュメントの配信確認メッセージの送信先アドレスを指定します。|  
|**svc_deliveryRctRqt_sendTo_address_type**|xs:string|BizTalk フレームワーク ドキュメントの配信確認メッセージの送信先アドレスの種類を指定します。|  
|**svc_deliveryRctRqt_sendBy**|xs:dateTime|BizTalk フレームワーク ドキュメントの配信確認メッセージを、いつまでに受信するかを指定します (分単位)。|  
|**svc_commitmentRctRqt_sendTo_address**|xs:string|送信者の要求処理に関する受信者の決定通知を送信するアドレスを指定します。|  
|**svc_commitmentRctRqt_sendTo_address_type**|xs:string|送信者の要求処理に関する受信者の決定通知を送信するアドレスの種類を指定します。|  
|**svc_commitmentRctRqt_sendBy**|xs:dateTime|BizTalk フレームワーク ドキュメントに関する契約確認メッセージを、送信者がいつまでに受信するかを指定します (分単位)。|  
|**prc_type**|xs:string|BizTalk Framework メッセージの処理に含まれるビジネス プロセスの種類を指定する URI 参照を提供します。|  
|**prc_instance**|xs:string|BizTalk フレームワーク ドキュメントに関連するビジネス プロセスの特定のインスタンスを一意に識別する URI 参照を提供します。|  
|**deliveryRct_receivedAt**|xs:dateTime|この受信で確認されたドキュメントの受信タイムスタンプを指定します。 受信タイムスタンプには、最初のコピーを受信した時間または受信確認されたコピーを受信した時間が反映されます。|  
|**deliveryRct_identity**|xs:string|配信確認で受信が確認された BizTalk フレームワーク ドキュメントの ID を指定します。|  
|**commitmentRct_identity**|xs:string|契約確認で受信が確認された BizTalk フレームワーク ドキュメントの ID を指定します。|  
|**commitmentRct_decidedAt**|xs:string|この受信で確認されたドキュメントの処理決定のタイムスタンプを指定します。|  
|**commitmentRct_decision**|xs:string|正または負の指定できる値と共に実際の決定を指定します。|  
|**commitmentRct_commitmentCode**|xs:QName|処理決定に関する詳細な状態を指定する修飾名 (XSD 形式) を指定します。|  

## <a name="see-also"></a>参照  
- **メッセージ コンテキスト プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)
