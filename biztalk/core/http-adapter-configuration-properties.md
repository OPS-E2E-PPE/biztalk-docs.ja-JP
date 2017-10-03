---
title: "HTTP アダプター構成プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, properties
- receive locations, adapters
- HTTP adapters, code sample
- HTTP adapters, send ports
- HTTP adapters, receive locations
- send ports, adapters
ms.assetid: 3d4e9d88-ea40-4478-a0cf-77057fadd3b2
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 731f08106c698d50e95c36b8325cc3d92aa0debb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-configuration-properties"></a>HTTP アダプター構成プロパティ
次の表に、HTTP アダプターの受信場所に設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|ReturnCorrelationHandle|VT_BOOL|成功時に、クライアントに対する HTTP 応答で送信されたメッセージの関連付けトークンを受信場所から送信することを指定します。|このプロパティは、一方向の受信場所に対してのみ有効です。<br /><br /> 有効な値は、<br /><br /> -1 (true)<br />-0 (false)|なし|  
|ResponseContentType|VT_BSTR|受信場所からクライアントに返送される HTTP 応答メッセージのコンテンツの種類を指定します。|このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> 最小長: 0<br /><br /> 最大長: 256|既定値は、text/xml です。|  
|SuspendFailedRequests|VT_BOOL|受信処理に失敗した HTTP 要求を中断するかどうかを指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|値を 0 (false) に設定すると、失敗した要求は破棄され、エラー状態コード (401 または 500) がクライアントに送信されます。<br /><br /> 値を -1 (true) に設定すると、失敗した要求は中断されます。また、一方向の受信ポートの場合はクライアントに "受理" 状態コード (200) が送信され、双方向の受信ポートの場合はクライアントに "エラー" 状態コード (500) が送信されます。<br /><br /> 既定値は 0 (false) です。|  
|UseSSO|VT_BOOL|エンタープライズ シングル サインオンを使用するように指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
|LoopBack|VT_BOOL|この場所で受信した要求メッセージをルーティングすることを指定したり、送信ポートをこの受信場所での応答として送信します。|このプロパティは、要求 - 応答の受信場所に対してのみ有効です。<br /><br /> 有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
  
 次のコード例は、プロパティの設定に使用する XML 文字列の形式を示しています。  
  
```  
<CustomProps>  
<ReturnCorrelationHandle vt="11">-1</ReturnCorrelationHandle>  
<ResponseContentType vt="8">text/xml</ResponseContentType>  
<SuspendFailedRequests vt="11">-1</SuspendFailedRequests>  
<UseSSO vt="11">-1</UseSSO>  
<LoopBack vt="11">-1</LoopBack>  
</CustomProps></  
```  
  
 次の表に、HTTP アダプターの送信ポートに設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|ProxyPort|VT_I4|この送信ポートのプロキシ サーバー ポートを指定します。|有効な値は、0 から 65535 までです。|UseProxy プロパティが 0 (false) に設定されている場合、このプロパティの値は必要ありません。<br /><br /> 既定値は 80 です。|  
|RequestTimeout|VT_I4|HTTP/HTTPS 送信のタイムアウトを秒単位で指定します。|有効値は、0 ～ MAX_LONG です。|この時間内に HTTP アダプタが応答を受信しない場合、サービスによりエラーがログに記録され、再試行インフラストラクチャに基づいてメッセージが再送信されます。<br /><br /> 0 に設定されている場合、タイムアウト値は要求メッセージのサイズを基準に計算されます。 値を設定しないと、ハンドラの値が使用されます。|  
|Certificate|VT_BSTR|SSL (Secure Sockets Layer) 接続の確立に使用するクライアント証明書の拇印を指定します。|最小長: 0<br /><br /> 最大長: 59|既定値は空です。|  
|AuthenticationScheme|VT_BSTR|接続先のサーバーで使用する認証の種類を指定します。|有効な値は、<br /><br /> 匿名<br />-基本<br />ダイジェスト<br />Kerberos|既定値は "Anonymous" です。|  
|[ユーザー名]|VT_BSTR|接続先のサーバーで認証に使用するユーザー名を指定します。|[基本] または [ダイジェスト] の AuthenticationScheme が使用されており、かつエンタープライズ シングル サインオンが使用されていない場合は、このプロパティに値を設定する必要があります。<br /><br /> 最小長: 0<br /><br /> 最大長: 256|なし|  
|EnableChunkedEncoding|VT_BOOL|チャンク エンコードを使用するために指定します。|HTTP 送信ハンドラーで [プロキシを使用する] を有効にしている場合、チャンク エンコードは暗黙的に無効になります。<br /><br /> 有効な値は、<br /><br /> -1 (true)<br />-0 (false)|このオプションが有効になっている場合、HTTP アダプターは HTTP チャンク エンコードが 8 Kb の最大チャンク サイズを使用します。<br /><br /> 既定値は 0 (false) です。|  
|UseProxy|VT_BOOL|HTTP 送信ハンドラーがプロキシ サーバーを使用するかどうかを指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
|ProxyName|VT_BSTR|この送信ポートのプロキシ サーバー アドレスを指定します。|最小長: 0<br /><br /> 最大長: 256|UseProxy プロパティが 0 (false) に設定されている場合、このプロパティの値は必要ありません。|  
|UseSSO|VT_BOOL|接続先のサーバーでの認証でクライアントの資格情報を取得する際に、シングル サインオンを使用するかどうかを指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
|Password|VT_NULL|接続先サーバーでの認証に使用するパスワードを指定します。|[基本] または [ダイジェスト] の AuthenticationScheme が使用されており、かつエンタープライズ シングル サインオンが使用されていない場合は、このプロパティに値を設定する必要があります。<br /><br /> バインド ファイルをエクスポートする場合は、この値を必ず Null に設定します。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このフィールドにパスワードを手動で設定する必要があります。<br /><br /> 最小長: 0<br /><br /> 最大長: 256|このフィールドに値を指定した場合は、このプロパティの型を VT_BSTR (vt="8") に設定してからバインド ファイルをインポートします。|  
|MaxRedirects|VT_I4|送信されるメッセージに許可されるリダイレクトの最大数を指定します。|有効な値は、0 10 からです。|既定値は 5 です。|  
|ContentType|VT_BSTR|要求メッセージのコンテンツの種類を指定します。|最小長: 0<br /><br /> 最大長: 256|この値が設定されていない場合、ハンドラの値が使用されます。|  
|ProxyPassword|VT_NULL|プロキシ サーバーで認証に使用するユーザー パスワードを指定します。|バインド ファイルをエクスポートする場合は、この値を必ず Null に設定します。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このフィールドにパスワードを手動で設定する必要があります。<br /><br /> 最小長: 0<br /><br /> 最大長: 256|UseProxy プロパティが 0 (false) に設定されている場合、このプロパティの値は必要ありません。|  
|ProxyUsername|VT_BSTR|プロキシ サーバーで認証のユーザー名を指定します。|最小長: 0<br /><br /> 最大長: 256|UseProxy プロパティが 0 (false) に設定されている場合、このプロパティの値は必要ありません。|  
|UseHandlerSetting|VT_BOOL|送信ポートの構成で、HTTP 送信ハンドラーに指定したプロキシ設定を使用することを指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は -1 (true) です。|  
  
 次のコード例は、プロパティの設定に使用する XML 文字列の形式を示しています。  
  
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