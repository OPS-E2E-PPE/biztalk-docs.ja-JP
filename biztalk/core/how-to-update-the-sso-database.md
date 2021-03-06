---
title: SSO データベースを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tickets [SSO], modifying
- managing [SSO], modifying Credential cache timeout
- tickets [SSO], timeouts
- modifying, SSO database
- managing [SSO], modifying ticket timeouts
- SSO database, modifying
ms.assetid: 45eb6a77-d91a-44a8-b26d-05508c288c36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a970bf80e5aa6e67913976426c0dbe2ba21c47e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383569"
---
# <a name="how-to-update-the-sso-database"></a>SSO データベースを更新する方法
MMC スナップインまたはコマンドラインを使用して、データベース、チケットのタイムアウト、および資格情報キャッシュ タイムアウト、監査などのアカウント名をマスター シークレット サーバー id、SSO データベースのグローバル情報を変更できます。  
  
## <a name="changing-timeouts-for-the-sso-system"></a>SSO システムのタイムアウトを変更します。  
 エンタープライズ シングル サインオン (SSO) システム レベルの 2 つのタイムアウトを変更することができます。  
  
 **チケットのタイムアウト。** このプロパティは、チケットの SSO の問題の有効期間の長さを指定します。 ほとんどの企業での SSO を使用するシナリオを満たすために既定のチケットのタイムアウトは 2 分です。 SSO 管理者は、アプリケーションの要件に基づいて変更できます。  
  
 **資格情報キャッシュ タイムアウト。** このプロパティは、すべての SSO サーバーの資格情報キャッシュのタイムアウトを指定します。 SSO サーバーを最初に検索した後、資格情報をキャッシュします。 既定では、資格情報キャッシュ タイムアウトは 60 分です。 SSO 管理者は、セキュリティ要件に基づいて適切な値にこれを変更できます。  
  
 これらのタイムアウトの両方を変更するには、SSO データベースを更新することで。  
  
 SSO データベースを更新するためのサンプル XML ファイルは次のとおりです。  
  
```  
<sso>  
<globalInfo>  
<ssoAdminAccount>Domain\Accountname</ssoAdminAccount>  
<ssoAffiliateAdminAccount>Domain\Accountname</ssoAffiliateAdminAccount>  
<secretServer>ComputerA</secretServer>  
<auditDeletedApps>1000</auditDeletedApps>  
<auditDeletedMappings>1000</auditDeletedMappings>  
<auditCredentialLookups>1000</auditCredentialLookups>  
<ticketTimeout>2</ticketTimeout>  
<credCacheTimeout>60</credCacheTimeout>  
</globalInfo>  
</sso>  
  
```  
  
#### <a name="to-change-timeouts-using-the-mmc-snap-in"></a>MMC スナップインを使用してタイムアウトを変更するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリックして**システム**、 をクリックし、**プロパティ**します。  
  
4.  **システム プロパティ**ダイアログ ボックスで、をクリックして、**全般** タブ。  
  
5.  適切な設定を入力し、クリックして**OK**します。  
  
#### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a>MMC スナップインを使用して SSO データベースを更新するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリックして**システム**、 をクリックし、**データベースのアップグレード**します。  
  
#### <a name="to-update-the-sso-database-using-the-command-line"></a>コマンドラインを使用して SSO データベースを更新するには  
  
1.  クリックして**開始**、 をクリックして**実行**、し、入力**cmd**します。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは *\<ドライブ\>* : \Program Files\Common \enterprise シングル サインオンします。  
  
3.  型**ssomanage – updatedb\<更新ファイル\>** ここで、 **\<更新ファイル\>** はパスとファイルの名前。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md)   
 [SSO の使用](../core/using-sso.md)