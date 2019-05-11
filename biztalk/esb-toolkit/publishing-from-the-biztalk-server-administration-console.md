---
title: BizTalk Server 管理コンソールからの発行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b78b1981-b227-4cf5-9435-6fc57963552a
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5423c228b4ea9b8cd16bdac35a0e72c2fecbc232
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301855"
---
# <a name="publishing-from-the-biztalk-server-administration-console"></a>BizTalk Server 管理コンソールからの発行
ESB 管理ポータルではなく BizTalk Server 管理コンソールを通して公開エンドポイントを管理する場合は、これを行うエンドポイントの説明フィールドに Universal Description, Discovery, and Integration (UDDI) モニカーを入力してUDDI を発行します。 次に、例のモニカーを示します。  
  
```  
uddi://TransportType=other;Status=Published.  
```  
  
 使用して、次の UDDI プロパティを設定することができます、**説明**フィールドに、BizTalk Server 管理コンソール。  
  
-   **ModifiedBy**します。 この省略可能なプロパティには、エンドポイントを変更したユーザーのアカウント名が含まれています。たとえば、MyDomainName\MyUserName です。  
  
-   **UDDIContact**します。 この省略可能なプロパティは、UDDI ビジネス プロバイダーに対して定義されているユーザーの連絡先の名前です。  
  
-   **UDDIUserType**します。 この省略可能なプロパティは、UDDI ビジネス プロバイダーに対して定義されているユーザーのユーザーの種類です。  
  
-   **UDDIEmail**します。 この省略可能なプロパティは、UDDI ビジネス プロバイダーに対して定義されているユーザーの電子メール アドレスです。  
  
-   **TransportType**します。 この省略可能なプロパティは、エンドポイントのアダプターの種類をなど、**ファイル、MQS、Wcf-wshttp、SOAP、HTTP、** または**FTP**します。  
  
-   **ステータス**します。 この省略可能なプロパティなど、エンドポイントの状態は、 **Published**または**保留**します。 UDDI 発行サービスでは、この属性を使用して、エンドポイントの状態を検出します。  
  
-   **BindingType**します。 この省略可能なプロパティは、UDDI バインドをサポートするなど特定のプロトコル (URL の種類) **mailto、http、https、ftp、fax、電話番号、** または**他**します。 UDDI 発行サービスでは、この属性を使用して、エンドポイントのバインディングを作成します。