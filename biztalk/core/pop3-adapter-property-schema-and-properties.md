---
title: POP3 アダプタ プロパティ スキーマおよびプロパティ |Microsoft ドキュメント
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
ms.openlocfilehash: b976aba7161272ebdc65da2b5bcd2067c8cd3a5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264170"
---
# <a name="pop3-adapter-property-schema-and-properties"></a>POP3 アダプタ プロパティ スキーマおよびプロパティ
POP3 アダプタ プロパティ スキーマのプロパティを次の表に示します。  
  
 **Namespace:** http://schemas.microsoft.com/BizTalk/2003/pop3-properties  
  
|**名前**|**型**|**Description**|  
|--------------|--------------|---------------------|  
|**Subject**|xs:string|設定するコンテンツを指定します、**サブジェクト**メッセージ ヘッダーには|  
|**From**|xs:string|上に配置する電子メール アドレスを指定します、**から**電子メール メッセージのヘッダー フィールド。|  
|**変換先**|xs:string|電子メール アドレスまたはアドレス上に配置を指定します、**に**電子メール メッセージのヘッダー フィールド。|  
|**ReplyTo**|xs:string|上に配置する電子メール アドレスを指定します、 **ReplyTo**電子メール メッセージのヘッダー フィールド。|  
|**[CC]**|xs:string|電子メール アドレスまたはアドレス上に配置を指定します、 **CC**電子メール メッセージのヘッダー フィールド。|  
|**[日付]**|xs:string|設定するコンテンツを指定します、**日付**電子メール メッセージのヘッダー フィールド。|  
|**DispositionNotificationTo**|xs:string|設定するコンテンツを指定します、 **DispositionNotificationTo**電子メール メッセージのヘッダー フィールド。|  
|**ヘッダー**|xs:string|電子メール メッセージのすべてのヘッダー フィールドに設定するコンテンツを指定します。|  
  
## <a name="see-also"></a>参照  
 [POP3 アダプタを構成します。](../core/configuring-the-pop3-adapter.md)