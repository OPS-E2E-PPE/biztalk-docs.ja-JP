---
title: HTTP アダプター プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2f4fdfbd082bb9bbb8e3a37355068b3c8d29c63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332890"
---
# <a name="http-adapter-property-schema-and-properties"></a>HTTP アダプター プロパティ スキーマおよびプロパティ
次の表は、HTTP アダプタ プロパティ スキーマのプロパティを一覧表示します。  
  
 **名前空間:** http://schemas.microsoft.com/BizTalk/2003/http-properties  
  
|名前|型|説明|  
|----------|----------|-----------------|  
|**ProxyName**|xs:string|プロキシ サーバーの名前を指定します。|  
|**ProxyPort**|xs:int|プロキシ サーバーのポートを指定します。|  
|**UseHandlerProxySettings**|xs:boolean|HTTP 送信ポートが、ハンドラーのプロキシ構成を使用するかどうかを指定します。|  
|**UseProxy**|xs:boolean|HTTP アダプタでプロキシ サーバーを使用するかどうかを指定します。|  
|**RequestTimeout**|xs:int|サーバーからの応答を待機する際のタイムアウト値です。 このプロパティが 0 (ゼロ) に設定されている場合のタイムアウト値を要求メッセージのサイズが計算されます。|  
|**ユーザー名**|xs:string|サーバーでの認証に使用するユーザー名。|  
|**Password**|xs:string|サーバーでの認証に使用するユーザー パスワード。|  
|**ProxyUsername**|xs:string|プロキシ サーバーで認証のユーザー名を指定します。|  
|**ProxyPassword**|xs:string|プロキシ サーバーで認証のユーザーのパスワードを指定します。|  
|**MaxRedirects**|xs:int|HTTP アダプターが要求をリダイレクトする最大回数。|  
|**ContentType**|xs:string|要求メッセージのコンテンツ タイプ。|  
|**AuthenticationScheme**|xs:string|接続先のサーバーで使用する認証の種類です。|  
|**[MSSQLSERVER のプロトコルのプロパティ]**|xs:string|SSL クライアント証明書の拇印です。|  
|**UseSSO**|xs:boolean|HTTP 送信ポートで SSO を使用しているかどうかを指定します。|  
|**AffiliateApplicationName**|xs:string|SSO に使用する関連アプリケーションの名前です。|  
|**InboundHttpHeaders**|xs:string|受信した HTTP 要求から HTTP ヘッダーが含まれています。|  
|**SubmissionHandle**|xs:string|要求メッセージの BizTalk Server 関連付けトークン (GUID) が含まれています。|  
|**EnableChunkedEncoding**|xs:boolean|HTTP アダプターによってエンコードされるチャンク対象かどうかを指定します。|  
|**UserHttpHeaders**|xs:string|HTTP 要求または応答メッセージに含まれるカスタマイズされたヘッダーが含まれています<br /><br /> 値、 **UserHttpHeaders**プロパティは、次の形式である必要があります。<br /><br /> `Header1: value\r\nHeader2: value\r\n`<br /><br /> **注**コロン (:) の配置ヘッダーと値の間の空白文字 () を選択します。 空のヘッダーには、フィルターで除外するエントリが発生します。空の値は問題ありません。<br /><br /> 使用して、次の 5 つの標準 HTTP ヘッダーを変更することができます、 **UserHttpHeaders**プロパティ。<br /><br /> -そのまま使用します。<br /><br /> -参照元<br /><br /> -期待します。<br /><br /> 場合-変更-以降<br /><br /> -ユーザー エージェント|  
  
## <a name="see-also"></a>参照  
 [HTTP アダプターの構成](../core/configuring-the-http-adapter.md)