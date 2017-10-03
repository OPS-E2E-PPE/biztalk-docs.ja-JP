---
title: "SMTP アダプター プロパティ スキーマおよびプロパティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserName property, SMTP adapters
- EmailBodyTextCharset property [SMTP adapters]
- configuring [SMTP adapters], properties
- Subject property [SMTP adapters]
- EmailBodyFileCharset property [SMTP adapters]
- Attachments property [SMTP adapters]
- SMTP adapters, schemas
- EmailBodyText property [SMTP adapters]
- configuring [SMTP adapters], schemas
- CC property [SMTP adapters]
- ReadReceipt property [SMTP adapters]
- Password property [SMTP adapters]
- ReplyBy property [SMTP adapters]
- DeliveryReceipt property [SMTP adapters]
- SMTP adapters, properties
- SMTPAuthenticate property [SMTP adapters]
- EmailBodyFile property [SMTP adapters]
- schemas, SMTP adapters
- SMTPHost property [SMTP adapters]
- From property [SMTP adapters]
- MessagePartsAttachments property [SMTP adapters]
ms.assetid: 6d062fb6-d728-4525-8f0d-bd3f0f8ff7ca
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09f7dfa67bfad53e43a4a6678ff6ad67705e0e27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="smtp-adapter-property-schema-and-properties"></a>SMTP アダプター プロパティ スキーマおよびプロパティ
SMTP アダプター プロパティ スキーマのプロパティを次の表に示します。  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/smtp-properties  
  
|名前|型|Description|  
|----------|----------|-----------------|  
|**ユーザー名**|xs:string|SMTP サーバーでの認証に使用するユーザー名を指定します。|  
|**Password**|xs:string|SMTP サーバーでの認証に使用するパスワードを指定します。|  
|**Smtp ホスト**|xs:string|メッセージの送信時に使用する SMTP サーバーの名前を指定します。|  
|**From**|xs:string|SMTP に配置する電子メール アドレスを指定**から**ヘッダー。|  
|**[CC]**|xs:string|メッセージのコピーを送信する電子メール アドレスを指定します。|  
|**Subject**|xs:string|メッセージの件名ヘッダーを指定します。|  
|**SMTPAuthenticate**|xs:int|SMTP サーバーで使用する認証の種類を指定します。|  
|**ReadReceipt**|xs:boolean|メッセージが開封されたときに確認電子メール メッセージを送信するかどうかを指定します。|  
|**DeliveryReceipt**|xs:boolean|メッセージの配信後に確認電子メール メッセージを送信するかどうかを指定します。|  
|**EmailBodyText**|xs:string|送信する電子メールの本文に使用するテキストを指定します。|  
|**EmailBodyTextCharset**|xs:string|ときに送信する電子メールの本文のエンコードを使用する文字セットの指定、 **EmailBodyText**オプションを使用します。 SMTP アダプタは、変換、 **EmailBodyText**文字で指定したセットに**EmailBodyTextCharset**です。|  
|**EmailBodyFile**|xs:string|ファイルの内容が、メールが送信されると、ファイルへの完全パスの本体用に使用されることを指定します。 このパスは、実行時に SMTP アダプターのホストからアクセスできる必要があります。|  
|**EmailBodyFileCharset**|xs:string|場合に送信される電子メールの本文のエンコードに使用する文字セットの指定、 **EmailBodyFile**プロパティを設定します。 SMTP アダプターではファイルの変換は行われません。ファイルはこの文字セットであらかじめエンコードされている必要があります。 ファイルにバイト オーダー マーク (BOM) が含まれている場合は、SMTP アダプターで削除されます。|  
|**[Attachments]**|xs:string|電子メール メッセージにファイルを添付することと、添付するファイルへの完全パスを指定します。 指定されたパスは、実行時に SMTP アダプターのホストからアクセスできる必要があります。|  
|**MessagePartsAttachments**|xs:unsignedInt|BizTalk メッセージ部分を電子メール メッセージに添付する方法を指定します。|  
|**ReplyBy**|xs:dateTime|DateTime 値を指定、**返信先**送信する電子メール メッセージのヘッダー。|  
  
## <a name="see-also"></a>参照  
 [SMTP アダプタの構成](../core/configuring-the-smtp-adapter.md)