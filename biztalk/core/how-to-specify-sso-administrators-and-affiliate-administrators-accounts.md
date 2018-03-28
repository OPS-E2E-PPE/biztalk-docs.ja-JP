---
title: SSO 管理者を指定し、関連管理者アカウントをどのように |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c96e2d99bd6071098a65b3635bb466de44a455d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-specify-sso-administrators-and-affiliate-administrators-accounts"></a>SSO 管理者を指定し、関連管理者アカウント方法
エンタープライズ シングル サインオン (SSO) 管理者アカウントと関連管理者アカウントは、ホスト グループまたは個別のアカウントにすることができます。 これらのアカウントは、SSO システムを構成する前に作成しておく必要があります。  
  
 ドメイン アカウントを使用する場合する必要があります、SSO 管理者および SSO 関連管理者アカウント ドメインとしてグローバル セキュリティ グループを作成ドメイン コント ローラーです。 これらのアカウントは、ドメイン管理者が作成します。  
  
 シングル サインオン管理者アカウントと関連管理者アカウントは、SSO データベースで指定する必要があります。 SSO データベースを更新して SSO 管理者グループを指定する場合、更新する前にシングル サインオン システムを無効にする必要があります。  
  
 次の XML コードは、SSO データベースを更新する場合のサンプル XML です。  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
</globalInfo>  
</sso>  
```  
  
> [!NOTE]
>  構成ウィザードでは、SSO データベースの SSO 管理者グループと SSO 関連管理者グループが自動的に指定されます。  
  
> [!NOTE]
>  SSO が構成されない場合、ユーザーがドメイン ローカル アカウントが、混在モード ドメインで使用されているかどうかを確認する必要があります。  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a>MMC スナップインでエンタープライズ シングル サインオン システムを無効にするには  
  
1.  **開始**  メニューのをクリックして **すべてのプログラム**, 、 をクリックして **Microsoft エンタープライズ シングル サインオン**, 、 をクリックし、 **SSO 管理**します。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  右クリック **システム**, 、クリックして **を無効にする**です。  
  
### <a name="to-disable-the-enterprise-single-sign-on-system-using-the-command-line"></a>コマンド ラインでエンタープライズ シングル サインオン システムを無効にするには  
  
1.  **開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは\<*ドライブ*\>: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 **ssomanage** –**disablesso**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a>MMC スナップインを使用して SSO データベースを更新するには  
  
1.  **開始**  メニューのをクリックして **すべてのプログラム**, 、**Microsoft エンタープライズ シングル サインオン**, 、し **SSO 管理**します。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  右クリック **システム**, 、クリックして **更新**します。  
  
### <a name="to-update-the-sso-database-using-the-command-line"></a>コマンド ラインを使用して SSO データベースを更新するには  
  
1.  **開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 * * ssomanage – updatedb *\<更新ファイル\>* * *、どこで*\<更新ファイル\>* XML ファイルの名前とパスは、します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-mmc-snap-in"></a>MMC スナップインでエンタープライズ シングル サインオン システムを有効にするには  
  
1.  **開始**  メニューのをクリックして **すべてのプログラム**, 、**Microsoft エンタープライズ シングル サインオン**, 、し **SSO 管理**します。  
  
2.  ENTSSO MMC スナップインのスコープ ペインで、展開、 **エンタープライズ シングル サインオン** ノードです。  
  
3.  右クリック **システム**, 、クリックして **を有効にする**です。  
  
### <a name="to-enable-the-enterprise-single-sign-on-system-using-the-command-line"></a>コマンド ラインでエンタープライズ シングル サインオン システムを有効にするには  
  
1.  **開始**  メニューのをクリックして **実行**, 、し、入力 **cmd**します。  
  
2.  コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ\>*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型 **ssomanage – enablesso**します。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO ユーザー グループ](../core/sso-user-groups.md)