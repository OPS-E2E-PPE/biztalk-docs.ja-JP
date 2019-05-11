---
title: SSO 管理者を指定し、関連管理者アカウントをどのように |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- administrator accounts, SSO
- enabling, SSO
- SSO, enabling
- disabling, SSO
- SSO, disabling
- managing [SSO], configuring administrator accounts
- managing [SSO], enabling
- managing [SSO], disabling
- SSO, administrator accounts
ms.assetid: 6c300e09-b781-45de-b2da-b1083164a1c0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faff8a6a8b8b9a639c4e03c4c48c287835667238
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383848"
---
# <a name="how-to-specify-sso-administrators-and-affiliate-administrators-accounts"></a>SSO 管理者を指定し、関連管理者アカウントの方法
エンタープライズ シングル サインオン (SSO) 管理者および関連管理者アカウントには、ホスト グループまたは個々 のアカウントを指定できます。 SSO システムを構成する前に、これらのアカウントを作成する必要があります。  
  
 ドメイン アカウントを使用する場合をする必要があります、SSO 管理者および SSO 関連管理者アカウント ドメインとしてグローバル セキュリティ グループを作成、ドメイン コント ローラーで。 ドメイン管理者は、これらのアカウントを作成する必要があります。  
  
 SSO データベースで、シングル サインオン管理者および関連管理者アカウントを指定する必要があります。 SSO 管理者グループと SSO データベースを更新する前に、シングル サインオン システムを無効にする必要があります。  
  
 次の XML コードは、SSO データベースを更新するためのサンプル XML を示しています。  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
</globalInfo>  
</sso>  
```  
  
> [!NOTE]
>  構成ウィザードでは、SSO 管理者と SSO 関連管理者グループ、SSO データベースで自動的を指定します。  
  
> [!NOTE]
>  SSO を構成しないと、ユーザーがローカル アカウントのドメインが混在モード ドメインで使用されているかどうかを確認する必要があります。  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a>MMC スナップインを使用してエンタープライズ シングル サインオン システムを無効にするには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、 をクリックし、**を無効にする**します。  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-command-line"></a>コマンドラインを使用してエンタープライズ シングル サインオン システムを無効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage** –**disablesso**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a>MMC スナップインを使用して SSO データベースを更新するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 **Microsoft エンタープライズ シングル サインオン**、し**SSO 管理**します。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、 をクリックし、**更新**します。  
  
### <a name="to-update-the-sso-database-using-the-command-line"></a>コマンドラインを使用して SSO データベースを更新するには  
  
1. **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2. コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
3. 型 * * ssomanage – updatedb *\<更新ファイル\>**<em>ここで、*\<更新ファイル\></em>は XML ファイルの名前とパス。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a>MMC スナップインを使用してエンタープライズ シングル サインオン システムを有効にするには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 **Microsoft エンタープライズ シングル サインオン**、し**SSO 管理**します。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、 をクリックし、**を有効にする**します。  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-command-line"></a>コマンドラインを使用してエンタープライズ シングル サインオン システムを有効にするには  
  
1.  **開始** メニューのをクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – enablesso**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO ユーザー グループ](../core/sso-user-groups.md)