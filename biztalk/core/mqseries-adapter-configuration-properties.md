---
title: MQSeries アダプター構成プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, code sample
- receive locations, adapters
- MQSeries adapters, send ports
- MQSeries adapters, properties
- MQSeries adapters, receive location
- send ports, adapters
ms.assetid: 7517a8bf-aa65-4af9-aed0-7c74fb480328
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9840b7018bf334d93076aaa0a9e20d697ab355c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264549"
---
# <a name="mqseries-adapter-configuration-properties"></a>MQSeries アダプター構成プロパティ
次の表、MQSeries アダプターの設定できる構成プロパティには、場所が表示されます。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|Uri|VT_BSTR|受信場所で監視する場所への完全パスを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
|queueDetails|VT_BSTR|サーバー、キュー マネージャー、およびキューを含むソースの MQSeries キューに関する情報を指定します。|-None|このプロパティの MQS が付きます。//、uri プロパティを作成します。|  
|transactionSupported|VT_BSTR|MQSeries アダプターが BizTalk Server と MQSeries Server 間の Microsoft 分散トランザクション コーディネーター (DTC) トランザクションを開始するかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|設定した場合にないメッセージ配信の保証はありません。<br /><br /> 既定値は、yes です。|  
|suspendAsNonResumable|VT_BSTR|かどうかに保留中のメッセージを再開可能としてはマークかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値はありません。|  
|dataOffsetForHeaders|VT_BSTR|アダプターでは、BizTalk Server のコンテキスト プロパティに対応する値を設定、MQSeries ヘッダー (MQXQH、mqiih 構造、および MQCIH 構造) の値が使用されます。 既定では、アダプターは、メッセージ本文から MQSeries プロパティを削除します。|有効な値は、<br /><br /> -[はい]<br />-なし|メッセージ本文のプロパティを保持するには、このプロパティを設定します。<br /><br /> 既定値は、yes です。|  
|PollingInterval|VT_BSTR|MQSeries キューをポーリングする受信コンポーネントによって使用される間隔を指定します。|有効な値は 1 ~ 10000 です。|PollingInterval は、アダプターに組み込まれている 3 秒の待機をハード コーディングされた間隔と組み合わせて動作します。 PollingInterval の値が 3 秒未満の場合、待機間隔は、pollingInterval の値に設定します。<br /><br /> 既定値は、3 です。|  
|pollingUnit|VT_BSTR|ポーリング間隔の時間の単位を指定します。|有効な値は、<br /><br /> -時間<br />-分<br />-秒|既定値は、秒です。|  
|maximumBatchSize|VT_BSTR|メッセージのバッチの最大サイズをキロバイト (KB) 単位で指定します。|有効な値が 1 から 10485760 には|既定値は 100 です。|  
|maximumNumberOfMessages|VT_BSTR|バッチのメッセージの最大数を指定します。|有効な値が 1 から 100000 には|既定値は 100 です。|  
|threadCount|VT_BSTR|ごとに使用されるスレッドの数の受信場所を指定します。|有効な値は 1 ~ 64 です。|既定値は 2 です。|  
|fragmentationSize|VT_BSTR|MQSAgent とアダプター間でデータが送信されるときは、キロバイト (KB) メッセージのメッセージ チャンク サイズを指定します。|有効な値は 1 ~ 1048576 です。|既定値は、500 です。|  
|文字セット|VT_BSTR|文字セットと MQSeries がメッセージを受信場所に送信する前に文字を変換するかどうかを指定します。|有効な値は、<br /><br /> -none。 変換されません。<br />-Ucs-2 および UTF-16。 これらの文字セットに変換します。 MQSeries は、それらの間は区別されません。<br />-UTF-8。 Utf-8 文字セットに変換します。|既定値は、none です。|  
|ErrorThreshold|VT_BSTR|ログイン エラーの最大数を指定します。 アダプターが動作を継続し、イベント ログで、イベントを記録場合は、アダプターが回復します。|有効な値は 1 ~ 1000 です。|既定値は 10 です。|  
|セグメント化|VT_BSTR|MQSeries がセグメント化されたメッセージをアセンブルまたはメッセージを取得するかどうかを指定します。|有効な値は、<br /><br /> -none<br />-完了|セグメント化を有効にすることがなく、MQSeries キューからメッセージを読み取る none を指定します。<br /><br /> アダプターに渡す前にセグメント化されたメッセージをアセンブルする完全なを指定します。<br /><br /> 既定値は、none です。|  
|順序付け|VT_BSTR|MQSeries キューから受信するときに、MQSeries がメッセージの順序を維持かどうかを指定します。|有効な値は、<br /><br /> -なし<br />-   noStop<br />-   yesStop<br />場合は、yesSuspend|メッセージの順序を無視するを指定します。<br /><br /> メッセージの順序を無視して、エラーがある場合は、受信場所を無効にする、noStop を指定します。<br /><br /> 順序付けを有効にする場合は、yesStop を指定します。 このオプションは、トランザクションを終了し、エラーがある場合は、受信場所を無効にします。<br /><br /> 順序付けを有効にする場合は、yesSuspend を指定します。 このオプションは、エラーがある場合に、メッセージを保留キューに移動します。 ユーザーは、エラーがある場合に、この値には順序は保持されませんがメッセージの受信を継続して受信場所では許可します。<br /><br /> 既定値はありません。|  
  
 次のコードでは、プロパティの設定に使用する文字列の形式を示します。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>MQS://TESTMQServer/DQM1/RQ0</uri><queueDetails>TESTMQServer/DQM1/RQ0</queueDetails><transactionSupported>yes</transactionSupported><suspendAsNonResumable>no</suspendAsNonResumable><dataOffsetForHeaders>yes</dataOffsetForHeaders><pollingInterval>1</pollingInterval><pollingUnit>seconds</pollingUnit><maximumBatchSize>100</maximumBatchSize><maximumNumberOfMessages>100</maximumNumberOfMessages><threadCount>2</threadCount><fragmentationSize>500</fragmentationSize><characterSet>none</characterSet><errorThreshold>10</errorThreshold><segmentation>none</segmentation><ordered>no</ordered></Config></AdapterConfig></CustomProps>  
```  
  
 MQSeries アダプターの設定できる構成プロパティ送信ポートに次の表に示します。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|Uri|VT_BSTR|データを送信する場所の完全なパスを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
|queueDetails|VT_BSTR|サーバー、キュー マネージャー、およびキューを含むターゲットの MQSeries キューに関する情報を指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|このプロパティの MQS が付きます。//、uri プロパティを作成します。|  
|transactionSupported|VT_BSTR|MQSeries アダプターが BizTalk Server と MQSeries Server 間の Microsoft 分散トランザクション コーディネーター (DTC) トランザクションを開始するかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|設定した場合にないメッセージ配信の保証はありません。<br /><br /> 既定値は、yes です。|  
|dataConversion|VT_BSTR|メッセージを MQSeries for Windows server の ANSI コード ページに変換するかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値はありません。|  
|segmentationAllowed|VT_BSTR|超える MQSeries キューのメッセージの最大長を個々 のメッセージの場合は、MQSeries キュー マネージャーのセグメント化を使用するかどうかを指定します。|有効な値は次のとおりです。<br /><br /> -[はい]<br />-なし|既定値はありません。|  
|fragmentationSize|VT_BSTR|アダプターと MQSAgent との間でデータが送信されるときは、キロバイト (KB) メッセージのメッセージ チャンク サイズを指定します。|有効な値は 1 ~ 1048576 です。|既定値は、500 です。|  
|順序付け|VT_BSTR|MQSeries キューに送信されるとき、MQSeries がメッセージの順序を維持するかどうかを指定します。|有効な値は、<br /><br /> -[はい]<br />-なし|既定値はありません。|  
  
 次のコードでは、プロパティの設定に使用する文字列の形式を示します。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><uri>MQS://TESTMQServer/DQM1(QM1)/SQ0</uri><queueDetails>TESTMQServer/DQM1(QM1)/SQ0</queueDetails><transactionSupported>yes</transactionSupported><dataConversion>no</dataConversion><segmentationAllowed>no</segmentationAllowed><fragmentationSize>500</fragmentationSize><ordered>no</ordered></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  アダプター フレームワークを使用して構築されたアダプターに TransportTypeData 構成データを指定するときに使用される名前と値のペアすべてに格納、 \<AdapterConfig\>要素。 以降、 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データを入力し、 \< \>データ内の文字をエスケープする必要があります。