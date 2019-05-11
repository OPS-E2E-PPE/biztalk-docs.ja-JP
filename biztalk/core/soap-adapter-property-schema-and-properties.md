---
title: SOAP アダプター プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 681a7f529d1326b3301a5cc09dc31e94c8bfbb96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65314052"
---
# <a name="soap-adapter-property-schema-and-properties"></a>SOAP アダプター プロパティ スキーマおよびプロパティ
次の表は、SOAP アダプタ プロパティ スキーマのプロパティを一覧表示します。  
  
 **名前空間:** http://schemas.microsoft.com/BizTalk/2003/soap-properties  
  
|名前|型|説明|  
|----------|----------|-----------------|  
|**AssemblyName**|xs:string|読み込んで実行する .NET 型およびアセンブリを識別します。|  
|**MethodName**|xs:string|対象のメソッドを呼び出す .NET アセンブリを識別します。|  
|**ユーザー名**|xs:string|サーバーで認証に使用するユーザー名。|  
|**Password**|xs:string|サーバーでの認証に使用するユーザーのパスワード。|  
|**ClientCertificate**|xs:string|SSL クライアント証明書の拇印。|  
|**UseProxy**|xs:Boolean|SOAP アダプターでプロキシ サーバーを使用するかどうかを指定します。|  
|**ProxyAddress**|xs:string|プロキシ サーバーのアドレスを指定します。|  
|**ProxyPort**|xs:int|プロキシ サーバーのポートを指定します。|  
|**ProxyUsername**|xs:string|プロキシ サーバーで認証のユーザー名を指定します。|  
|**ProxyPassword**|xs:string|プロキシ サーバーで認証のユーザーのパスワードを指定します。|  
|**UnknownHeaders**|xs:string|不明な SOAP ヘッダーのシリアル化された一覧を指定します。|  
|**AffiliateApplicationName**|xs:string|SSO に使用する関連アプリケーションの名前を定義します。|  
|**AuthenticationScheme**|xs:string|移行先サーバーで使用する認証の種類を指定します。|  
|**UseSSO**|xs:boolean|SOAP アダプターが送信ポートの SSO を使用するかどうかを指定します。|  
|**UseHandlerSetting**|xs:boolean|SOAP 送信ポートが、ハンドラーのプロキシ構成を使用するかどうかを指定します。|  
|**ClientConnectionTimeout**|xs:int|サーバーからの応答の待機のタイムアウト期間を指定します。 ゼロ (0) に設定すると、システムは要求メッセージのサイズに基づいて、タイムアウトを計算します。|  
|**UserDefined**|xs:string|ユーザー定義のクラスを定義します。|  
|**UseSoap12**|xs:boolean|SOAP 1.2 プロトコルをサポートするプロキシ コードを生成するかどうかを指定します。|  
  
## <a name="see-also"></a>参照  
 [SOAP アダプターの構成](../core/configuring-the-soap-adapter.md)