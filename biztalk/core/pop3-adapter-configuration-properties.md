---
title: "POP3 アダプター構成プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, adapters
- POP3 adapters, receive locations
- POP3 adapters, code sample
- POP3 adapters, properties
ms.assetid: e30c848d-afff-42f3-8162-c7ea8c7e3b9a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bf7aa17f36143f80a82f664dbabd257d7b924db
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="pop3-adapter-configuration-properties"></a>POP3 アダプター構成プロパティ
次の表に、POP3 アダプターの受信場所に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|mailServer|VT_BSTR|POP3 アダプターによってポーリングされるメールボックスが存在する POP3 メール サーバーを指定します。|なし|なし|  
|serverPort|VT_BSTR|POP3 メール サーバーのポートを指定します。|有効な値は、0 から 65535 までです。|値を 0 に設定すると、sslRequired プロパティが false に設定されている場合は既定の POP3 ポートであるポート 110 が使用され、sslRequired プロパティが true に設定されている場合はポート 995 が使用されます。<br /><br /> 既定値は 0 です。|  
|userName|VT_BSTR|POP3 サーバーでの認証に使用するユーザー名を指定します。|なし|なし|  
|パスワード|VT_BSTR|POP3 サーバーでの認証に使用するユーザーのパスワードを指定します。|バインド ファイルをエクスポートする場合、この値は常にマスクされます。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このフィールドにパスワードを手動で設定する必要があります。|なし|  
|authenticationScheme|VT_BSTR|接続先のサーバーで使用する認証の種類を指定します。|有効な値は、<br /><br /> -基本<br />ダイジェスト<br />-SPA|このプロパティの既定値はありません。|  
|sslRequired|VT_BSTR|接続先のサーバーとの通信に SSL を使用するかどうかを指定します。|有効な値は、<br /><br /> 場合は true。<br />-false|既定値は false です。|  
|applyMIME|VT_BSTR|POP3 アダプターが受け取るメッセージに MIME デコードを適用するかどうかを指定します。|有効な値は、<br /><br /> 場合は true。<br />-false|既定値は、true です。|  
|bodyPartContentType|VT_BSTR|BizTalk Server に送信する電子メールの受信メッセージのボディ部のコンテンツの種類を指定します。|有効な値は、<br /><br /> -本文<br />-テキスト/xml<br />-テキスト/プレーン<br />-テキスト/|このプロパティの既定値はありません。|  
|bodyPartIndex|VT_BSTR|BizTalk Server に送信する電子メールの受信メッセージのボディ部を指定します。|有効な値は、0 128 です。|既定値は 0 です。|  
|errorThreshold|VT_BSTR|アダプターをシャットダウンするまでに許可するネットワーク エラーまたはプロトコル エラーの最大数を指定します。|有効な値は 0 ~ 4294967295 です。|アダプターがシャットダウンしないようにするには、値 0 を指定します。<br /><br /> 既定値は 10 です。|  
|pollingInterval|VT_BSTR|POP3 サーバーからメッセージを取得する処理の間隔を指定します。|有効な値は、<br /><br /> 場合は、120 に pollingUnitOfMeasure の値が 1 日です。<br />場合は、2880 に pollingUnitOfMeasure の値が 1 時間です。<br />場合は、172800 に pollingUnitOfMeasure の値が 1 分です。<br />場合は、10368000 に 2 から pollingUnitOfMeasure の値は秒です。|既定値は 5 です。|  
|pollingUnitOfMeasure|VT_BSTR|pollingInterval プロパティに指定された値と組み合わせて使用する単位を指定します。|有効な値は、<br /><br /> 日<br />-時間<br />-(分)<br />秒数|既定値は分です。|  
|uri|VT_BSTR|受信場所で監視するメールボックスへの完全なパスを指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。|なし|  
  
 次のコードは、プロパティの設定に使用する文字列の形式を示しています。  
  
```  
<CustomProps><AdapterConfig vt="8"><Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema"><mailServer>test.microsoft.com</mailServer><serverPort>0</serverPort><userName>testuser</userName><password>******</password><authenticationScheme>Basic</authenticationScheme><sslRequired>false</sslRequired><applyMIME>true</applyMIME><bodyPartContentType>text/xml</bodyPartContentType><bodyPartIndex>1</bodyPartIndex><errorThreshold>10</errorThreshold><pollingInterval>5</pollingInterval><pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure><uri>POP3://test.microsoft.com#testuser</uri></Config></AdapterConfig></CustomProps>  
```  
  
> [!NOTE]
>  アダプター フレームワークを使用して構築されたアダプターに TransportTypeData 構成データを指定するときに使用される名前/値ペア必要がありますすべてに格納される、 \<AdapterConfig > 要素。 \<AdapterConfig > 要素は VT_BSTR を指定します (vt =「8」) データを入力し、 \< \>データ内の文字をエスケープする必要があります。