---
title: EDI インターチェンジと確認を送信する静的な送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b432c5e-ea0c-4174-bb4a-958b061c1827
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5c9e3e1648d570c41567339617c9a0b20ad8d47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391378"
---
# <a name="configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments"></a>EDI インターチェンジと受信確認を送信するための静的送信ポートの構成
EDI 受信確認またはインターチェンジを送信するには、静的な一方向送信ポートまたは静的な送信請求-応答 (双方向) の送信ポートのいずれかを使用することができます。  
  
-   作成、一方向送信ポートを作成する場合も、一方向の受信 (有効になっている) 場合は、EDI 受信確認を受信するポート。  
  
-   EDI インターチェンジを送信して、関連付けられている受信パイプライン経由で EDI 受信確認 (有効な場合) を受信する送信請求-応答送信ポートを作成します。  
  
## <a name="configuring-a-static-one-way-send-port"></a>静的な一方向送信ポートを構成します。  
 静的な一方向送信 EDI インターチェンジおよび受信確認の送信、次の構成を使用するポートを作成します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ:[全般]**|[ポートの種類]|静的な一方向|  
|**送信ポートのプロパティ:[全般]**|トランスポートの種類|多くの型、ファイル、FTP、HTTP、MQSeries、MSMQ、SMTP、SOAP、SQL など、WCF の型、および Windows SharePoint Services を使用できます。|  
|**送信ポートのプロパティ:[全般]**|送信ハンドラー|BizTalkServerApplication|  
|**送信ポートのプロパティ:[全般]**|[送信パイプライン]|EdiSend|  
|**トランスポートのプロパティ:(ファイル トランスポートの種類) の認証**|ホストに (ユーザー名とパスワード) を持つネットワーク共有へのアクセスがあるない場合に、これらの資格情報を使用します。|認証が必要な場合に設定します。|  
|**送信ポートのプロパティ:フィルター**|プロパティ|BTS.MessageType<br /><br /> 注:<br /><br /> BTS を使用することもできます。ReceivePortName またはその他のプロパティを昇格します。|  
|**送信ポートのプロパティ:フィルター**|演算子|==|  
|**送信ポートのプロパティ:フィルター**|値|**BTS を使用します。インターチェンジのメッセージの種類:**<br /><br /> - **X12**: `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`、または<br /><br /> - **Edifact**: `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`<br /><br /> **BTS を使用します。Ack の MessageType**:<br /><br /> -                     **X12**: `http://schemas.microsoft.com/Edi/X12#X12_997_Root`、または<br /><br /> -                     **X12**: `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`、または<br /><br /> -                     **Edifact**: `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="configuring-a-static-solicit-response-send-port"></a>静的な送信請求-応答の送信ポートの構成  
 作成する静的な送信請求-応答 (双方向) の EDI インターチェンジおよび受信確認の送信、次の構成を使用するポートを送信します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ:[全般]**|[ポートの種類]|静的な送信請求-応答|  
|**送信ポートのプロパティ:[全般]**|トランスポートの種類|多くの種類などの HTTP、MQSeries、MSMQ、SOAP、SQL、および WCF の種類を指定できます。 ファイル、FTP、SMTP、または Windows SharePoint Services にすることはできません。|  
|**送信ポートのプロパティ:[全般]**|送信ハンドラー|BizTalkServerApplication|  
|**送信ポートのプロパティ:[全般]**|[送信パイプライン]|EdiSend|  
|**送信ポートのプロパティ:[全般]**|受信パイプライン。|EdiReceive|  
|**トランスポートのプロパティ:(HTTP トランスポートの種類) の認証**|ホストに (ユーザー名とパスワード) を持つネットワーク共有へのアクセスがあるない場合に、これらの資格情報を使用します。|認証が必要な場合に設定します。|  
|**送信ポートのプロパティ:フィルター**|プロパティ|BTS.MessageType<br /><br /> 注:<br /><br /> BTS を使用することもできます。ReceivePortName またはその他のプロパティを昇格します。|  
|**送信ポートのプロパティ:フィルター**|演算子|==|  
|**送信ポートのプロパティ:フィルター**|値|**BTS を使用します。インターチェンジのメッセージの種類:**<br /><br /> -                     **X12**: `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`、または<br /><br /> -                     **Edifact**: `http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`<br /><br /> **BTS を使用します。Ack の MessageType**:<br /><br /> -                     **X12**: `http://schemas.microsoft.com/Edi/X12#X12_997_Root`、または<br /><br /> -                     **X12**: `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`、または<br /><br /> -                     **Edifact**: `http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a>アグリーメント プロパティの設定  
 送信ポートを作成した後は、関数への送信パイプラインに必要なアグリーメントのプロパティを設定する必要があります。 これらのプロパティのさまざまなページの設定、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [EDI ソリューションのポートを構成します。](../core/configuring-ports-for-an-edi-solution.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)