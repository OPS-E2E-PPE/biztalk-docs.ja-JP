---
title: EDI インターチェンジと確認を送信する動的送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a124059c-c29c-4a7f-a8a3-13dffc09ae5c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4883eb78a24eb7ad7254e319c901602dfcb97a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391398"
---
# <a name="configuring-a-dynamic-send-port-to-send-edi-interchanges-and-acknowledgments"></a>EDI インターチェンジと確認を送信するための動的送信ポートの構成
を、EDI 受信確認またはインターチェンジを送信するには、静的な送信ポートまたは動的送信ポートのいずれかを使用できます。 動的送信ポートでは、アグリーメントを解決し、DestinationPartyName コンテキスト プロパティの値に基づいて送信先アドレスを決定するために複数の送信先のいずれかにインターチェンジを送信することができます。  
  
> [!NOTE]
>  受信されると、XML メッセージに基づく EDI インターチェンジを送信して、パススルーを使用している場合は、そのアプリケーションを受信するためのパイプラインの受信、DestinationPartyName コンテキスト プロパティを昇格させる必要があります。 詳細については、次を参照してください。[アグリーメントの解決と送信 EDI メッセージのスキーマ決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)します。  
  
> [!NOTE]
>  インターチェンジを受信したポートで EDI 逆アセンブラーの DestinationPartyName プロパティが設定するため、動的送信ポートが受信確認を送信する場合は、DestinationPartyName コンテキスト プロパティが昇格する既に、受信確認。  
  
 動的な一方向の送信ポートを作成するには、次の構成を使用します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ:[全般]**|[ポートの種類]|動的な一方向|  
|**送信ポートのプロパティ:[全般]**|送信ハンドラー|BizTalkServerApplication|  
|**送信ポートのプロパティ:[全般]**|[送信パイプライン]|EdiSend|  
|**ファイル トランスポートのプロパティ:認証**|ホストに (ユーザー名とパスワード) を持つネットワーク共有へのアクセスがあるない場合に、これらの資格情報を使用します。|認証が必要な場合に設定します。|  
|**送信ポートのプロパティ:フィルター**|プロパティ|BTS.MessageType|  
|**送信ポートのプロパティ:フィルター**|演算子|==|  
|**送信ポートのプロパティ:フィルター**|値|**インターチェンジの**:<br /><br /> - `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`、または<br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`、または<br /><br /> **Ack の**:<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_997_Root`、または<br /><br /> -                   `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`、または<br /><br /> -                   `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a>アグリーメント プロパティの設定  
 送信ポートを作成した後は、関数への送信パイプラインに必要なアグリーメントのプロパティを設定する必要があります。 これらのプロパティのさまざまなページの設定、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [EDI ソリューションのポートの構成](../core/configuring-ports-for-an-edi-solution.md)