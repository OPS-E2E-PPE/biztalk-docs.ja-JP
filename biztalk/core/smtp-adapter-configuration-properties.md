---
title: "SMTP アダプター構成プロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SMTP adapters, properties
- SMTP adapters, code sample
- SMTP adapters, send ports
- send ports, adapters
ms.assetid: 6af287f5-272a-42d7-9878-99a4157c06ce
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b8bb0c5562c07260a9d411b8144bd7a576eb3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter-configuration-properties"></a>SMTP アダプター構成プロパティ
次の表に、SMTP アダプターの送信ポートに設定できる構成プロパティを示します。  
  
|プロパティ名|型|Description|制限|コメント|  
|-------------------|----------|-----------------|------------------|--------------|  
|DeliveryReceipt|VT_BOOL|メッセージの配信時に確認の電子メール メッセージが送信されるように指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
|From|VT_BSTR|SMTP 差出人ヘッダーに配置する電子メール アドレスを指定します。|最小長: 0<br /><br /> 最大長: 256|なし|  
|MessagePartsAttachments|VT_UI4|BizTalk メッセージ部分を電子メール メッセージに添付する方法を指定します。|有効な値は、<br /><br /> -0 (メッセージ部分を添付しない)<br />-1 (アタッチ ボディ部のみ<br />-2 (すべての部分を添付する)|既定値は 0 (メッセージ部分を添付しない) です。|  
|[CC]|VT_BSTR|メッセージのカーボン コピーを送信する電子メール アドレスを指定します。|最大の長さ: 1024|複数のアドレスを指定できます。|  
|SMTPAuthenticate|VT_UI4|有効な値は、<br /><br /> -0 (認証しない)<br />-1 (基本認証)<br />-2 (プロセス アカウント (NTLM))|この値を指定しなかった場合は、[(既定)UI] の値が適用されます。|[(既定)UI] の値を指定すると、送信ハンドラーに指定された構成値が SMTP 送信ポートで使用されます。|  
|[ユーザー名]|VT_BSTR|SMTP サーバーでの認証に使用するユーザー名を指定します。|SMTPAuthenticate プロパティが 1 (基本認証) 以外の値に設定されている場合、このプロパティの値は必要ありません。<br /><br /> 最小長: 0<br /><br /> 最大長: 256|なし|  
|EmailBodyFileCharset|VT_BSTR|送信するファイルの文字セットのエンコードを指定します。|EmailBodyFile プロパティが設定されていない場合、このプロパティの値は必要ありません。|SMTP アダプターは指定されたエンコードをファイルに適用しません。このオプションは、送信するファイルがどのようにエンコードされているかを指定するためにのみ使用します。<br /><br /> 既定値は utf-8 です。|  
|EmailBodyText|VT_BSTR|送信する電子メールの本文に使用するテキストを指定します。|64 Kb の最大長:|なし|  
|ReadReceipt|VT_BOOL|メッセージが読み取られるときに確認の電子メール メッセージが送信されるように指定します。|有効な値は、<br /><br /> -1 (true)<br />-0 (false)|既定値は 0 (false) です。|  
|変換先|VT_BSTR|メッセージ送信先の電子メール アドレスを指定します。|なし|なし|  
|EmailBodyFile|VT_BSTR|送信する電子メールの本文に使用されるファイルへのパスを指定します。|パスの最大長: 256 文字|実稼働環境で使用する BizTalk Server グループのすべての BizTalk Server からアクセス可能なファイル共有のパスを指定することを推奨します。|  
|Subject|VT_BSTR|メッセージの件名ヘッダーを指定します。|最小長: 0<br /><br /> 最大長: 256|なし|  
|Password|VT_NULL|SMTP サーバーでの認証に使用するパスワードを指定します。|SMTPAuthenticate プロパティが 1 (基本認証) に設定されていない限り、このプロパティは、値を必要ありません。<br /><br /> バインド ファイルをエクスポートする場合は、この値を必ず Null に設定します。 ターゲットの BizTalk Server 構成にバインド ファイルをインポートする前に、このフィールドにパスワードを手動で設定する必要があります。|なし|  
|[Attachments]|VT_BSTR|送信する電子メールに添付されるファイルへのパスを指定します。|パスの最大長: 256 文字|なし|  
|SMTPHost|VT_BSTR|メッセージの送信時に使用する SMTP サーバーの名前を指定します。|送信ポートまたは受信場所の URI は 256 文字以内で指定してください。<br /><br /> パスの最大長: 256 文字|なし|  
|EmailBodyTextCharset|VT_BSTR|送信する電子メールの本文のエンコードに使用する文字セットを指定します。|EmailBodyText プロパティが設定されていない場合、このプロパティの値は必要ありません。|既定値は utf-8 です。|  
  
 次のコード例は、プロパティの設定に使用する XML 文字列の形式を示しています。  
  
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