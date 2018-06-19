---
title: BizTalk アダプターに IPv6 のアドレス指定を使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93cd2ead-5e87-47ac-8f78-d56b80afd34e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5726d5b05c548fd728228fcad39e56ce535fbb5
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710625"
---
# <a name="using-ipv6-addressing-with-biztalk-adapters"></a>BizTalk アダプターにおける IPv6 アドレス指定の使用
BizTalk Server アダプターでは、IPv6 アドレスの使用をサポートします。 このトピックでは、UNC パスに対して IPv6 アドレスを指定するために使用される命名規則、リテラル IPv6 アドレスを指定するための命名規則、および HTTP アダプターと SOAP アダプターでの IPv6 スコープ識別子の使用について説明します。  
  
## <a name="ipv6-address-nomenclature-used-for-a-unc-path"></a>UNC パスに対して使用される IPv6 アドレス命名規則  
 UNC パスでリテラル IPv6 アドレスを指定するには、次の手順に従います。  
  
1.  すべてのコロン文字 ":" をダッシュ文字 "-" で置換します。  
  
2.  テキストを追加"**.ipv6 という**"IP アドレスにします。  
  
 たとえば、2001:DB8:2a:1005:230:48ff:fe73:989d という IPv6 アドレスを使用してコンピューター上のファイル共有を参照する URI は、次のようになります。  
  
```  
\\2001-DB8-2a-1005-230-48ff-fe73-989d.ipv6-literal.net\<sharename\>  
```  
  
 ここで\< *sharename* \>ターゲット コンピューター上のファイル共有の名前を指定します。  
  
> [!NOTE]
>  ファイル送信ハンドラーとファイル受信ハンドラーが実行されているホスト インスタンスのユーザー アカウントが、ファイル共有に対する適切なアクセス許可を持っていることを確認します。 ファイル アダプターでファイルを受信するために必要なフォルダーのアクセス許可の詳細については、次を参照してください。[ファイル受信ハンドラーを構成する](../core/configure-the-file-adapter.md)です。 ファイル アダプターを持つファイルを送信するときに必要なフォルダーのアクセス許可の詳細については、次を参照してください。[ファイル アダプターに関する既知の問題](../core/known-issues-with-the-file-adapter.md)です。 ファイル アダプターで使用するためにサポートされているファイル システムについては、次を参照してください。 [http://support.microsoft.com/kb/815070](http://support.microsoft.com/kb/815070)します。  
  
## <a name="using-ipv6-scope-identifiers-with-the-http-adapter-and-the-soap-send-adapter"></a>HTTP アダプターおよび SOAP 送信アダプターにおける IPv6 スコープ識別子の使用  
 HTTP 送信アダプターと受信 SOAP 送信アダプタでは、スコープ識別子が IPv6 アドレスで使用されている場合、スコープ識別子必要がありますエスケープすることをエスケープ コードに必要な **%25**します。 たとえば、 **fe80::550c:489f:e65e:aef3 %8** スコープ識別子 (%8) を含む有効な IPv6 アドレスします。 HTTP 送受信アダプターまたは SOAP 送信アダプターと共にこの IPv6 アドレスを使用するには、スコープ識別子を次のようにエスケープさせる必要があります。  
  
```  
fe80::550c:489f:e65e:aef3%258  
```  
  
## <a name="adapter-uri-nomenclature-used-for-a-literal-ipv6-address"></a>リテラル IPv6 アドレスで使用されるアダプター URI 命名規則  
  
-   アダプターの URI としてリテラル IPv6 アドレスを使用するには、IP アドレスを角かっこ [ と ] で囲みます。 たとえば、2001:DB8:2a:1005:230:48ff:fe73:989d という IPv6 アドレスの URI は、次のようになります。  
  
    ```  
    [2001:DB8:2a:1005:230:48ff:fe73:989d]  
    ```  
  
    > [!NOTE]
    >  アダプターの Uri のガイドラインに従うために、リテラルの使用の IPv6 アドレス [RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375)します。  
  
-   リテラル IPv6 アドレスを POP3 受信アダプター、SMTP 送信アダプター、または SQL 送受信アダプターのサーバー名として指定する場合、IPv6 アドレスを角かっこで囲む必要はありません。  
  
## <a name="summary-of-considerations-when-using-literal-ipv6-addressing-with-biztalk-adapters"></a>BizTalk アダプターでリテラル IPv6 アドレス指定を使用する場合の考慮事項のまとめ  
 次の表に、リテラル IPv6 アドレスを使用するために IP アドレスを角かっこ [ および ] で囲むことがいつ必要になるか、および IPv6 アドレスで使用されるスコープ識別子をエスケープさせることがいつ必要になるかを示します。  
  
|[アダプター]|リテラル IPv6 アドレスを角かっこで囲む必要性|スコープ識別子をエスケープさせる必要性|  
|---|---|---|  
|POP3 受信|いいえ|いいえ|  
|SMTP 送信|いいえ|いいえ|  
|SQL 送受信|いいえ|いいえ|  
|ファイル送受信|いいえ (セクションを参照して **UNC パスに対して使用される IPv6 アドレス命名規則**)|いいえ|  
|HTTP 送受信|可|はい|  
|MQSeries 送受信|はい|いいえ|  
|MSMQ 送受信|可|いいえ|  
|SOAP 送信|はい|可|  
|SOAP 受信|はい|いいえ|  
|WCF 送受信|はい|いいえ|