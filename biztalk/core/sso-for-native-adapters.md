---
title: ネイティブ アダプターの SSO |Microsoft Docs
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
ms.openlocfilehash: 7d526f9b3cfc0e6b749469151606f4ae19ce454f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258594"
---
# <a name="sso-for-native-adapters"></a>ネイティブ アダプターの SSO
エンタープライズ シングル サインオン (SSO) では、別のコンピューター システムや Web サイトとの相互運用時 1 回だけサインインすることができます。 この機能を Microsoft の[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]により、BizTalk アダプターで、適切なユーザー ID と、Microsoft Windows 資格情報に基づいて、一般的な認証メカニズムを使用して、ネットワーク内の複数のアプリケーションへの資格情報を提供します。 Windows は、資格情報を認証した後は、アプリケーションに接続する追加の資格情報を提供する必要はありません。  
  
 既定で無効になっていることには、SSO を使用することは、HTTP および SOAP アダプターの使用です。 HTTP アダプターの送信ポートの構成し、受信場所で SSO を使用するにはSOAP アダプタは、SSO を使用する受信場所のみを構成できます。 どちらのアダプターには、BizTalk Server 管理コンソールを使用して SSO を構成します。  
  
 SSO での認証は、主に Windows 認証と Active Directory で作成された Windows グループに依存しています。 ユーザーまたは sso 管理者が完了したすべての操作では、Windows 認証するユーザーまたは管理者最初が必要です。  
  
 HTTP および SOAP アダプターと SSO のしくみについての詳細については、「参照」の該当するトピックを参照してください。  
  
## <a name="see-also"></a>参照  
 [SSO を使用してください。](../core/using-sso.md)   
 [HTTP アダプター](../core/http-adapter.md)   
 [SOAP アダプター](../core/soap-adapter.md)