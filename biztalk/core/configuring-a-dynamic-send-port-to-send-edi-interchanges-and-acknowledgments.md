---
title: "EDI インターチェンジと確認を送信する動的送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a124059c-c29c-4a7f-a8a3-13dffc09ae5c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a793fc22394c2b4d294bcd48fae1f9403ae9278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments"></a>EDI インターチェンジと確認を送信するための動的送信ポートの構成
EDI 確認またはインターチェンジを送信するには、静的送信ポートまたは動的送信ポートを使用できます。 動的送信ポートは、アグリーメントを解決して、DestinationPartyName コンテキスト プロパティ内の値に基づいて送信先アドレスを特定します。そのため、動的送信ポートを使用すると、複数の送信先のいずれにもインターチェンジを送信できるようになります。  
  
> [!NOTE]
>  受信した XML メッセージに基づく EDI インターチェンジを送信し、そのアプリケーションを受信するためにパススルー受信パイプラインを使用する場合は、DestinationPartyName コンテキスト プロパティを昇格させる必要があります。 詳細については、次を参照してください。[アグリーメントの解決と送信 EDI メッセージのスキーマの決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)です。  
  
> [!NOTE]
>  動的送信ポートが確認を送信する場合は、インターチェンジを受信したポートの EDI 逆アセンブラーによって確認の DestinationPartyName プロパティが設定されるため、DestinationPartyName コンテキスト プロパティが既に昇格されています。  
  
 一方向の動的送信ポートを作成するには、次の構成を使用します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ: 全般**|[ポートの種類]|動的な一方向|  
|**送信ポートのプロパティ: 全般**|送信ハンドラー|BizTalkServerApplication|  
|**送信ポートのプロパティ: 全般**|[送信パイプライン]|EdiSend|  
|**ファイル トランスポートのプロパティ: 認証**|ホストにネットワーク共有へのアクセス権がない場合に、これらの資格情報を (ユーザー名およびパスワードと共に) 使用します。|認証が必要な場合に設定します。|  
|**送信ポートのプロパティ: フィルター**|プロパティ|BTS.MessageType|  
|**送信ポートのプロパティ: フィルター**|演算子|==|  
|**送信ポートのプロパティ: フィルター**|値|**インターチェンジの**:<br /><br /> - `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`、または<br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`、または<br /><br /> **Ack の**:<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`、または<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`、または<br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a>アグリーメント プロパティの設定  
 送信ポートを作成したら、送信パイプラインを正しく機能させるために必要となるアグリーメント プロパティを設定する必要があります。 さまざまなページでこれらのプロパティが設定されて、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [EDI ソリューションのポートを構成します。](../core/configuring-ports-for-an-edi-solution.md)