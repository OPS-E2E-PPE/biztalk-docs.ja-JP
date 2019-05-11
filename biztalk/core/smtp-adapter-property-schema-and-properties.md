---
title: SMTP アダプター プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcc5e9b1ab3ac9ef5d898c21e0c70638425443a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270988"
---
# <a name="smtp-adapter-property-schema-and-properties"></a>SMTP アダプター プロパティ スキーマおよびプロパティ
次の表は、SMTP アダプター プロパティ スキーマのプロパティを一覧表示します。  
  
 **名前空間:** http://schemas.microsoft.com/BizTalk/2003/smtp-properties  
  
|名前|型|説明|  
|----------|----------|-----------------|  
|**ユーザー名**|xs:string|SMTP サーバーでの認証に使用するユーザー名を指定します。|  
|**Password**|xs:string|SMTP サーバーでの認証に使用するパスワードを指定します。|  
|**SMTPHost**|xs:string|メッセージの送信時に使用する SMTP サーバーの名前を指定します。|  
|**From**|xs:string|SMTP に配置する電子メール アドレスを指定**から**ヘッダー。|  
|**Cc**|xs:string|メッセージのコピーを送信する電子メール アドレスを指定します。|  
|**[Subject]**|xs:string|メッセージの件名ヘッダーを指定します。|  
|**SMTPAuthenticate**|xs:int|SMTP サーバーで使用する認証の種類を指定します。|  
|**ReadReceipt**|xs:boolean|メッセージが読み取られるときに、確認の電子メール メッセージを送信するかどうかを指定します。|  
|**DeliveryReceipt**|xs:boolean|メッセージの配信後も、確認の電子メール メッセージを送信するかどうかを指定します。|  
|**EmailBodyText**|xs:string|送信する電子メールの本文に使用するテキストを指定します。|  
|**EmailBodyTextCharset**|xs:string|ときに送信する電子メールの本文のエンコードを使用する文字セットの指定、 **EmailBodyText**オプションを使用します。 SMTP アダプタは、変換、 **EmailBodyText**文字で指定されたセットに**EmailBodyTextCharset**します。|  
|**EmailBodyFile**|xs:string|ファイルの内容が送信される電子メールやファイルへの完全パスの本文に使用されることを指定します。 このパスは、実行時に SMTP アダプターのホストからアクセスできる必要があります。|  
|**EmailBodyFileCharset**|xs:string|場合に送信する電子メールの本文のエンコードを使用する文字セットの指定、 **EmailBodyFile**プロパティを設定します。 SMTP アダプターではファイルの変換は行われません。ファイルはこの文字セットであらかじめエンコードされている必要があります。 ファイルにバイト オーダー マーク (BOM) が含まれている場合は、SMTP アダプターで削除されます。|  
|**[Attachments]**|xs:string|電子メール メッセージにファイルを添付することと、添付するファイルへの完全パスを指定します。 指定されたパスは、実行時に SMTP アダプターのホストからアクセスできる必要があります。|  
|**MessagePartsAttachments**|xs:unsignedInt|BizTalk メッセージ部分を電子メール メッセージに添付する方法を指定します。|  
|**ReplyBy**|xs:dateTime|DateTime 値を指定、**返信先**送信する電子メール メッセージのヘッダー。|  
  
## <a name="see-also"></a>参照  
 [SMTP アダプターの構成](../core/configuring-the-smtp-adapter.md)