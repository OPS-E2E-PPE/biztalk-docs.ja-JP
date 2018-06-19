---
title: 'シングル サインオン: イベント 10516 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d20df92f-c995-4cbc-a8f9-21cea30b82c9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b74ca4a47bc62d28b25564bd5843729c56362
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269898"
---
# <a name="single-sign-on-event-10516"></a>シングル サインオン: イベント 10516
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10516|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_BAD_SSO_APP_ADMIN|  
|メッセージ テキスト|SSO 関連管理者アカウントが無効です。 これがローカル アカウントである場合、このアカウントがサーバーに存在することを確認します。 ドメイン アカウントである場合、ドメイン管理者に問い合わせてください。 アカウントが有効である場合は SSO を有効にします。%r<br /><br /> SSO 関連管理者: %1 %r<br /><br /> 無効なアカウント: %2 %r<br /><br /> エラー コード: %3|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、エンタープライズ シングル サインオンによって作成された SSO 関連管理者アカウントまたはグループが有効な Windows アカウントではないことを示します。 SSO 関連管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。 また、ドメインまたはローカル グループ アカウントのいずれかを指定することもできます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
-   SSO 関連管理者アカウントが存在することを確認します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO ユーザー グループ](../core/sso-user-groups.md)  
  
-   [SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md)