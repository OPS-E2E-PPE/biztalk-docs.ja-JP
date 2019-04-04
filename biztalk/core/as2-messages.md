---
title: AS2 メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fac8418-3c07-4513-94aa-e7a25087d789
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68ada5722e7b64d6ceaf3b511af5ac500a4dcce7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022600"
---
# <a name="as2-messages"></a>AS2 メッセージ
このトピックでは、AS2 メッセージの構造、コンテキスト プロパティ、ヘッダーなど、AS2 メッセージについて説明します。  
  
## <a name="structure-of-an-as2-message"></a>AS2 メッセージの構造  
 BizTalk Server では、AS2 メッセージがに従って構造化[RFC 4130"Mime-based Secure ピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。  
  
 AS2 メッセージの基本構造は、AS2 固有のヘッダーが追加された HTTP メッセージ内の MIME 形式で構成されます。 HTTP、AS2、および MIME の各ヘッダーの下のメッセージの性質は、次のメッセージの種類によって異なります。  
  
- **署名**– ドキュメント ペイロードの周囲に署名ラッパーが追加、メッセージが署名されている場合。  
  
- **圧縮された**–、ドキュメント ペイロードと署名ペイロードの周囲に圧縮ラッパーが追加、メッセージが圧縮されている場合。  
  
- **暗号化された**– ドキュメント、署名、および圧縮のペイロードの周囲に暗号化ラッパーが追加、メッセージが暗号化されている場合。  
  
  暗号化、署名、および圧縮に基づいた AS2 メッセージのメッセージ構造を次の表に示します。  
  
|AS2 メッセージのオプション|メッセージの構造|  
|-------------------------|-----------------------|  
|-圧縮なし<br /><br /> -暗号化なし<br /><br /> -署名|`HTTP, AS2, MIME Header      EDI/XML Payload`|  
|圧縮されました。<br /><br /> -暗号化なし<br /><br /> -署名|`HTTP, AS2, MIME Header      PKCS7-MIME Compression           EDI/XML Payload (compressed)`|  
|署名付き<br /><br /> -圧縮なし<br /><br /> -暗号化なし|`HTTP, AS2, MIME Header       MIME Security Multipart (signed)           EDI/XML Payload           CMS-PKCS7 Signature`|  
|署名付き<br /><br /> 圧縮されました。<br /><br /> -暗号化なし|`HTTP, AS2, MIME Header       PKCS7-MIME Compression           MIME Security Multipart (signed)(compressed)                EDI/XML Payload (compressed)                CMS-PKCS7 Signature (compressed)`|  
|-暗号化<br /><br /> -圧縮なし<br /><br /> -署名|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           EDI/XML Payload (encrypted)`|  
|圧縮されました。<br /><br /> -暗号化<br /><br /> -署名|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                EDI/XML Payload (compressed)(encrypted)`|  
|-暗号化<br /><br /> 署名付き<br /><br /> -圧縮なし|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           MIME Security Multiparts (signed)(encrypted)                EDI/XML Payload (encrypted)                CMS-PKCS7 Signature (encrypted)`|  
|圧縮されました。<br /><br /> -暗号化<br /><br /> 署名付き|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                MIME Security Multiparts (signed)(compressed)(encrypted)                     EDI/XML Payload (compressed)(encrypted)                     CMS-PKCS7 Signature (compressed)(encrypted)`|  
  
 ドキュメントのペイロードは、複数のドキュメントで構成され、RFC 2387」の説明に従ってにマルチパート/関連の MIME エンベロープ内で格納されます。 Content-Disposition MIME ヘッダーは、メッセージ内の各ドキュメントのファイル名を指定するために使用できます。  
  
 次の表に、メッセージの暗号化、署名、および圧縮の各オプションに基づいた、複数の添付ファイルを含む AS2 メッセージのメッセージ構造を示します。  
  
|AS2 メッセージのオプション|メッセージの構造|  
|-------------------------|-----------------------|  
|-圧縮なし<br /><br /> -暗号化なし<br /><br /> -署名|`HTTP, AS2, MIME Header      MIME Multipart/related           EDI/XML Payloads`|  
|圧縮されました。<br /><br /> -暗号化なし<br /><br /> -署名|`HTTP, AS2, MIME Header      PKCS7-MIME Compression           MIME Multipart/related                EDI/XML Payload (compressed)`|  
|署名付き<br /><br /> -圧縮なし<br /><br /> -署名|`HTTP, AS2, MIME Header       MIME Security Multipart (signed)           MIME Multipart/related                EDI/XML Payload           CMS-PKCS7 Signature`|  
|圧縮されました。<br /><br /> 署名付き<br /><br /> -暗号化なし|`HTTP, AS2, MIME Header       PKCS7-MIME Compression           MIME Security Multipart (signed)(compressed)                MIME Multipart/related (compressed)                     EDI/XML Payload (compressed)                CMS-PKCS7 Signature (compressed)`|  
|-暗号化<br /><br /> -圧縮なし<br /><br /> -署名|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           MIME Multipart/related (encrypted)                EDI/XML Payload (encrypted)`|  
|圧縮されました。<br /><br /> -暗号化<br /><br /> -署名|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                MIME Multipart/related                     EDI/XML Payload (compressed)(encrypted)`|  
|-暗号化<br /><br /> 署名付き<br /><br /> -圧縮なし|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           MIME Security Multiparts (signed)(encrypted)                MIME Multipart/related                     EDI/XML Payload (encrypted)                CMS-PKCS7 Signature (encrypted)`|  
|圧縮されました。<br /><br /> -暗号化<br /><br /> 署名付き|`HTTP, AS2, MIME Header       CMS-PKCS7 MIME Encryption           PKCS7-MIME Compression (encrypted)                MIME Security Multiparts (signed)(compressed)(encrypted)                     MIME Multipart/related                          EDI/XML Payload (compressed)(encrypted)                     CMS-PKCS7 Signature (compressed)(encrypted)`|  
  
## <a name="as2-context-properties"></a>AS2 のコンテキスト プロパティ  
 AS2 メッセージの処理に使用されるコンテキスト プロパティには、昇格できるプロパティや非公開のプロパティが含まれますが、これらのプロパティは中断されたメッセージや追跡メッセージで表示できます。 AS2 コンテキスト プロパティの一覧は、[AS2 コンテキスト プロパティ](../core/as2-context-properties.md)を参照してください。  
  
## <a name="as2-headers"></a>AS2 のヘッダー  
 AS2 メッセージの AS2 ヘッダーは受信側パーティと送信元パーティを記述し、受信側パーティが MDN 応答を送信するために必要な情報を提供します。 しない限り、受信側パーティは MDN ヘッダーを使用は、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**AS2 アグリーメントのプロパティが選択されている情報が、アグリーメントで使用できない場合またはプロパティ。  
  
 AS2-From ヘッダー、AS2-To ヘッダー、および MessageID コンテキスト プロパティは、AS2 メッセージを一意に記述します。 これらは、MDN を応答対象の AS2 メッセージに関連付けるためにも使用されます。  
  
 これらのヘッダーを次の表に示します (アルファベット順)。  
  
|AS2 ヘッダー|必須/省略可|値|  
|----------------|------------------------|------------|  
|AS2-Version|省略可|"1.1"|  
|AS2-From|必須|AS2 メッセージを送信した会社の名前。<br /><br /> 値: 文字列、印刷可能な ASCII、長さ 1 ～ 128 文字|  
|AS2-To|必須|AS2 メッセージが送信される会社の名前。<br /><br /> 値: 文字列、印刷可能な ASCII、長さ 1 ～ 128 文字|  
|AS2-Text|必須|テキスト (メッセージのこのヘッダー)<br /><br /> 値: 文字列、印刷可能な ASCII、長さ 1 ～ 128 文字|  
|Disposition-Notification-To|必須|存在する場合は、返される MDN に対する要求として機能します。 receipt-delivery-option ヘッダーを伴う場合は、非同期 MDN に対する要求になります。 それ以外の場合は、同期 MDN に対する要求になります。<br /><br /> 存在しない場合、MDN は必須ではありません。<br /><br /> 値: 必要なメール アドレス。 ただし、MDN を返す位置の識別にメール アドレスを使用することはできません。 受信側アプリケーションはメール アドレスを無視し、アドレス構文の違反を示すエラーを表示しません。|  
|EDIINT-Features|必須|発信元システムがサポートしている機能を示します。 BizTalk ではこのヘッダーを使用して、複数の添付ファイルのサポートを示します。<br /><br /> 値: "MA"|  
|Receipt-Delivery-Option|必須|MDN が送信される URL を示します。 Receipt-Delivery-Option が存在する場合、Disposition-notification-to は非同期 MDN に対する要求として機能します。 Receipt-Delivery-Option は常に Disposition-Notification-To を伴う必要があります。<br /><br /> Receipt-Delivery-Option が存在せず、Disposition-notification-to が存在する場合、Disposition-notification-to は同期 MDN に対する要求として機能します。<br /><br /> 値: URL 文字列|  
|signed-receipt-protocol<br /><br /> (Disposition-Notification-Options 内)|省略可|"pcks7-signature" に設定した場合は、受信側パーティから署名付きの確認メッセージを要求するために使用され、署名付きの受信確認が要求側に返される形式を示します。<br /><br /> 値: 省略可能、pcks7-signature|  
|signed-receipt-micalg<br /><br /> (Disposition-Notification-Options 内)|省略可|確認メッセージに署名する際に要求側によって優先的に使用される MIC アルゴリズムの一覧です。 受信側パーティは、左から順に MIC アルゴリズムの一覧に従う必要があります。<br /><br /> 値: 省略可能、MD5、または SHA1|  
  
 受信メッセージでは、AS2EdiReceive および AS2Receive 受信パイプラインは、AS2 アグリーメント プロパティの Signed Receipt Protocol および Signed Receipt MIC Algorithm の値を検証します。  
  
 送信 AS2 メッセージでは、AS2EdiSend および AS2Send 送信パイプラインは、AS2 アグリーメントに入力された値から前の AS2 ヘッダーを設定します (ただし、1.1 としてハードコーディングされている AS2-Version を除きます)。  
  
 **MDN に対する要求**  
  
 受信側パーティが MDN (Message Disposition Notification) を返す要求は、送信されるメッセージに次のヘッダーを配置することで行われます。  
  
 MDN-request-header = "Disposition-notification-to"  ":"  mail-address  
  
 MDN を返す位置の識別にはメール アドレスは使用されません。 受信側アプリケーションは値を無視し、アドレス構文の違反に関するエラーを送信しません。  
  
## <a name="see-also"></a>参照  
 [MDN メッセージ](../core/mdn-messages.md)