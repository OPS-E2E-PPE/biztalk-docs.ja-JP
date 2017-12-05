---
title: "BizTalk Server 管理コンソールから公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b78b1981-b227-4cf5-9435-6fc57963552a
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fbe03b1a8df67581ce73db31cd5ed4b80b7a109c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからの発行
ESB の管理ポータルではなく、BizTalk Server 管理コンソールを通じて公開エンドポイントを管理する場合は、これを行うエンドポイントの説明 フィールドに Universal Description, Discovery, and Integration (UDDI) モニカーを入力してUDDI を発行します。 例モニカーを次に示します。  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 使用して、次の UDDI プロパティを設定することができます、**説明**フィールドで、BizTalk Server 管理コンソール。  
  
-   **ModifiedBy**です。 このオプションのプロパティには、エンドポイントを変更したユーザーのアカウント名が含まれていますたとえば、MyDomainName\MyUserName です。  
  
-   **UDDIContact**です。 このオプションのプロパティは、UDDI Business プロバイダーに対して定義されているユーザーの連絡先の名前です。  
  
-   **UDDIUserType**です。 このオプションのプロパティは、UDDI Business プロバイダーに対して定義されているユーザーのユーザーの種類です。  
  
-   **UDDIEmail**です。 このオプションのプロパティは、UDDI Business プロバイダーに対して定義されているユーザーの電子メール アドレスです。  
  
-   **TransportType**です。 省略可能なこのプロパティは、エンドポイント アダプターの種類など**ファイル、MQS、Wcf-wshttp、SOAP、HTTP、**または**FTP**です。  
  
-   **ステータス**です。 省略可能なこのプロパティは、エンドポイントの状態など**Published**または**保留**です。 UDDI 発行サービスでは、この属性を使用して、エンドポイントの状態を検出します。  
  
-   **BindingType**です。 この省略可能なプロパティは、UDDI バインディングをサポートするなど、特定のプロトコル (URL の種類) **mailto、http、https、ftp、fax、電話、**または**他の**します。 UDDI 発行サービスでは、この属性を使用して、エンドポイントのバインディングを作成します。