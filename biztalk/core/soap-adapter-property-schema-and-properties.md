---
title: "SOAP アダプター プロパティ スキーマおよびプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ProxyUsername property [SOAP adapters]
- ClientConnectionTimeout property [SOAP adapters]
- SOAP adapters, properties
- ProxyAddress property [SOAP adapters]
- UserDefined property [SOAP adapters]
- AssemblyName property [SOAP adapters]
- ClientCertificate property [SOAP adapters]
- AffiliateApplicationName property [SOAP adapters]
- schemas, SOAP adapters
- AuthenticationScheme property [SOAP adapters]
- UserName property, SOAP adapters
- UseProxy property [SOAP adapters]
- Password property [SOAP adapters]
- configuring [SOAP adapters], schemas
- UnknownHeaders property [SOAP adapters]
- configuring [SOAP adapters], properties
- UseSoap12 property [SOAP adapters]
- UseHandlerSetting property [SOAP adapters]
- SOAP adapters, schemas
- ProxyPassword property [SOAP adapters]
- UseSSO property [SOAP adapters]
- MethodName property [SOAP adapters]
- ProxyPort property [SOAP adapters]
ms.assetid: b471cf4b-2d87-4aa2-ae4a-f48517fd4c94
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a24a9ccfc3a07abe925761fe2d6886646981be9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="soap-adapter-property-schema-and-properties"></a>SOAP アダプター プロパティ スキーマおよびプロパティ
SOAP アダプタ プロパティ スキーマのプロパティを次の表に示します。  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/soap-properties  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|**AssemblyName**|xs:string|読み込んで実行する .NET 型およびアセンブリを識別します。|  
|**MethodName**|xs:string|.NET アセンブリの呼び出す対象メソッドを識別します。|  
|**ユーザー名**|xs:string|サーバーで認証に使用するユーザー名。|  
|**Password**|xs:string|サーバーでの認証に使用するユーザーのパスワード。|  
|**ClientCertificate**|xs:string|SSL クライアント証明書の拇印。|  
|**UseProxy**|xs:Boolean|SOAP アダプタでプロキシ サーバーを使用するかどうかを指定します。|  
|**ProxyAddress**|xs:string|プロキシ サーバーのアドレスを指定します。|  
|**ProxyPort**|xs:int|プロキシ サーバーのポートを指定します。|  
|**ProxyUsername**|xs:string|プロキシ サーバーで認証のユーザー名を指定します。|  
|**ProxyPassword**|xs:string|プロキシ サーバーで認証用のユーザー パスワードを指定します。|  
|**UnknownHeaders**|xs:string|不明な SOAP ヘッダーのシリアル化された一覧を指定します。|  
|**AffiliateApplicationName**|xs:string|SSO に使用する関連アプリケーションの名前を定義します。|  
|**AuthenticationScheme**|xs:string|移行先サーバーで使用する認証の種類を指定します。|  
|**UseSSO**|xs:boolean|SOAP アダプタで送信ポートに SSO を使用するかどうかを指定します。|  
|**UseHandlerSetting**|xs:boolean|SOAP 送信ポートでハンドラのプロキシ構成を使用するかどうかを指定します。|  
|**ClientConnectionTimeout**|xs:int|サーバーからの応答を待機する際のタイムアウト期間を指定します。 ゼロ (0) に設定すると、システムは要求メッセージのサイズに基づくタイムアウト値を計算します。|  
|**UserDefined**|xs:string|ユーザー定義のクラスを定義します。|  
|**UseSoap12**|xs:boolean|SOAP 1.2 プロトコルをサポートするプロキシ コードを生成するかどうかを指定します。|  
  
## <a name="see-also"></a>参照  
 [SOAP アダプターの構成](../core/configuring-the-soap-adapter.md)