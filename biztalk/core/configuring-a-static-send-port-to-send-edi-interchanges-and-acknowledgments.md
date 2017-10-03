---
title: "EDI インターチェンジと確認を送信する静的な送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b432c5e-ea0c-4174-bb4a-958b061c1827
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8645cd36447c814a5c43534e6c01de51e4be52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-static-send-port-to-send-edi-interchanges-and-acknowledgments"></a>EDI インターチェンジと受信確認を送信するための静的送信ポートの構成
EDI 受信確認またはインターチェンジを送信するには、静的な一方向の送信ポートまたは静的な送信請求 - 応答 (双方向) の送信ポートを使用できます。  
  
-   EDI 受信確認 (有効になっている場合) を受信する一方向の受信ポートを作成する場合は、一方向の送信ポートを作成します。  
  
-   関連付けられた受信パイプライン経由で EDI インターチェンジを送信し、EDI 受信確認 (有効になっている場合) を受信するには、送信請求 - 応答の送信ポートを作成します。  
  
## <a name="configuring-a-static-one-way-send-port"></a>静的な一方向の送信ポートの構成  
 静的な一方向の送信ポートを作成して EDI インターチェンジおよび受信確認を送信するには、次の構成を使用します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ: 全般**|[ポートの種類]|静的な一方向|  
|**送信ポートのプロパティ: 全般**|トランスポートの種類|FILE、FTP、HTTP、MQSeries、MSMQ、SMTP、SOAP、SQL、WCF などのさまざまなトランスポート、および Windows SharePoint Services を指定できます。|  
|**送信ポートのプロパティ: 全般**|送信ハンドラー|BizTalkServerApplication|  
|**送信ポートのプロパティ: 全般**|[送信パイプライン]|EdiSend|  
|**トランスポートのプロパティ: 認証 (ファイル トランスポートの種類)**|ホストにネットワーク共有へのアクセス権がない場合に、これらの資格情報を (ユーザー名およびパスワードと共に) 使用します。|認証が必要な場合に設定します。|  
|**送信ポートのプロパティ: フィルター**|プロパティ|BTS.MessageType<br /><br /> 注:<br /><br /> BTS.ReceivePortName またはその他の昇格させたプロパティを使用することもできます。|  
|**送信ポートのプロパティ: フィルター**|演算子|==|  
|**送信ポートのプロパティ: フィルター**|値|**BTS を使用します。インターチェンジの MessageType:**<br /><br /> - **X12**: `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`、または<br /><br /> - **Edifact**:`http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`<br /><br /> **BTS を使用します。Ack の MessageType**:<br /><br /> -                     **X12**: `http://schemas.microsoft.com/Edi/X12#X12_997_Root`、または<br /><br /> -                     **X12**: `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`、または<br /><br /> -                     **Edifact**:`http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="configuring-a-static-solicit-response-send-port"></a>静的な送信請求 - 応答の送信ポートの構成  
 静的な送信請求 - 応答 (双方向) の送信ポートを作成して EDI インターチェンジおよび受信確認を送信するには、次の構成を使用します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ: 全般**|[ポートの種類]|静的な送信請求 - 応答|  
|**送信ポートのプロパティ: 全般**|トランスポートの種類|HTTP、MQSeries、MSMQ、SOAP、SQL、および WCF など、さまさざまな種類を指定できます。 FILE、FTP、SMTP、または Windows SharePoint Services を指定することはできません。|  
|**送信ポートのプロパティ: 全般**|送信ハンドラー|BizTalkServerApplication|  
|**送信ポートのプロパティ: 全般**|[送信パイプライン]|EdiSend|  
|**送信ポートのプロパティ: 全般**|受信パイプライン。|EdiReceive|  
|**トランスポートのプロパティ: 認証 (HTTP トランスポートの種類)**|ホストにネットワーク共有へのアクセス権がない場合に、これらの資格情報を (ユーザー名およびパスワードと共に) 使用します。|認証が必要な場合に設定します。|  
|**送信ポートのプロパティ: フィルター**|プロパティ|BTS.MessageType<br /><br /> 注:<br /><br /> BTS.ReceivePortName またはその他の昇格させたプロパティを使用することもできます。|  
|**送信ポートのプロパティ: フィルター**|演算子|==|  
|**送信ポートのプロパティ: フィルター**|値|**BTS を使用します。インターチェンジの MessageType:**<br /><br /> -                     **X12**: `http://schemas.microsoft.com/Edi/X12/2006#<schema name>`、または<br /><br /> -                     **Edifact**:`http://schemas.microsoft.com/Edi/Edifact/2006#<schema name>`<br /><br /> **BTS を使用します。Ack の MessageType**:<br /><br /> -                     **X12**: `http://schemas.microsoft.com/Edi/X12#X12_997_Root`、または<br /><br /> -                     **X12**: `http://schemas.microsoft.com/Edi/X12#X12_TA1_Root`、または<br /><br /> -                     **Edifact**:`http://schemas.microsoft.com/Edi/Edifact#Efact_Contrl_Root`|  
  
## <a name="setting-agreement-properties"></a>アグリーメント プロパティの設定  
 送信ポートを作成したら、送信パイプラインを正しく機能させるために必要となるアグリーメント プロパティを設定する必要があります。 さまざまなページでこれらのプロパティが設定されて、**アグリーメントのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [EDI ソリューションのポートを構成します。](../core/configuring-ports-for-an-edi-solution.md)   
 [送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)