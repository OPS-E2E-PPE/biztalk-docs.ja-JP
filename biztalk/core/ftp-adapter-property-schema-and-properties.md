---
title: "FTP アダプター プロパティ スキーマおよびプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [FTP adapters], schemas
- FTP adapters, properties
- BeforePut property [FTP adapters]
- PassiveMode property [FTP adapters]
- configuring [FTP adapters], properties
- UserName property, FTP adapters
- SSOAffiliateApplication property [FTP adapters]
- AfterPut property [FTP adapters]
- ReceivedFileName property [FTP adapters]
- RepresentationType property [FTP adapters]
- SpoolingFolder property [FTP adapters]
- FTP adapters, schemas
- CommandLogFileName property [FTP adapters]
- AllocateStorage property [FTP adapters]
- schemas, FTP adapters
- Password property [FTP adapters]
- MaxConnections property [FTP adapters]
ms.assetid: 677fdb61-c2b0-4df2-a826-840113e61e8b
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cf72847fccd84a1435e436a4bf2b59d36e26179
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="ftp-adapter-property-schema-and-properties"></a>FTP アダプター プロパティ スキーマおよびプロパティ
FTP アダプタ プロパティ スキーマのプロパティを次の表に示します。  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/ftp-properties  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|**RepresentationType**|xs:string|FTP アダプタによって送信されるデータの形式を指定します。<br /><br /> **有効な値:**バイナリまたは ASCII|  
|**SSOAffiliateApplication**|xs:string|FTP 送信ポートで使用するエンタープライズ シングル サインオン関連アプリケーションを指定します。|  
|**UserName**|xs:string|メッセージの送信時に FTP サーバーにログオンするユーザーの名前を指定します。|  
|**Password**|xs:string|メッセージの送信時に FTP サーバーへのログオンに使用するパスワードを指定します。|  
|**BeforePut**|xs:string|ファイルの PUT コマンドの前に実行する FTP コマンドを指定します。たとえば、FTP サーバーの既定値を変更するコマンドなどがあります。 コマンドの区切りにはセミコロン (;) を使用します。 ファイルを開くコマンドは必要ありません。|  
|**AfterPut**|xs:string|ファイル PUT の後に実行する FTP コマンドを指定します。 コマンドの区切りにはセミコロン (;) を使用します。|  
|**ReceivedFileName**|xs:string|FTP アダプタがメッセージを読み取るファイルの完全な名前を指定します。|  
|**MaxConnections**|xs:unsignedInt|サーバーに対して同時に開くことができる FTP 接続の最大数を指定します。 値 0 を指定した場合、接続は制限されません。|  
|**CommandLogFileName**|xs:string|FTP 経由でファイルを送受信したときに発生したエラー状態の診断に使用できるログ ファイルのコピーを保存する場所を指定します。|  
|**AllocateStorage**|xs:boolean|BizTalk Server では、このオプションは廃止されており、このプロパティの使用はお勧めします。|  
|**PassiveMode**|xs:boolean|FTP サーバーへのアダプターの接続モードを指定します。<br /><br /> アクティブ モードでは、FTP アダプターによって開かれたポートに FTP サーバーが接続します。 パッシブ モードでは、FTP サーバーによって開かれたポートに FTP アダプターが接続します。<br /><br /> 場合**PassiveMode**は、アダプターがアクティブ モードを使用して FTP サーバーに接続し、false を指定します。 このプロパティの既定値は False です。|  
|**SpoolingFolder**|xs:string|FTP サーバーの一時フォルダの場所を指定します。 このフォルダは、転送エラーの修復に使用されます。|  
|**UseSsl**|xs:boolean|FTPS サーバーとの通信で FTP アダプターが強制的に SSL を使用するかどうかを指定します。|  
|**UseDataProtection**|xs:boolean|ファイル転送に SSL 暗号化を使用するかどうかを指定します。 FTPS サーバーとの間でデータ ファイルを送受信する場合にアダプターで強制的に SSL 暗号化を使用する場合は True を選択します。 アダプターがデータ ファイルをプレーンテキストで送受信する場合は False を選択します。|  
|**FtpsConnectionMode**|xs:string|FTPS サーバーに対する SSL 接続のモードを指定します。<br /><br /> **有効な値:**暗黙的または明示的な|  
|**ClientCertificateHash**|xs:string|SSL (Secure Sockets Layer) のネゴシエーションで使用する必要のあるクライアント証明書の SHA1 ハッシュを指定します。<br /><br /> このハッシュに基づいて、BizTalk ホスト インスタンスを実行しているユーザー アカウントの個人ストアからクライアント証明書が取得されます。|  
  
## <a name="see-also"></a>参照  
 [FTP アダプターの構成](../core/configuring-the-ftp-adapter.md)
 
 [FTP アダプターのベスト プラクティスと推奨事項](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)
 
 [FTP アダプター](../core/ftp-adapter.md)