---
title: "HTTP アダプター プロパティ スキーマおよびプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AffiliateApplicationName property [HTTP adapters]
- Certificate property [HTTP adapters]
- Password property [HTTP adapters]
- HTTP adapters, properties
- InboundHttpHeaders property [HTTP adapters]
- UseHandlerProxySettings property [HTTP adapters]
- configuring [HTTP adapters], properties
- schemas, HTTP adapters
- RequestTimeout property [HTTP adapters]
- ProxyPassword property [HTTP adapters]
- UseSSO property [HTTP adapters]
- HTTP adapters, schemas
- AuthenticationScheme property [HTTP adapters]
- ProxyName property [HTTP adapters]
- ProxyPort property [HTTP adapters]
- UseProxy property [HTTP adapters]
- configuring [HTTP adapters], schemas
- ContentType property [HTTP adapters]
- MaxRedirects property [HTTP adapters]
- ProxyUsername property [HTTP adapters]
- UserName property, HTTP adapters
ms.assetid: c9b50a82-8cb1-4521-9cf3-5fd77a3531e1
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 416ad39e804a4907dc39c7cef941e9a1bb57d3dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-property-schema-and-properties"></a>HTTP アダプター プロパティ スキーマおよびプロパティ
HTTP アダプタ プロパティ スキーマのプロパティを次の表に示します。  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/http-properties  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|**ProxyName**|xs:string|プロキシ サーバーの名前を指定します。|  
|**ProxyPort**|xs:int|プロキシ サーバーのポートを指定します。|  
|**UseHandlerProxySettings**|xs:boolean|HTTP 送信ポートでハンドラのプロキシ構成を使用するかどうかを指定します。|  
|**UseProxy**|xs:boolean|HTTP アダプタでプロキシ サーバーを使用するかどうかを指定します。|  
|**RequestTimeout**|xs:int|サーバーからの応答を待機する際のタイムアウト値です。 ゼロ (0) に設定されている場合、タイムアウト値は要求メッセージのサイズを基準に計算されます。|  
|**ユーザー名**|xs:string|サーバーでの認証に使用するユーザー名です。|  
|**Password**|xs:string|サーバーでの認証に使用するユーザーのパスワードです。|  
|**ProxyUsername**|xs:string|プロキシ サーバーで認証のユーザー名を指定します。|  
|**ProxyPassword**|xs:string|プロキシ サーバーで認証用のユーザー パスワードを指定します。|  
|**MaxRedirects**|xs:int|HTTP アダプタで要求をリダイレクトする最大回数です。|  
|**ContentType**|xs:string|要求メッセージのコンテンツの種類です。|  
|**AuthenticationScheme**|xs:string|接続先のサーバーで使用する認証の種類です。|  
|**[MSSQLSERVER のプロトコルのプロパティ]**|xs:string|SSL クライアント証明書の拇印です。|  
|**UseSSO**|xs:boolean|HTTP 送信ポートで SSO を使用するかどうかを指定します。|  
|**AffiliateApplicationName**|xs:string|SSO に使用する関連アプリケーションの名前です。|  
|**InboundHttpHeaders**|xs:string|受信した HTTP 要求の HTTP ヘッダーを表します。|  
|**SubmissionHandle**|xs:string|要求メッセージの BizTalk Server 関連付けトークン (GUID) を表します。|  
|**EnableChunkedEncoding**|xs:boolean|HTTP アダプターで使用されてエンコード チャンクかどうかを指定します。|  
|**UserHttpHeaders**|xs:string|HTTP の要求メッセージまたは応答メッセージに含まれているカスタマイズされたヘッダーを表します。<br /><br /> 値、 **UserHttpHeaders**プロパティは、次の形式である必要があります。<br /><br /> `Header1: value\r\nHeader2: value\r\n`<br /><br /> **注**コロン (:) と、ヘッダーと値の間のスペース文字 () に配置します。 ヘッダーが空の場合、エントリは表示されません。空の値は問題ありません。<br /><br /> 使用して次の 5 つの標準 HTTP ヘッダーを変更することができます、 **UserHttpHeaders**プロパティ。<br /><br /> Accept します。<br /><br /> -参照元<br /><br /> -期待します。<br /><br /> 場合の変更-以降<br /><br /> -ユーザー エージェント|  
  
## <a name="see-also"></a>参照  
 [HTTP アダプタの構成](../core/configuring-the-http-adapter.md)