---
title: FTP アダプター プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b61a9bf97f3003a83d148b1c800c13216360ef3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387779"
---
# <a name="ftp-adapter-property-schema-and-properties"></a>FTP アダプター プロパティ スキーマおよびプロパティ
次の表には、FTP アダプタ プロパティ スキーマのプロパティが含まれています。  
  
 **名前空間:** http://schemas.microsoft.com/BizTalk/2003/ftp-properties  
  
|名前|型|説明|  
|----------|----------|-----------------|  
|**RepresentationType**|xs:string|FTP アダプターがデータを送信する方法を指定します。<br /><br /> **有効な値:** バイナリまたは ASCII|  
|**SSOAffiliateApplication**|xs:string|FTP の送信ポートを使用するエンタープライズ シングル サインオン関連アプリケーションを指定します。|  
|**UserName**|xs:string|メッセージを送信するときに、FTP サーバーにログオンするユーザー名を指定します。|  
|**Password**|xs:string|メッセージを送信するときに、FTP サーバーにログオンするときに使用するパスワードを指定します。|  
|**BeforePut**|xs:string|このコマンドは、PUT、FTP サーバー上の既定値を変更するコマンドなどのファイルの前に実行する FTP コマンドを指定します。 セミコロン (;) で個別のコマンド。 [開く] コマンドは必要ありません。|  
|**AfterPut**|xs:string|ファイル PUT の後に実行する FTP コマンドを指定します。 セミコロン (;) で個別のコマンド。|  
|**ReceivedFileName**|xs:string|FTP アダプターがメッセージを読み取るファイルの完全名を指定します。|  
|**MaxConnections**|xs:unsignedInt|サーバーを開くことができる FTP の同時接続の最大数を指定します。 値 0 は無制限を意味します。|  
|**CommandLogFileName**|xs:string|FTP 経由でファイルを送受信する際のエラー状況の診断に使用できるログ ファイルのコピーを保存する場所を指定します。|  
|**AllocateStorage**|xs:boolean|BizTalk Server でこのオプションは非推奨とし、このプロパティの使用はお勧めします。|  
|**PassiveMode**|xs:boolean|アダプターが FTP サーバーに接続モードを指定します。<br /><br /> アクティブ モードでは、FTP サーバーは、FTP アダプターによって開かれたポートに接続します。 パッシブ モードでは、FTP アダプターは、FTP サーバーによって開かれたポートに接続します。<br /><br /> 場合**PassiveMode**が false、アダプターはアクティブ モードを使用して FTP サーバーに接続します。 このプロパティの既定値は false です。|  
|**SpoolingFolder**|xs:string|FTP サーバー上の一時フォルダの場所を指定します。 これを使用するには、転送エラーから復旧できるようにします。|  
|**UseSsl**|xs:boolean|FTP アダプターが FTPS サーバーとの通信に SSL を使用する必要があるかどうかを指定します。|  
|**UseDataProtection**|xs:boolean|ファイル転送に、SSL 暗号化を使用するかどうかを指定します。 アダプターは SSL 暗号化を使用する必要があります、FTPS サーバーからデータ ファイルを受信している場合は、true を選択します。 データ ファイルをプレーン テキストとして送受信するアダプターでは false を選択します。|  
|**FtpsConnectionMode**|xs:string|FTPS サーバーに対する SSL 接続のモードを指定します。<br /><br /> **有効な値:** 暗黙的または明示的です|  
|**ClientCertificateHash**|xs:string|Secure Sockets Layer (SSL) のネゴシエーションで使用する必要があるクライアント証明書の SHA1 ハッシュを指定します。<br /><br /> このハッシュに基づいて、クライアント証明書が取得される、BizTalk ホスト インスタンスが実行されているユーザー アカウントの個人用ストア。|  
  
## <a name="see-also"></a>参照  
 [FTP アダプターの構成](../core/configuring-the-ftp-adapter.md)
 
 [FTP アダプターのベスト プラクティスと推奨事項](../core/best-practices-and-recommendations-for-the-ftp-adapter.md)
 
 [FTP アダプター](../core/ftp-adapter.md)