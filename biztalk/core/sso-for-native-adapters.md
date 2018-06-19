---
title: ネイティブ アダプターの SSO |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, SSO
- SSO, adapters
ms.assetid: d8527f0f-910c-42ce-9bd3-83ab6d4349c0
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45aaf357d943853cc9504762437f554f1d28efb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278058"
---
# <a name="sso-for-native-adapters"></a>ネイティブ アダプターの SSO
エンタープライズ シングル サインオン (SSO) を使用すると、さまざまなコンピューター システムや Web サイトと相互運用する際にサインオンの回数が 1 回で済みます。 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のこの機能により、BizTalk アダプターは、ネットワーク内で共通の認証メカニズムを使用している複数のアプリケーションに対し、Microsoft Windows の資格情報に基づいて、適切なユーザー ID および資格情報を提供できます。 Windows によって資格情報が認証された後は、アプリケーションへの接続に他の資格情報を指定する必要はありません。  
  
 SSO は、HTTP アダプターおよび SOAP アダプターに使用できますが、既定では無効になっています。 HTTP アダプターでは、送信ポートおよび受信場所の両方を SSO を使用するように構成できます。また、SOAP アダプターでは、受信場所のみを、SSO を使用するように構成できます。 どちらのアダプターでも、BizTalk Server 管理コンソールを使用して SSO を構成します。  
  
 SSO での認証は、主に、Windows 認証、および Active Directory で作成された Windows グループに依存しています。 SSO でユーザーまたは管理者が完了するすべての操作では、最初に、Windows によってユーザーまたは管理者を認証する必要があります。  
  
 SSO と HTTP アダプターおよび SOAP アダプターとの連携の詳細については、「関連項目」の該当するトピックを参照してください。  
  
## <a name="see-also"></a>参照  
 [SSO の使用](../core/using-sso.md)   
 [HTTP アダプター](../core/http-adapter.md)   
 [SOAP アダプター](../core/soap-adapter.md)