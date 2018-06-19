---
title: 'シングル サインオン: イベント 10519 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e709957e-a690-4a44-a863-07b2a55dae7b
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928892ff1d0ee461a26095ddc7a72fd3accecf10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271010"
---
# <a name="single-sign-on-event-10519"></a>シングル サインオン: イベント 10519
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10519|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_BAD_APP_ADMIN_GROUP|  
|メッセージ テキスト|このアプリケーションのアプリケーション管理者アカウントが無効です。 これがローカル アカウントである場合、このアカウントがサーバーに存在することを確認します。 ドメイン アカウントである場合、ドメイン管理者に問い合わせてください。 アカウントが有効である場合は、アプリケーションを有効にします。 このコンピューターでこのアプリケーションを使用しない場合、このメッセージは無視して構いません。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> アプリケーション管理者: %2 %r<br /><br /> 無効なアカウント: %3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、アプリケーション管理者グループ アカウントが有効な Windows アカウントではないことを示します。 アプリケーション管理者アカウント グループは、関連アプリケーションごとに 1 つ存在します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   
  
-   指定したアプリケーション管理者アカウントが存在することを確認します。  
  
-   SSO 管理ユーティリティを使用して、指定した関連アプリケーションが適切なアプリケーション管理者アカウントを使用するように構成されていることを確認します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO ユーザー グループ](../core/sso-user-groups.md)  
  
-   [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)  
  
-   [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)