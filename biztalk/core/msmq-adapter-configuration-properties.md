---
title: MSMQ アダプター構成プロパティ |Microsoft Docs
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
ms.openlocfilehash: 66c6e2345044b9fbd43bbb3fce4e0c8cf265ce72
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531162"
---
# <a name="msmq-adapter-configuration-properties"></a>MSMQ アダプター構成プロパティ
次の表の MSMQ アダプターに対して設定できる構成プロパティには、場所が表示されます。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|queue|VT_BSTR|受信場所で監視する場所への有効なキューのパスを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
|batchSize|VT_BSTR|メッセージ ボックス データベースにメッセージのバッチを送信するときに、MSMQ アダプターを使用してバッチ サイズを指定します。|有効な値は 1 ~ 4294967295 です。|既定値は、20 です。|  
|transactional|VT_BSTR|Microsoft 分散トランザクション (MSDTC) のコンテキストで元のキューからメッセージを読み取るかどうかを指定します。|有効な値は、<br /><br /> -true<br />-false<br /><br /> アダプターは、リモート キューのトランザクションの読み込みをサポートしていません。|既定値は false です。|  
|serialProcessing|VT_BSTR|順序でメッセージを処理するかどうかを指定します。|有効な値は、<br /><br /> -true<br />-false|既定値は false です。|  
|onFailure|VT_BSTR|アダプターがエラーに応答する方法を指定します。|有効な値は、<br /><br /> -   stopOnFailure<br />-   suspendNonResumable<br />-   suspendResumable|既定値は、suspendresumable です。|  
|Uri|VT_BSTR|受信場所で監視するキューへの完全パスを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
  
 次のコードでは、プロパティの設定に使用する文字列の形式を示します。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><queue>FORMATNAME:DIRECT=OS:.\PRIVATE$\QUEUE</queue><batchSize>20</batchSize><transactional>false</transactional><serialProcessing>false</serialProcessing><onFailure>suspendResumable</onFailure><uri>FORMATNAME:DIRECT=OS:.\PRIVATE$\QUEUE</uri></Config></AdapterConfig></CustomProps>  
```  
  
 MSMQ アダプターの設定できる構成プロパティ送信ポートに次の表に示します。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|キュー|VT_BSTR|送信先キューを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
|maximumMessageSiz|VT_BSTR|指定したキューに送信するメッセージの最大メッセージ サイズをキロバイト (KB) 単位を指定します。|有効な値は 1 ~ 4294967295 segmentationSupport および transactional に設定する場合は true。 それ以外の場合、有効な値は 1 ~ 4095 です。|既定値は 1024 にします。|  
|acknowledgeType|VT_BSTR|1 つまたは複数の受信確認の種類を指定します。|有効な値は、.NET のメンバー **System.Messaging.AcknowledgeTypes**列挙体。|既定値は、None です。|  
|administrationQueue|VT_BSTR|MSMQ 管理キューを指定します。|なし|なし|  
|timeOut|VT_BSTR|送信先キューにメッセージが到達するまでの最大待機時間を指定します。|このプロパティは、transactional プロパティが設定されている場合にのみ適用されます。 true に設定します。<br /><br /> -TimeOutUnits の値の日を指定するときに、有効な値は 1 ~ 10675199 が。<br />-有効な値は、時間の timeOutUnits の値を指定するときに、1 ~ 596523 は。<br />-TimeOutUnits の値の分を指定するときに、有効な値は 1 ~ 35791394 が。<br />-TimeOutUnits の値の秒を指定するときに、有効な値は 1 ~ 2147483647 ですが。|なし|  
|priority|VT_BSTR|メッセージの優先順位を指定します。|有効な値は、.NET のメンバー **System.Messaging.MessagePriority**列挙体。|なし|  
|recoverable|VT_BSTR|メッセージの回復可能性を保証するかどうかを指定します。|有効な値は、<br /><br /> -true<br />-false|既定値は false です。|  
|encryptionAlgorithm|VT_BSTR|使用する暗号化アルゴリズムを指定します。|有効な値は、.NET のメンバー **System.Messaging.EncryptionAlgorithm**列挙体。|既定値は、None です。|  
|useAuthentication|VT_BSTR|認証を使用するかどうかを指定します。|証明書のプロパティと組み合わせてこのプロパティを使用して、メッセージを確認します。 キューにアクセスするのにには、ユーザー名とパスワードのプロパティを使用します。|なし|  
|証明書 (certificate)|VT_BSTR|メッセージの確認に使用する証明書を指定します。|40 文字の証明書の拇印を入力します。|なし|  
|segmentationSupport|VT_BSTR|セグメント化をサポートするかどうかを指定します。|有効な値は、<br /><br /> -true<br />-false|既定値は false です。|  
|transactional|VT_BSTR|Microsoft 分散トランザクション (MSDTC) のコンテキストでのメッセージの送信をサポートするかどうかを指定します。|有効な値は、<br /><br /> -true<br />-false|既定値は false です。|  
|useJournalQueue|VT_BSTR|メッセージが処理されるたびに、メッセージのコピーを保存するかどうかを指定します。|有効な値は、<br /><br /> -true<br />-false|既定値は false です。|  
|useDeadLetterQueue|VT_BSTR|かどうか発生する場合、エラー、配信不能キューにメッセージを送信するかを指定します。|有効な値は、<br /><br /> -true<br />-false|既定値は true です。|  
|ackTypeEnumsValue|VT_BSTR|指定した acknowledgeType 値に関連付けられている値のビットごとの OR を指定します。|なし|既定値は 0 です。|  
|timeOutUnits|VT_BSTR|TimeOut プロパティに指定された値と組み合わせて使用する単位を指定します。|有効な値は、<br /><br /> 日<br />-時間<br />-分<br />秒数|既定値は [日] です。|  
|userName|VT_BSTR|リモート キューのユーザー名を指定します。|既定値は空です。|  
|password|VT_BSTR|リモート キューにアクセスするために userName プロパティに指定された値と組み合わせて使用するパスワードを指定します。|バインド ファイルをエクスポートするときにこの値は常にマスクされます。 このフィールドは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。|既定値は空です。|  
|BodyType|VT_BSTR|MSMQ のメッセージ本文の種類を指定します。|有効な値は、.NET のメンバー **VarEnum**列挙体。|既定値は、8209 です。|  
|Uri|VT_BSTR|送信先キューへの完全パスを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
  
 次のコードでは、プロパティの設定に使用する文字列の形式を示します。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><queue>FORMATNAME:DIRECT=OS:TESTSERVER\PRIVATE$\DESTQUEUE</queue><maximumMessageSize>1024</maximumMessageSize><acknowledgeType>None</acknowledgeType><administrationQueue>Direct=OS:TestServer\Private$\AdminQueue</administrationQueue><timeOut>4</timeOut><priority>Normal</priority><recoverable>false</recoverable><encryptionAlgorithm>None</encryptionAlgorithm><useAuthentication>false</useAuthentication><segmentationSupport>false</segmentationSupport><transactional>false</transactional><useJournalQueue>false</useJournalQueue><useDeadLetterQueue>true</useDeadLetterQueue><ackTypeEnumsValue>0</ackTypeEnumsValue><timeOutUnits>Days</timeOutUnits><userName>TestUser</userName><password>******</password><bodyType>8209</bodyType><uri>FORMATNAME:DIRECT=OS:TESTSERVER\PRIVATE$\DESTQUEUE</uri></Config></AdapterConfig>  
```  
  
> [!NOTE]
>  アダプター フレームワークを使用して構築されたアダプターに TransportTypeData 構成データを指定するときに使用される名前と値のペアすべてに格納、 \<AdapterConfig\>要素。 以降、 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データを入力し、 \< \>データ内の文字をエスケープする必要があります。