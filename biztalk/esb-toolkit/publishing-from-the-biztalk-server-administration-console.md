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
ms.openlocfilehash: 313bfb773a94914ed9bebd3930dfd0033ecf4ac3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからの発行
使用したエンドポイント パブリッシュを管理する場合、 [!INCLUDE[prague](../includes/prague-md.md)] ESB 管理ポータルではなく管理コンソールで、これを行うの説明 フィールドに Universal Description, Discovery, and Integration (UDDI) モニカーを入力して、UDDI を発行するエンドポイント。 例モニカーを次に示します。  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 使用して、次の UDDI プロパティを設定することができます、**説明**フィールドで、[!INCLUDE[prague](../includes/prague-md.md)]管理コンソール。  
  
-   **ModifiedBy**です。 このオプションのプロパティには、エンドポイントを変更したユーザーのアカウント名が含まれていますたとえば、MyDomainName\MyUserName です。  
  
-   **UDDIContact**です。 このオプションのプロパティは、UDDI Business プロバイダーに対して定義されているユーザーの連絡先の名前です。  
  
-   **UDDIUserType**です。 このオプションのプロパティは、UDDI Business プロバイダーに対して定義されているユーザーのユーザーの種類です。  
  
-   **UDDIEmail**です。 このオプションのプロパティは、UDDI Business プロバイダーに対して定義されているユーザーの電子メール アドレスです。  
  
-   **TransportType**です。 省略可能なこのプロパティは、エンドポイント アダプターの種類など**ファイル、MQS、Wcf-wshttp、SOAP、HTTP、**または**FTP**です。  
  
-   **ステータス**です。 省略可能なこのプロパティは、エンドポイントの状態など**Published**または**保留**です。 UDDI 発行サービスでは、この属性を使用して、エンドポイントの状態を検出します。  
  
-   **BindingType**です。 この省略可能なプロパティは、UDDI バインディングをサポートするなど、特定のプロトコル (URL の種類) **mailto、http、https、ftp、fax、電話、**または**他の**します。 UDDI 発行サービスでは、この属性を使用して、エンドポイントのバインディングを作成します。