---
title: "シングル サインオン: イベント 10517 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b63e4b0-0ef6-45c2-b8b1-55ac20e79e26
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2716eb7d331ec5c15070555a028c00310188856c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10517"></a>シングル サインオン: イベント 10517
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10517|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_ERROR_BAD_SSO_ADMIN|  
|メッセージ テキスト|SSO 管理者アカウントが無効です。 これがローカル アカウントである場合、このアカウントがサーバーに存在することを確認します。 ドメイン アカウントである場合、ドメイン管理者に問い合わせてください。 アカウントが有効である場合は SSO を有効にします。%r<br /><br /> SSO 管理者: %1 %r<br /><br /> 無効なアカウント: %2 %r<br /><br /> エラー コード: %3|  
  
## <a name="explanation"></a>説明  
 このエラー イベントは、エンタープライズ シングル サインオンについて指定されている SSO 管理者アカウントが、有効な Windows アカウントではないことを示します。 エンタープライズ シングル サインオン サービスを実行しているサービス アカウントは、このグループのメンバである必要があります。 SSO 管理者アカウントには、Windows グループ アカウントまたは単独アカウントのいずれかを指定できます。 また、ドメインまたはローカルのグループ アカウントを指定することもできます。 単独アカウントを使用すると、このアカウントを別の単独アカウントに変更できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  
  
-   SSO 管理者アカウントが存在することを確認します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO ユーザー グループ](../core/sso-user-groups.md)