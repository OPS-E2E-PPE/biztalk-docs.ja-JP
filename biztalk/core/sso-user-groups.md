---
title: "SSO ユーザー グループ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 949f3aa72771982321abf6904c43352b8821fc0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sso-user-groups"></a>SSO ユーザー グループ
エンタープライズ シングル サインオン (SSO) システムを構成および管理するには、ロールごとに特定の Windows グループとアカウントを作成する必要があります。 エンタープライズ SSO でアクセス アカウントを構成する際には、各ロールに複数のアカウントを指定することができます。 このセクションでは、各ロールについて説明します。  
  
> [!IMPORTANT]
>  SSO を構成する際には、ドメイン グループを使用することを強くお勧めします。  
  
> [!NOTE]
>  セキュリティ上の理由から、SSO システムでは組み込みアカウントは使用できません。  
  
## <a name="single-sign-on-administrators"></a>シングル サインオン管理者  
 SSO 管理者には、SSO システムで最高レベルのユーザー権利が与えられています。 SSO 管理者は、次の操作を実行できます。  
  
-   SSO データベースの作成および管理  
  
-   マスタ シークレットの作成および管理  
  
-   SSO システムの有効化および無効化  
  
-   パスワード同期アダプタの作成  
  
-   SSO システムでのパスワード同期の有効化および無効化  
  
-   ホスト側開始 SSO の有効化および無効化  
  
-   すべての管理作業の実行  
  
 SSO 管理者アカウントは、Windows グループ アカウントまたは単独アカウントのいずれかにできます。 また、ドメインまたはローカルのグループや単独アカウントのいずれかを指定することもできます。 単独アカウントを使用すると、このアカウントを別の単独アカウントに変更できません。 そのため、単独アカウントは使用しないことをお勧めします。 元のアカウントが新しいグループのメンバであれば、単独アカウントをグループ アカウントに変更できます。  
  
> [!IMPORTANT]
>  エンタープライズ シングル サインオン サービスを実行しているサービス アカウントは、このグループのメンバである必要があります。 環境をセキュリティで保護するために、同じサービス アカウントが他のサービスで使用されていないことを確認してください。  
  
## <a name="single-sign-on-affiliate-administrators"></a>シングル サインオン関連管理者  
 SSO 関連管理者は、SSO システムに含まれる関連アプリケーションを定義します。 関連アプリケーションとは、SSO を使用して接続するバックエンド システムを表す論理エンティティのことです。 SSO 関連管理者は、次の操作を実行できます。  
  
-   関連アプリケーションの作成、管理、および削除  
  
-   各関連アプリケーションに対するアプリケーション管理者アカウントの指定  
  
-   アプリケーション管理者とアプリケーション ユーザーが実行できるすべての管理作業の実行  
  
 SSO 関連管理者アカウントには、Windows グループ アカウントまたは単独アカウントのいずれかを指定できます。 また、ドメインまたはローカルのグループやアカウントのいずれかを指定することもできます。  
  
## <a name="application-administrators"></a>アプリケーション管理者  
 アプリケーション管理者グループは、関連アプリケーションごとに 1 つ存在します。  
  
 このグループのメンバーを実行できます。  
  
-   アプリケーション ユーザー グループ アカウントの変更  
  
-   特定の関連アプリケーションのすべてのユーザーに対する資格情報マッピングの作成、削除、および管理  
  
-   特定の関連アプリケーション ユーザー グループ アカウントのすべてのユーザーに対する資格情報の設定  
  
-   アプリケーション ユーザーが実行できるすべての管理作業の実行  
  
## <a name="application-users"></a>アプリケーション ユーザー  
 アプリケーション ユーザー グループは、関連アプリケーションごとに 1 つ存在します。 このグループには、エンタープライズ シングル サインオン環境に存在するエンド ユーザーの一覧が含まれています。 このグループのメンバは、次の操作を実行できます。  
  
-   関連アプリケーションでの資格情報の検索  
  
-   関連アプリケーションでの資格情報マッピングの管理  
  
> [!NOTE]
>  グループを割り当てる際には注意する必要があります。 たとえば、SSO アプリケーション ユーザー グループに BizTalk Server セキュリティ ユーザー グループを使用することができます。 グループを割り当てる前に、ユーザーに与えられるアクセス権が、そのユーザーに必要かどうかを確認してください。  
  
## <a name="see-also"></a>参照  
 [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)   
 [SSO データベースを更新する方法](../core/how-to-update-the-sso-database.md)   
 [ユーザー マッピングを管理します。](../core/managing-user-mappings.md)   
 [SSO について](../core/understanding-sso.md)