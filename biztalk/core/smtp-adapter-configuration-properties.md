---
title: SMTP アダプター構成プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SMTP adapters, properties
- SMTP adapters, code sample
- SMTP adapters, send ports
- send ports, adapters
ms.assetid: 6af287f5-272a-42d7-9878-99a4157c06ce
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 740e3081e9b03dec725b02dd0107d9c8a1363b48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401887"
---
# <a name="smtp-adapter-configuration-properties"></a>SMTP アダプター構成プロパティ
SMTP アダプターの設定できる構成プロパティ送信ポートに次の表に示します。  
  
|プロパティ名|型|説明|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|DeliveryReceipt|VT_BOOL|メッセージが配信されるときに確認の電子メール メッセージを送信する必要がありますを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
|From|VT_BSTR|SMTP 差出人ヘッダーに配置する電子メール アドレスを指定します。|最小長:0<br /><br /> 最大長:256|なし|  
|MessagePartsAttachments|VT_UI4|BizTalk メッセージ部分を電子メール メッセージに添付する方法を指定します。|有効な値は、<br /><br /> -0 (メッセージ部分を添付しない)<br />-1 (アタッチ ボディ部のみ<br />-2 (すべての部分を添付する)|既定値は、0 (メッセージ部分を添付しないです)。|  
|[CC]|VT_BSTR|メッセージのカーボン コピーを送信する電子メール アドレスを指定します。|最大長:1024|複数のアドレスを指定できます。|  
|SMTPAuthenticate|VT_UI4|有効な値は、<br /><br /> -0 (認証しない)<br />-1 (基本認証)<br />-2 (プロセス アカウント (NTLM))|この値が指定されていない場合 (既定値) の値が適用されます。|(既定値) の値では、SMTP 送信ポートで送信ハンドラで指定された構成値を使用していることを示します。|  
|Username|VT_BSTR|SMTP サーバーでの認証に使用するユーザー名を指定します。|SMTPAuthenticate プロパティが 1 (基本認証) に設定されていない限り、このプロパティは、値を必要ありません。<br /><br /> 最小長:0<br /><br /> 最大長:256|なし|  
|EmailBodyFileCharset|VT_BSTR|送信するファイルの文字セットのエンコードを指定します。|EmailBodyFile プロパティが設定されていない限り、このプロパティは、値を必要ありません。|SMTP アダプターがファイルに指定したエンコーディングを適用していない、このオプションは、送信されるファイルが既にエンコードされた方法を指定するためだけです。<br /><br /> 既定値は utf-8 です。|  
|EmailBodyText|VT_BSTR|送信する電子メールの本文に使用するテキストを指定します。|最大長:64 kb|なし|  
|ReadReceipt|VT_BOOL|メッセージが読み取られるときに確認の電子メール メッセージを送信する必要がありますを指定します。|有効な値は、<br /><br /> -   -1 (true)<br />-0 (false)|既定値は 0 (false です)。|  
|目的|VT_BSTR|メッセージ送信先の電子メール アドレスを指定します。|なし|なし|  
|EmailBodyFile|VT_BSTR|送信する電子メールの本文に使用されるファイルへのパスを指定します。|パスの最大長:256 文字|運用環境で使用する BizTalk Server グループ内のすべての BizTalk サーバーからアクセスできるファイル共有のパスを指定する場合は、推奨されるベスト プラクティスを勧めします。|  
|Subject|VT_BSTR|メッセージの件名ヘッダーを指定します。|最小長:0<br /><br /> 最大長:256|なし|  
|パスワード|VT_NULL|SMTP サーバーでの認証に使用するパスワードを指定します。|SMTPAuthenticate プロパティが 1 (基本認証) に設定されていない限り、このプロパティは、値を必要ありません。<br /><br /> この値は常に、バインド ファイルをエクスポートする場合は null に設定します。 このフィールドは、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前に、パスワードを使用して手動設定する必要があります。|なし|  
|[Attachments]|VT_BSTR|送信される電子メールに添付するファイルへのパスを指定します。|パスの最大長:256 文字|なし|  
|SMTPHost|VT_BSTR|メッセージの送信時に使用する SMTP サーバーの名前を指定します。|URI を送信ポートまたは受信場所が 256 文字を超えることはできません。<br /><br /> パスの最大長:256 文字|なし|  
|EmailBodyTextCharset|VT_BSTR|送信する電子メールの本文のエンコードを使用する文字セットを指定します。|EmailBodyText プロパティが設定されていない限り、このプロパティは、値を必要ありません。|既定値は utf-8 です。|  
  
 次のコードでは、プロパティの設定に使用する XML 文字列の形式を示します。  
  
```  
<CustomProps>  
<DeliveryReceipt vt="11">-1</DeliveryReceipt>  
<From vt="8">someone@microsoft.com</From>  
<MessagePartsAttachments vt="19">0</MessagePartsAttachments>  
<CC vt="8">someoneelse@microsoft.com</CC>  
<SMTPAuthenticate vt="19">1</SMTPAuthenticate>  
<Username vt="8">OverrideUsername</Username>  
<EmailBodyFileCharset vt="8">utf-8</EmailBodyFileCharset>  
<EmailBodyText vt="8">Email Body Text</EmailBodyText>  
<ReadReceipt vt="11">-1</ReadReceipt>  
<To vt="8">recipient@microsoft.com</To>  
<EmailBodyFile vt="8">C:\emailbodyfile.xml</EmailBodyFile>  
<Subject vt="8">test mail</Subject>  
<Password vt="1" />  
<Attachments vt="8">C:\attachment.txt</Attachments>  
<SMTPHost vt="8">emailhost</SMTPHost>  
<EmailBodyTextCharset vt="8">utf-8</EmailBodyTextCharset>  
</CustomProps>  
```