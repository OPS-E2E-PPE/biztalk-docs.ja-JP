---
title: POP3 アダプター構成プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, adapters
- POP3 adapters, receive locations
- POP3 adapters, code sample
- POP3 adapters, properties
ms.assetid: e30c848d-afff-42f3-8162-c7ea8c7e3b9a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3ca7c44230e47e1aeccd415630d4153ae5f4eb6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394925"
---
# <a name="pop3-adapter-configuration-properties"></a>POP3 アダプター構成プロパティ
次の表の POP3 アダプターを設定できる構成プロパティには、場所が表示されます。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|mailServer|VT_BSTR|POP3 アダプターによってポーリングされるメールボックスが存在する POP3 メール サーバーを指定します。|なし|なし|  
|serverPort|VT_BSTR|POP3 メール サーバーのポートを指定します。|有効な値は、0 から 65535 までです。|0 の値は、sslRequired プロパティが false に設定されている場合は、既定の POP3 ポート 110 を使用するか、sslRrequired プロパティが設定されている場合はポート 995 を示します。 true に設定します。<br /><br /> 既定値は 0 です。|  
|userName|VT_BSTR|POP3 サーバーで認証に使用するユーザー名を指定します。|なし|なし|  
|password|VT_BSTR|POP3 サーバーで認証に使用するユーザーのパスワードを指定します。|バインド ファイルをエクスポートするときにこの値は常にマスクされます。 このフィールドは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。|なし|  
|authenticationScheme|VT_BSTR|接続先のサーバーで使用する認証の種類を指定します。|有効な値は、<br /><br /> -基本<br />-ダイジェスト<br />SPA|このプロパティの既定値はありません。|  
|sslRequired|VT_BSTR|移行先サーバーとの通信に SSL を使用するかどうかを指定します。|有効な値は、<br /><br /> -true<br />-false|既定値は false です。|  
|applyMIME|VT_BSTR|POP3 アダプターで受信したメッセージに MIME デコードを適用するかどうかを指定します。|有効な値は、<br /><br /> -true<br />-false|既定値は true です。|  
|bodyPartContentType|VT_BSTR|BizTalk Server に送信する電子メールの受信メッセージのボディ部のコンテンツの種類を指定します。|有効な値は、<br /><br /> -本文<br />-   text/xml<br />-テキスト/プレーン<br />-テキスト/|このプロパティの既定値はありません。|  
|bodyPartIndex|VT_BSTR|BizTalk Server に送信する電子メールの受信メッセージのボディ部を指定します。|有効な値は、0 128 です。|既定値は 0 です。|  
|ErrorThreshold|VT_BSTR|アダプターをシャット ダウンするまで待機するネットワークまたはプロトコル エラーの最大数を指定します。|有効な値は 0 ~ 4294967295 です。|アダプターがシャット ダウンするを防ぐために 0 の値を指定します。<br /><br /> 既定値は 10 です。|  
|PollingInterval|VT_BSTR|POP3 サーバーからメッセージを取得試行の間隔を指定します。|有効な値は、<br /><br /> 場合は、120 に pollingUnitOfMeasure の値が 1 日です。<br />1 ~ 2880 場合元 pollingUnitOfMeasure の値は時間です。<br />1 ~ 172800 場合元 pollingUnitOfMeasure の値は分です。<br />2 ~ 10368000 場合元 pollingUnitOfMeasure の値は秒です。|既定値は 5 です。|  
|pollingUnitOfMeasure|VT_BSTR|PollingInterval の値と組み合わせて使用する測定単位を指定します。|有効な値は、<br /><br /> 日<br />-時間<br />-分<br />秒数|既定値は、分です。|  
|Uri|VT_BSTR|受信場所で監視するメールボックスへの完全パスを指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。|なし|  
  
 次のコードでは、プロパティの設定に使用する文字列の形式を示します。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><mailServer>test.microsoft.com</mailServer><serverPort>0</serverPort><userName>testuser</userName><password>******</password><authenticationScheme>Basic</authenticationScheme><sslRequired>false</sslRequired><applyMIME>true</applyMIME><bodyPartContentType>text/xml</bodyPartContentType><bodyPartIndex>1</bodyPartIndex><errorThreshold>10</errorThreshold><pollingInterval>5</pollingInterval><pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure><uri>POP3://test.microsoft.com#testuser</uri></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  アダプター フレームワークを使用して構築されたアダプターに TransportTypeData 構成データを指定するときに使用される名前と値のペアすべてに格納、 \<AdapterConfig > 要素。 以降、 \<AdapterConfig > 要素は VT_BSTR を指定します (vt =「8」) データを入力し、 \< \>データ内の文字をエスケープする必要があります。