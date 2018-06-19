---
title: MSMQ アダプター構成プロパティ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, send ports
- receive locations, adapters
- MSMQ adapters, properties
- MSMQ adapters, code sample
- send ports, adapters
ms.assetid: d660d0ce-bff9-4bc5-be1d-38954c2fdbe2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 060d6fbfb75c97e4fa4bc6bbfc3f160972c437ff
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974552"
---
# <a name="msmq-adapter-configuration-properties"></a>MSMQ アダプター構成プロパティ
次の表に、MSMQ アダプターの受信場所に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|queue|VT_BSTR|受信場所で監視する場所への有効なキューのパスを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
|batchSize|VT_BSTR|メッセージのバッチをメッセージ ボックス データベースに送信するときに、MSMQ アダプターが使用するバッチ サイズを指定します。|有効な値は 1 ~ 4294967295 です。|既定値は 20 です。|  
|transactional|VT_BSTR|Microsoft 分散トランザクション コーディネーター (MSDTC) のコンテキストで、送信元のキューからメッセージを読み取るかどうかを指定します。|有効な値は、<br /><br /> 場合は true。<br />-false<br /><br /> アダプタは、リモート キューのトランザクションの読み込みをサポートしていません。|既定値は false です。|  
|serialProcessing|VT_BSTR|順序でメッセージを処理するかどうかを指定します。|有効な値は、<br /><br /> 場合は true。<br />-false|既定値は false です。|  
|onFailure|VT_BSTR|エラーに対するアダプターの対応方法を指定します。|有効な値は、<br /><br /> -stopOnFailure<br />-suspendNonResumable<br />-suspendresumable です|既定値は suspendResumable です。|  
|uri|VT_BSTR|受信場所で監視するキューへの完全なパスを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
  
 次のコードは、プロパティの設定に使用する文字列の形式を示しています。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><queue>FORMATNAME:DIRECT=OS:.\PRIVATE$\QUEUE</queue><batchSize>20</batchSize><transactional>false</transactional><serialProcessing>false</serialProcessing><onFailure>suspendResumable</onFailure><uri>FORMATNAME:DIRECT=OS:.\PRIVATE$\QUEUE</uri></Config></AdapterConfig></CustomProps>  
```  
  
 次の表に、MSMQ アダプターの送信ポートに設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|キュー|VT_BSTR|送信先キューを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
|maximumMessageSiz|VT_BSTR|指定したキューに送信するメッセージの最大サイズを KB 単位で指定します。|segmentationSupport および transactional が true に設定されている場合の有効値は、1 ～ 4294967295 です。 その他の場合の有効値は、1 ～ 4095 です。|既定値は 1024 です。|  
|acknowledgeType|VT_BSTR|1 つまたは複数の確認の種類を指定します。|有効な値は、.net メンバー **System.Messaging.AcknowledgeTypes**列挙します。|既定値は None です。|  
|administrationQueue|VT_BSTR|MSMQ 管理キューを指定します。|なし|なし|  
|timeOut|VT_BSTR|送信先キューにメッセージが到達するまでの最大待機時間を指定します。|このプロパティは、transactional プロパティが true に設定されている場合にのみ適用されます。<br /><br /> -TimeOutUnits の値の日を指定するときに、有効な値は 1 ~ 10675199 はします。<br />-有効な値は、timeOutUnits 時間の値を指定するときに、1 ~ 596523 はします。<br />-TimeOutUnits の値の分を指定するときに、有効な値は 1 ~ 35791394 はします。<br />-TimeOutUnits の値の秒を指定するときに、有効な値は 1 ~ 2147483647 はします。|なし|  
|priority|VT_BSTR|メッセージの優先度を指定します。|有効な値は、.net メンバー **System.Messaging.MessagePriority**列挙します。|なし|  
|recoverable|VT_BSTR|メッセージの回復可能性を保証するかどうかを指定します。|有効な値は、<br /><br /> 場合は true。<br />-false|既定値は false です。|  
|encryptionAlgorithm|VT_BSTR|使用する暗号化アルゴリズムを指定します。|有効な値は、.net メンバー **System.Messaging.EncryptionAlgorithm**列挙します。|既定値は None です。|  
|useAuthentication|VT_BSTR|認証を使用するかどうかを指定します。|メッセージを確認するには、certificate プロパティと組み合わせてこのプロパティを使用します。 キューにアクセスするには、userName プロパティおよび password プロパティを使用します。|なし|  
|証明書 (certificate)|VT_BSTR|メッセージの確認に使用する証明書を指定します。|40 文字の証明書の拇印を入力します。|なし|  
|segmentationSupport|VT_BSTR|セグメント化をサポートするかどうかを指定します。|有効な値は、<br /><br /> 場合は true。<br />-false|既定値は false です。|  
|transactional|VT_BSTR|Microsoft 分散トランザクション コーディネーター (MSDTC) のコンテキストで、メッセージの送信をサポートするかどうかを指定します。|有効な値は、<br /><br /> 場合は true。<br />-false|既定値は false です。|  
|useJournalQueue|VT_BSTR|メッセージを処理する場合に常にメッセージのコピーを保存するかどうかを指定します。|有効な値は、<br /><br /> 場合は true。<br />-false|既定値は false です。|  
|useDeadLetterQueue|VT_BSTR|障害が発生した場合に配信不能キューにメッセージを送信するかどうかを指定します。|有効な値は、<br /><br /> 場合は true。<br />-false|既定値は、true です。|  
|ackTypeEnumsValue|VT_BSTR|指定した acknowledgeType 値に関連付けられている値のビット単位の OR 演算を指定します。|なし|既定値は 0 です。|  
|timeOutUnits|VT_BSTR|timeOut プロパティに指定された値と組み合わせて使用する単位を指定します。|有効な値は、<br /><br /> 日<br />-時間<br />-(分)<br />秒数|既定値は [日] です。|  
|userName|VT_BSTR|リモート キューのユーザー名を指定します。|既定値は空です。|  
|パスワード|VT_BSTR|リモート キューにアクセスするために userName プロパティに指定した値と組み合わせて使用するパスワードを指定します。|バインド ファイルをエクスポートする場合、この値は常にマスクされます。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このフィールドにパスワードを手動で設定する必要があります。|既定値は空です。|  
|bodyType|VT_BSTR|MSMQ のメッセージ本文の種類を指定します。|有効な値は、.net メンバー **VarEnum**列挙します。|既定値は、8209 です。|  
|uri|VT_BSTR|送信先キューの完全なパスを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
  
 次のコードは、プロパティの設定に使用する文字列の形式を示しています。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><queue>FORMATNAME:DIRECT=OS:TESTSERVER\PRIVATE$\DESTQUEUE</queue><maximumMessageSize>1024</maximumMessageSize><acknowledgeType>None</acknowledgeType><administrationQueue>Direct=OS:TestServer\Private$\AdminQueue</administrationQueue><timeOut>4</timeOut><priority>Normal</priority><recoverable>false</recoverable><encryptionAlgorithm>None</encryptionAlgorithm><useAuthentication>false</useAuthentication><segmentationSupport>false</segmentationSupport><transactional>false</transactional><useJournalQueue>false</useJournalQueue><useDeadLetterQueue>true</useDeadLetterQueue><ackTypeEnumsValue>0</ackTypeEnumsValue><timeOutUnits>Days</timeOutUnits><userName>TestUser</userName><password>******</password><bodyType>8209</bodyType><uri>FORMATNAME:DIRECT=OS:TESTSERVER\PRIVATE$\DESTQUEUE</uri></Config></AdapterConfig>  
```  
  
> [!NOTE]
>  アダプター フレームワークを使用して構築されたアダプターに TransportTypeData 構成データを指定するときに使用される名前/値ペア必要がありますすべてに格納される、 \<AdapterConfig\>要素。 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データを入力し、 \< \>データ内の文字をエスケープする必要があります。