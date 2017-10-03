---
title: "SSO データベースを更新する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tickets [SSO], modifying
- managing [SSO], modifying Credential cache timeout
- tickets [SSO], timeouts
- modifying, SSO database
- managing [SSO], modifying ticket timeouts
- SSO database, modifying
ms.assetid: 45eb6a77-d91a-44a8-b26d-05508c288c36
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1381ee4e5c2b90a96c52b59d125ec3121af02a4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-sso-database"></a>SSO データベースを更新する方法
SSO データベースのグローバル情報 (マスター シークレット サーバー ID、アカウント名、データベースの監査、チケットのタイムアウト、資格情報キャッシュのタイムアウトなど) は、MMC スナップインまたはコマンド ラインを使用して変更できます。  
  
## <a name="changing-timeouts-for-the-sso-system"></a>SSO システムのタイムアウトを変更する  
 エンタープライズ シングル サインオン (SSO) システム レベルでは、次の 2 つのタイムアウトを変更できます。  
  
 **チケットのタイムアウト。** このプロパティは、チケット SSO 問題の有効期間の長さを指定します。 SSO を使用する企業の大半のシナリオを満たすために、チケットのタイムアウトの既定値は 2 分に設定されています。 SSO 管理者は、アプリケーションの要件に基づいてこの値を変更できます。  
  
 **資格情報キャッシュ タイムアウトをします。** このプロパティは、すべての SSO サーバーの資格情報キャッシュ タイムアウトを指定します。 SSO サーバーは、資格情報を最初に検索した後でキャッシュします。 既定では、資格情報キャッシュ タイムアウトは、60 分です。 SSO 管理者は、セキュリティ要件に基づいて、この値を適切な値に変更できます。  
  
 SSO データベースを更新して、これらのタイムアウトの両方を変更します。  
  
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
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**プロパティ**です。  
  
4.  **システム プロパティ**ダイアログ ボックスで、をクリックして、**全般** タブ。  
  
5.  適切な設定を入力し、クリックして**OK**です。  
  
#### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a>MMC スナップインを使用して SSO データベースを更新するには  
  
1.  **開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、クリックして**SSO 管理**です。  
  
2.  ENTSSO MMC スナップインの [スコープ] ウィンドウで、展開、**エンタープライズ シングル サインオン**ノード。  
  
3.  右クリック**システム**、クリックして**データベースのアップグレード**です。  
  
#### <a name="to-update-the-sso-database-using-the-command-line"></a>コマンド ラインを使用して SSO データベースを更新するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、し、入力**cmd**です。  
  
2.  コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。 既定のインストール ディレクトリは*\<ドライブ >*: \program files \common files \enterprise シングル サインオンします。  
  
3.  型**ssomanage – updatedb\<更新プログラム ファイル >**ここで、 **\<更新プログラム ファイル >**はパスとファイルの名前。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md)   
 [SSO の使用](../core/using-sso.md)