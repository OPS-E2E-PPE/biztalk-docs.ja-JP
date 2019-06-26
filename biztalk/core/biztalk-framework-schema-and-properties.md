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
ms.openlocfilehash: 96aa2417e089d6ce2453b69af240e7c0056f2692
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358044"
---
# <a name="biztalk-framework-schema-and-properties"></a>BizTalk Framework スキーマおよびプロパティ
** http://schemas.microsoft.com/BizTalk/2003/btf2-properties **名前空間には、BizTalk Framework 逆アセンブラー パイプライン コンポーネントのメッセージおよび部分コンテキスト プロパティを設定するために使用できるプロパティが含まれています。 BizTalk Framework 逆アセンブラー パイプライン コンポーネントでは、これらのプロパティを使用して作成されるメッセージの適切なヘッダーを生成します。 次の表では、BizTalk Framework のプロパティについて説明します。  

## <a name="properties-list"></a>[プロパティ]  

|名前|型|説明|  
|----------|----------|-----------------|  
|**IsReliable**|xs:boolean|変換先から受信確認を受信するまでに、BizTalk Framework メッセージを再送するかどうかを示します。 このプロパティは BizTalk Framework コンポーネントによって内部的に設定し、エンジンが使用します。 コードからこのプロパティの値は変わりません。|  
|**PassAckThrough**|xs:boolean|使用しているのではなく BizTalk Framework 逆アセンブラー パイプライン コンポーネントを通じて受信確認メッセージを渡す必要があるかどうかを示します。|  
|**eps_to_address**|xs:string|送信先アドレスを指定します。|  
|**eps_to_address_type**|xs:string|送信先アドレスの種類を指定します。|  
|**eps_from_address**|xs:string|送信元アドレスを指定します。|  
|**eps_from_address_type**|xs:string|ソース アドレスの種類を指定します。|  
|**prop_identity**|xs:string|ログ記録、追跡、エラー処理、またはその他のドキュメントの処理と相関関係の要件のために BizTalk フレームワーク ドキュメントを一意に識別する URI 参照。|  
|**prop_sentAt**|xs:string|BizTalk フレームワーク ドキュメントの送信タイムスタンプです。|  
|**prop_topic**|xs:string|BizTalk フレームワーク ドキュメントの全体的な目的を一意に識別する URI 参照。|  
|**svc_deliveryRctRqt_sendTo_address**|xs:string|BizTalk フレームワーク ドキュメントの配信確認メッセージを送信するアドレスを指定します。|  
|**svc_deliveryRctRqt_sendTo_address_type**|xs:string|BizTalk フレームワーク ドキュメントの配信確認メッセージを送信するアドレスの種類を指定します。|  
|**svc_deliveryRctRqt_sendBy**|xs:dateTime|BizTalk フレームワーク ドキュメントの配信確認メッセージを受信する必要があります (分単位) を指定します。|  
|**svc_commitmentRctRqt_sendTo_address**|xs:string|送信者の要求の処理に関する受信者の決定の通知の送信先アドレスを指定します。|  
|**svc_commitmentRctRqt_sendTo_address_type**|xs:string|送信者の要求の処理に関する受信者の決定の通知の送信先アドレスの種類を指定します。|  
|**svc_commitmentRctRqt_sendBy**|xs:dateTime|送信者が BizTalk フレームワーク ドキュメントに関する契約確認メッセージを受信する必要があります (分単位で時間を指定します。|  
|**prc_type**|xs:string|BizTalk Framework メッセージの処理に関連するビジネス プロセスの種類を指定する URI 参照を提供します。|  
|**prc_instance**|xs:string|BizTalk フレームワーク ドキュメントに関連するビジネス プロセスの特定のインスタンスを一意に識別する URI 参照を提供します。|  
|**deliveryRct_receivedAt**|xs:dateTime|この受信で確認されたドキュメントの受信タイムスタンプを指定します。 受信タイムスタンプには、最初のコピーを受信した時刻または確認されたコピーを受信した時刻を反映可能性があります。|  
|**deliveryRct_identity**|xs:string|配信確認メッセージで確認された BizTalk フレームワーク ドキュメントの id を指定します。|  
|**commitmentRct_identity**|xs:string|コミットメント受信で確認された BizTalk フレームワーク ドキュメントの id を指定します。|  
|**commitmentRct_decidedAt**|xs:string|この受信で確認されたドキュメントの処理決定のタイムスタンプを指定します。|  
|**commitmentRct_decision**|xs:string|正または負の値を実際の決定を指定します。|  
|**commitmentRct_commitmentCode**|xs:QName|処理決定に関する詳細な状態を指定する (XSD) で修飾名を指定します。|  

## <a name="see-also"></a>参照  
- **メッセージ コンテキスト プロパティ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]   
- [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)
