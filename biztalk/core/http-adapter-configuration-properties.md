---
title: HTTP アダプター構成プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, properties
- receive locations, adapters
- HTTP adapters, code sample
- HTTP adapters, send ports
- HTTP adapters, receive locations
- send ports, adapters
ms.assetid: 3d4e9d88-ea40-4478-a0cf-77057fadd3b2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a2388a442923674f9b0eea52ffba1ed09a7b2e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332844"
---
# <a name="http-adapter-configuration-properties"></a>HTTP アダプター構成プロパティ
次の表を HTTP アダプターの設定できる構成プロパティには、場所が表示されます。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|ReturnCorrelationHandle|VT_BOOL|成功すると、受信場所から送信すること、送信されたメッセージの関連付けトークンをクライアントに HTTP 応答で指定します。|このプロパティは、一方向の受信場所に対してのみ有効です。<br /><br /> 有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|なし|  
|ResponseContentType|VT_BSTR|受信場所からクライアントに返送される HTTP 応答メッセージのコンテンツの種類を指定します。|このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> 最小長:0<br /><br /> 最大長:256|既定値は、テキストまたは xml です。|  
|SuspendFailedRequests|VT_BOOL|受信処理に失敗した HTTP 要求を中断するかどうかを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|0 (false) の値は、失敗した要求は破棄され、エラー状態コード (401 または 500) をクライアントに送信することを示します。<br /><br /> -1 (true) の値は、失敗した要求を中断し、「受理」状態を送信する方法の 1 つのクライアントにコード (200) の受信ポートまたは受信ポートを 2 つの方法については、クライアントに「エラー」状態コード (500) を示します。<br /><br /> 既定値は 0 (false です)。|  
|UseSSO|VT_BOOL|エンタープライズ シングル サインオンが使用されることを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
|ループバック|VT_BOOL|この場所で受信した要求メッセージがルーティングされることを指定する送信ポートまたはこの受信場所の応答として送信します。|このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> 有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
  
 次のコードでは、プロパティの設定に使用する XML 文字列の形式を示します。  
  
```  
<CustomProps>  
<ReturnCorrelationHandle vt="11">-1</ReturnCorrelationHandle>  
<ResponseContentType vt="8">text/xml</ResponseContentType>  
<SuspendFailedRequests vt="11">-1</SuspendFailedRequests>  
<UseSSO vt="11">-1</UseSSO>  
<LoopBack vt="11">-1</LoopBack>  
</CustomProps></  
```  
  
 HTTP アダプターの設定できる構成プロパティ送信ポートに次の表に示します。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|ProxyPort|VT_I4|この送信ポートのプロキシ サーバー ポートを指定します。|有効な値は、0 から 65535 までです。|UseProxy が 0 (false) に設定されている場合、このプロパティは、値を必要ありません。<br /><br /> 既定値は 80 です。|  
|RequestTimeout|VT_I4|HTTP/HTTPS 送信のタイムアウトを秒単位で指定します。|有効な値は 0 ~ max_long です。|この時間内に HTTP アダプタが応答を受信しない場合、サービスによりエラーがログに記録され、再試行インフラストラクチャに基づいてメッセージが再送信されます。<br /><br /> かどうか 0 に設定すると、BizTalk メッセージング エンジン計算要求メッセージのサイズに基づいて、タイムアウトします。 値を設定しないと、ハンドラの値が使用されます。|  
|Certificate|VT_BSTR|SSL (Secure Sockets Layer) 接続の確立に使用するクライアント証明書の拇印を指定します。|最小長:0<br /><br /> 最大長:59|既定値は空です。|  
|AuthenticationScheme|VT_BSTR|接続先のサーバーで使用する認証の種類を指定します。|有効な値は、<br /><br /> 匿名<br />-基本<br />-ダイジェスト<br />-Kerberos|既定値には Anonymous です。|  
|Username|VT_BSTR|移行先サーバーでの認証に使用するユーザー名を指定します。|このプロパティには、値がある場合、AuthenticationScheme の基本的なダイジェストを使用すると、やエンタープライズ シングル サインオンは使用されません。<br /><br /> 最小長:0<br /><br /> 最大長:256|なし|  
|EnableChunkedEncoding|VT_BOOL|チャンク エンコードを使用するために指定します。|プロキシを使用する、HTTP 送信ハンドラが構成されている場合、チャンク エンコードは無効に暗黙的にです。<br /><br /> 有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|このオプションを有効にすると、HTTP アダプターは HTTP チャンク エンコード 8 Kb のチャンクの最大サイズを使用します。<br /><br /> 既定値は 0 (false です)。|  
|UseProxy|VT_BOOL|HTTP 送信ハンドラーがプロキシ サーバーを使用するかどうかを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
|ProxyName|VT_BSTR|この送信ポートのプロキシ サーバー アドレスを指定します。|最小長:0<br /><br /> 最大長:256|UseProxy が 0 (false) に設定されている場合、このプロパティは、値を必要ありません。|  
|UseSSO|VT_BOOL|接続先のサーバーでの認証でクライアントの資格情報を取得する際に、シングル サインオンを使用するかどうかを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
|パスワード|VT_NULL|移行先サーバーでの認証に使用するパスワードを指定します。|このプロパティには、値がある場合、AuthenticationScheme の基本的なダイジェストを使用すると、やエンタープライズ シングル サインオンは使用されません。<br /><br /> この値は常に、バインド ファイルをエクスポートする場合は null に設定します。 このフィールドは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。<br /><br /> 最小長:0<br /><br /> 最大長:256|このプロパティの型を VT_BSTR に設定 (vt =「8」) このフィールドの値を指定する場合は、バインド ファイルをインポートする前にします。|  
|MaxRedirects|VT_I4|送信されるメッセージに許可されるリダイレクトの最大数を指定します。|有効な値は 0 ~ 10 です。|既定値は 5 です。|  
|ContentType|VT_BSTR|要求メッセージのコンテンツの種類を指定します。|最小長:0<br /><br /> 最大長:256|この値が設定されていない場合、ハンドラの値が使用されます。|  
|ProxyPassword|VT_NULL|プロキシ サーバーで認証に使用するユーザー パスワードを指定します。|この値は常に、バインド ファイルをエクスポートする場合は null に設定します。 このフィールドは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。<br /><br /> 最小長:0<br /><br /> 最大長:256|UseProxy が 0 (false) に設定されている場合、このプロパティは、値を必要ありません。|  
|ProxyUsername|VT_BSTR|プロキシ サーバーで認証のユーザー名を指定します。|最小長:0<br /><br /> 最大長:256|UseProxy が 0 (false) に設定されている場合、このプロパティは、値を必要ありません。|  
|UseHandlerSetting|VT_BOOL|送信ポートの構成が、HTTP 送信ハンドラーのプロキシ設定を使用する必要がありますを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は-1 (true です)。|  
  
 次のコードでは、プロパティの設定に使用する XML 文字列の形式を示します。  
  
```  
<CustomProps>  
<ProxyPort vt="3">80</ProxyPort>  
<RequestTimeout vt="3">60</RequestTimeout>  
<Certificate vt="8">A7 6D F9 06 5E FC 97 66 75 59 B5 D6 67 0C 84 DC 64 F5 BF B9</Certificate>  
<AuthenticationScheme vt="8">Basic</AuthenticationScheme>  
<Username vt="8">authenticateduser</Username>  
<EnableChunkedEncoding vt="11">-1</EnableChunkedEncoding>  
<UseProxy vt="11">-1</UseProxy>  
<ProxyName vt="8">proxyserver</ProxyName>  
<UseSSO vt="11">0</UseSSO>  
<Password vt="1" />  
<MaxRedirects vt="3">5</MaxRedirects>  
<ContentType vt="8">text/xml</ContentType>  
<ProxyPassword vt="1" />  
<ProxyUsername vt="8">proxyuser</ProxyUsername>  
<UseHandlerSetting vt="11">0</UseHandlerSetting>  
</CustomProps>  
```