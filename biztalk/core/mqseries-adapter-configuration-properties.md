---
title: "MQSeries アダプター構成プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, code sample
- receive locations, adapters
- MQSeries adapters, send ports
- MQSeries adapters, properties
- MQSeries adapters, receive location
- send ports, adapters
ms.assetid: 7517a8bf-aa65-4af9-aed0-7c74fb480328
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 332d8027a12e2d58a8b177d7b0c87eeec8996217
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-configuration-properties"></a>MQSeries アダプター構成プロパティ
次の表に、MQSeries アダプターの受信場所に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|受信場所で監視する場所への完全なパスを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
|queueDetails|VT_BSTR|サーバー、キュー マネージャー、およびキューを含むソースの MQSeries キューに関する情報を指定します。|-なし|このプロパティの前には、uri プロパティを作成するための MQS:// が付きます。|  
|transactionSupported|VT_BSTR|MQSeries アダプターが、BizTalk Server と MQSeries Server 間の Microsoft 分散トランザクション コーディネーター (DTC) トランザクションを開始するかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|no に設定すると、メッセージ配信が保証されません。<br /><br /> 既定値は yes です。|  
|suspendAsNonResumable|VT_BSTR|保留されたメッセージを再開可能に設定するかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値はありません。|  
|dataOffsetForHeaders|VT_BSTR|アダプタは、MQSeries ヘッダー (MQXQH 構造、MQIIH 構造、および MQCIH 構造) の値を使用して、BizTalk Server のコンテキスト プロパティの対応する値を設定します。 既定では、アダプタは、メッセージのボディ部から MQSeries プロパティを削除します。|有効な値は、<br /><br /> -[はい]<br />-なし|メッセージ本文のプロパティを保存する場合は、このプロパティに no を設定してください。<br /><br /> 既定値は yes です。|  
|pollingInterval|VT_BSTR|MQSeries キューをポーリングするために受信コンポーネントによって使用される間隔を指定します。|有効な値は 1 ~ 10000 です。|pollingInterval は、アダプターに組み込まれている 3 秒の待機間隔 (ハードコードされている) と共に使用されます。 pollingInterval の値が 3 秒未満の場合、待機間隔には、pollingInterval の値が設定されます。<br /><br /> 既定値は、3 です。|  
|pollingUnit|VT_BSTR|ポーリング間隔に使用する時間単位を指定します。|有効な値は、<br /><br /> -時間<br />-(分)<br />-(秒)|既定値は、seconds です。|  
|maximumBatchSize|VT_BSTR|メッセージの最大バッチ サイズを KB 単位で指定します。|有効な値は、1 ~ 10485760 です。|既定値は 100 です。|  
|maximumNumberOfMessages|VT_BSTR|バッチ内に含めるメッセージの最大数を指定します。|有効な値は、1 ~ 100000 です。|既定値は 100 です。|  
|threadCount|VT_BSTR|受信場所ごとに使用されるスレッド数を指定します。|有効な値は 1 ~ 64 です。|既定値は 2 です。|  
|fragmentationSize|VT_BSTR|MQSAgent とアダプターとの間でメッセージが送信されるときのメッセージ チャンク サイズを KB 単位で指定します。|有効な値は 1 ~ 1048576 します。|既定値は 500 です。|  
|characterSet|VT_BSTR|文字セットと MQSeries が、受信場所にメッセージを送信する前に文字を変換するかどうかを指定します。|有効な値は、<br /><br /> -none です。 UCS-2 および UTF-16 を変換しません。<br />-Ucs-2 および UTF-16。 これらの文字セットに変換します。 MQSeries は、これらの文字セットを区別しません。<br />-UTF-8。 UTF-8 文字セットに変換します。|既定値は none です。|  
|errorThreshold|VT_BSTR|ログに記録するエラーの最大数を指定します。 アダプタは処理を続行し、アダプタが回復すると、イベント ログにイベントを書き込みます。|有効な値は 1 ~ 1000 です。|既定値は 10 です。|  
|セグメント化|VT_BSTR|MQSeries がセグメント化されたメッセージをアセンブルするか、メッセージをそのまま取得するかを指定します。|有効な値は、<br /><br /> -なし<br />-完了|セグメント化を有効にせずに MQSeries キューからメッセージを読み込むには、none を指定します。<br /><br /> セグメント化されたメッセージをアダプターに渡す前にアセンブルするには、complete を指定します。<br /><br /> 既定値は none です。|  
|順序付けられた式|VT_BSTR|MQSeries が、MQSeries キューからメッセージを受信するときのメッセージ順序を保存するかどうかを指定します。|有効な値は、<br /><br /> -なし<br />-noStop<br />場合は、yesStop<br />場合は、yesSuspend|メッセージの順序を無視する場合は、no を指定します。<br /><br /> メッセージの順序を無視し、エラーが発生した場合に受信場所を無効にするには、noStop を指定します。<br /><br /> 順序を有効にする場合は、yesStop を指定します。 このオプションを選択した場合、エラーが発生すると、トランザクションが終了され、受信場所が無効になります。<br /><br /> 順序を有効にする場合は、yesSuspend を指定します。 このオプションを選択した場合、エラーが発生すると、メッセージが保留キューに移動されます。 エラーが発生した場合、順序は保存されませんが、受信場所でメッセージの受信が続行します。<br /><br /> 既定値はありません。|  
  
 次のコードは、プロパティの設定に使用する文字列の形式を示しています。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>MQS://TESTMQServer/DQM1/RQ0</uri><queueDetails>TESTMQServer/DQM1/RQ0</queueDetails><transactionSupported>yes</transactionSupported><suspendAsNonResumable>no</suspendAsNonResumable><dataOffsetForHeaders>yes</dataOffsetForHeaders><pollingInterval>1</pollingInterval><pollingUnit>seconds</pollingUnit><maximumBatchSize>100</maximumBatchSize><maximumNumberOfMessages>100</maximumNumberOfMessages><threadCount>2</threadCount><fragmentationSize>500</fragmentationSize><characterSet>none</characterSet><errorThreshold>10</errorThreshold><segmentation>none</segmentation><ordered>no</ordered></Config></AdapterConfig></CustomProps>  
```  
  
 次の表に、MQSeries アダプターの送信ポートに設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|uri|VT_BSTR|データの送信先の完全なパスを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
|queueDetails|VT_BSTR|サーバー、キュー マネージャー、およびキューを含むターゲットの MQSeries キューに関する情報を指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|このプロパティの前には、uri プロパティを作成するための MQS:// が付きます。|  
|transactionSupported|VT_BSTR|MQSeries アダプターが、BizTalk Server と MQSeries Server 間の Microsoft 分散トランザクション コーディネーター (DTC) トランザクションを開始するかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|no に設定すると、メッセージ配信が保証されません。<br /><br /> 既定値は yes です。|  
|dataConversion|VT_BSTR|MQSeries for Windows サーバーの ANSI コード ページにメッセージを変換するかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値はありません。|  
|segmentationAllowed|VT_BSTR|個別のメッセージが MQSeries キューのメッセージの最大長を超えた場合に MQSeries キュー マネージャーのセグメント化を使用するかどうかを指定します。|有効な値は次のとおりです。<br /><br /> -[はい]<br />-なし|既定値はありません。|  
|fragmentationSize|VT_BSTR|アダプターと MQSAgent との間でメッセージが送信されるときのメッセージ チャンク サイズを KB 単位で指定します。|有効な値は 1 ~ 1048576 します。|既定値は 500 です。|  
|順序付けられた式|VT_BSTR|MQSeries が、MQSeries キューにメッセージが送信されるときのメッセージ順序を保持するかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値はありません。|  
  
 次のコードは、プロパティの設定に使用する文字列の形式を示しています。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>MQS://TESTMQServer/DQM1(QM1)/SQ0</uri><queueDetails>TESTMQServer/DQM1(QM1)/SQ0</queueDetails><transactionSupported>yes</transactionSupported><dataConversion>no</dataConversion><segmentationAllowed>no</segmentationAllowed><fragmentationSize>500</fragmentationSize><ordered>no</ordered></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  アダプター フレームワークを使用して構築されたアダプターに TransportTypeData 構成データを指定するときに使用される名前/値ペア必要がありますすべてに格納される、 \<AdapterConfig > 要素。 \<AdapterConfig > 要素は VT_BSTR を指定します (vt =「8」) データを入力し、 \< > データ内の文字をエスケープする必要があります。