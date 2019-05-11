---
title: SSO ユーザー グループ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- groups, SSO
- user accounts, administrators
- service accounts, SSO
- SSO, user groups
- SSO, service accounts
- SSO, administrator accounts
ms.assetid: e279001e-c724-4a2d-8939-0ba9dd08a19c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd38c0417c84f7130a40f54fb684b01b6b853623
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398950"
---
# <a name="sso-user-groups"></a>SSO ユーザー グループ
で構成して、エンタープライズ シングル サインオン (SSO) システムを管理するには、これらの各ロールの特定の Windows グループとアカウントを作成する必要があります。 エンタープライズ SSO でアクセス アカウントを構成するときに、これらの各ロールの 1 つ以上のアカウントを指定できます。 このセクションでは、これらの役割について説明します。  
  
> [!IMPORTANT]
>  SSO を構成するときに、ドメイン グループを使用することを強くお勧めします。  
  
> [!NOTE]
>  セキュリティのために、SSO システムにビルトイン アカウントはできません。  
  
## <a name="single-sign-on-administrators"></a>シングル サインオン管理者  
 SSO 管理者では、SSO システムで最高レベルのユーザー権限を持っています。 設定できます。  
  
- 作成し、SSO データベースの管理  
  
- 作成し、マスター シークレットの管理  
  
- 有効にして、SSO システムを無効にします。  
  
- パスワード同期アダプターを作成します。  
  
- 有効にして、SSO システムでパスワード同期を無効にします。  
  
- 有効にして、ホスト側開始 SSO を無効にします。  
  
- すべての管理タスクを実行します。  
  
  SSO 管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。 SSO 管理者アカウントはドメインまたはローカル グループまたは個々 のアカウントのいずれかにもできます。 個々 のアカウントを使用する場合は、別の単独アカウントをこのアカウントを変更することはできません。 そのため、個別のアカウントを使用しないことをお勧めします。 元のアカウントが、新しいアカウントのメンバーである限りは、グループ アカウントにこのアカウントを変更できます。  
  
> [!IMPORTANT]
>  エンタープライズ シングル サインオン サービスを実行するサービス アカウントは、このアカウントのメンバーである必要があります。 環境をセキュリティで保護するには、他のサービスが、同じサービス アカウントを使用していないことを確認します。  
  
## <a name="single-sign-on-affiliate-administrators"></a>シングル サインオン関連管理者  
 SSO 関連管理者は、SSO システムを含む関連アプリケーションを定義します。 関連アプリケーションが接続先 SSO を使用してバックエンド システムを表す論理エンティティです。 SSO 関連管理者は。  
  
- 作成、管理、および関連アプリケーションの削除  
  
- 各関連アプリケーションのアプリケーション管理者アカウントを指定します。  
  
- アプリケーション管理者およびアプリケーションのユーザーが可能なすべての管理タスクを実行します。  
  
  SSO 関連管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。 SSO 関連管理者アカウントはドメインまたはローカル グループまたはアカウントのいずれかにもできます。  
  
## <a name="application-administrators"></a>アプリケーション管理者  
 関連アプリケーションごとに 1 つのアプリケーション管理者グループがあります。  
  
 このグループのメンバーは次のとおりです。  
  
-   アプリケーションのユーザー グループ アカウントを変更します。  
  
-   作成、削除、および特定の関連アプリケーションのすべてのユーザーの資格情報マッピングの管理  
  
-   特定の関連アプリケーション ユーザー グループ アカウントですべてのユーザーの資格情報を設定します。  
  
-   アプリケーションのユーザーが可能なすべての管理タスクを実行します。  
  
## <a name="application-users"></a>アプリケーション ユーザー  
 関連アプリケーションごとに 1 つのアプリケーション ユーザー グループ アカウントがあります。 このアカウントには、エンタープライズ シングル サインオン環境でのエンドユーザーの一覧が含まれています。 このアカウントのメンバーは次のとおりです。  
  
-   関連アプリケーションでの資格情報の検索します。  
  
-   関連アプリケーションで資格情報マッピングを管理します。  
  
> [!NOTE]
>  グループを割り当てるときに、警戒してください。 たとえば、SSO アプリケーション ユーザー グループの BizTalk Server のセキュリティ ユーザー グループを使用するは可能であれば、です。 これを実行する前に、すべてのユーザーが使用可能になるすべてのアクセスを必要があることが確認をしてください。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)   
 [SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md)   
 [ユーザー マッピングの管理](../core/managing-user-mappings.md)   
 [SSO について](../core/understanding-sso.md)