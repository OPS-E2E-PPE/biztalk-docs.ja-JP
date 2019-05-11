---
title: POP3 アダプタ プロパティ スキーマおよびプロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, POP3 adapters
- Subject properties [POP3 adapters]
- Date properties [POP3 adapters]
- From properties [POP3 adapters]
- To properties [POP3 adapters]
- POP3 adapters, properties
- configuring [POP3 adapters], schemas
- configuring [POP3 adapters], properties
- CC properties [POP3 adapters]
- Headers properties [POP3 adapters]
- ReplyTo properties [POP3 adapters]
- DispositionNotificationTo properties [POP3 adapters]
ms.assetid: 7a10ae1f-dbcf-4c05-9a50-2503895960f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bfd98117254686f69a590430f46fbd07a4d0b03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394912"
---
# <a name="pop3-adapter-property-schema-and-properties"></a>POP3 アダプタ プロパティ スキーマおよびプロパティ
次の表は、POP3 アダプタ プロパティ スキーマのプロパティを一覧表示します。  
  
 **名前空間:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties  
  
|**名前**|**型**|**[説明]**|  
|--------------|--------------|---------------------|  
|**[Subject]**|xs:string|設定するコンテンツを指定します、**サブジェクト**メッセージ ヘッダーには|  
|**From**|xs:string|設定する電子メール アドレスを指定します、**から**電子メール メッセージのヘッダー フィールド。|  
|**変換先**|xs:string|上に配置された電子メール アドレスを指定します、**に**電子メール メッセージのヘッダー フィールド。|  
|**ReplyTo**|xs:string|設定する電子メール アドレスを指定します、 **ReplyTo**電子メール メッセージのヘッダー フィールド。|  
|**Cc**|xs:string|上に配置された電子メール アドレスを指定します、 **CC**電子メール メッセージのヘッダー フィールド。|  
|**Date**|xs:string|設定するコンテンツを指定します、**日付**電子メール メッセージのヘッダー フィールド。|  
|**DispositionNotificationTo**|xs:string|設定するコンテンツを指定します、 **DispositionNotificationTo**電子メール メッセージのヘッダー フィールド。|  
|**ヘッダー**|xs:string|すべての電子メール メッセージのヘッダー フィールドの内容を指定します。|  
  
## <a name="see-also"></a>参照  
 [POP3 アダプターの構成](../core/configuring-the-pop3-adapter.md)