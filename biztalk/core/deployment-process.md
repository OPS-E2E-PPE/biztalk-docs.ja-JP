---
title: 展開プロセス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying
- deploying, SSO
- LogonExternalUser test [SSO]
- security, SSO
- SSO, LogonExternalUser test
- SSO, security
ms.assetid: 7dd4c022-c70b-467a-bf94-dc4ac6029f81
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89b5e3640626ce63a58532568b08b7290bc40c4c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389743"
---
# <a name="deployment-process"></a>展開プロセス
次の手順では、エンタープライズ シングル サインオンのセキュリティで保護された展開の概要を説明します。 SQL Server で実行するアクションに関する詳細な手順は、SQL Server のドキュメントを参照してください。  
  
1.  SQL Server のドメイン コント ローラーで、次のプロパティで信頼を作成するのに、新しい信頼ウィザードを使用します。  
  
    -   **名:** ORCH.com  
  
    -   **方向:** 双方向  
  
    -   **両側:** このドメインのみ  
  
    -   **出力方向の信頼認証レベル--ローカル ドメイン:** 認証の選択  
  
    -   **パスワード:** パスワードを選択します。  
  
    -   **出力方向の信頼を確認します。** はい  
  
    -   **入力方向の信頼を確認します。** いいえ  
  
2.  ORCH.com ドメイン コント ローラーで、次のプロパティで信頼を作成するのに、新しい信頼ウィザードを使用します。  
  
    -   **名:** SQL.com  
  
    -   **方向:** 双方向  
  
    -   **両側:** このドメインのみ  
  
    -   **出力方向の信頼認証レベル--ローカル ドメイン:** 認証の選択  
  
    -   **パスワード:** ORCH.com のパスワードと同じである必要があります。  
  
    -   **出力方向の信頼を確認します。** はい  
  
    -   **入力方向の信頼を確認します。** いいえ  
  
3.  ORCH.com ドメイン コント ローラーで、SQL.COM から受信ドメイン レベルの信頼関係を設定します。  
  
4.  SQL.com ドメイン コント ローラーで、ORCH.COM から送信に対してドメイン レベルの信頼関係を設定します。  
  
5.  ORCH.com ドメイン コント ローラーには、Windows Server 2008 SP2 または Windows Server 2008 R2 ドメイン機能レベルを上げます。  
  
6.  ORCH ドメインでは、次の新しいユーザーを作成します。  
  
    -   ORCH\SSOSvcUser  
  
    -   ORCH\TestAppUser  
  
    -   ORCH\AffAppUser  
  
7.  追加**オペレーティング システムの一部として機能**SSOSvcUser と TestAppUser にします。  
  
8.  追加**認証を許可されている**orch \testadmin する権限。  
  
9. SQL ドメインの SQL2 に \ssosvcuser を追加します。 (この手順が必要で Active Directory MMC 詳細ビューを使用します。)  
  
10. SQL2 コンピュータに、次の 2 つの新しいログインを作成します。  
  
    -   ORCH\TestAdmin  
  
    -   ORCH\SSOSvcUser  
  
11. SQL2 ドメインに、2 つのドメイン グローバル グループを作成します。  
  
    -   ORCH\SSOAdminGroup  
  
    -   ORCH\SSOAffAdminGroup  
  
12. 追加**認証を許可されている**\ssoadmingroup グループに特権。  
  
13. SQL2 データベースでは、次の新しいログインを作成します。  
  
    -   ORCH\SSOAdminGroup  
  
14. 次のように、マスター シークレット サーバーをインストールします。  
  
    -   Orch \testadmin を使用して NTS5 にログオンします。  
  
    -   マスター シークレット サーバーとして SQL2 を使用して、ESSO をインストールします。  
  
15. Orch \testadmin を使用して HIS1 にログオンし、エンタープライズ シングル サインオンをインストールします。 データベース サーバー名 SQL2 を使用して、HIS2 に参加する SSO として ESSO を構成します。  
  
16. Orch \testadmin を使用して HIS3 にエンタープライズ シングル サインオンの管理ユーティリティをインストールします。  
  
17. 次のグループには、次のユーザーを追加します。  
  
    -   Orch \testappuser を \ssoadmingroup に追加します。  
  
    -   \Testaffusergroup に \affappuser を追加します。  
  
18. His3、SQL Server Enterprise Edition をインストールし、ログイン \affappuser を追加します。  
  
19. コマンド プロンプトを開き、HIS1 コンピュータでとを設定する、次のコマンドを使用して委任とプロトコル遷移の制限します。  
  
    -   **setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**  
  
    -   **setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**  
  
20. **\Ssosvcuser**と**orch \testappuser**プロパティ ページでは、次のオプションを選択して両方のユーザー アカウントに対して適切な委任を設定します。  
  
    -   **指定されたサービスのみへの委任では、このユーザーを信頼します。**  
  
    -   **任意の認証プロトコルを使用して、**  
  
21. Orch \testadmin を使用して、HIS1 コンピュータで、次を実行します。  
  
    -   Orch \testappuser を Remote Desktop User グループに追加します。  
  
    -   Grant**認証された後の権限を借用**\ssosvcuser する権限  
  
    -   Grant**認証された後の権限を借用**orch \testappuser を特権  
  
22. HIS1 にログオンして、デプロイを確認します。 orch \testappuser を使用すると、次のアプリケーションの構成を実行します。  
  
     LogonExternalUser テストを実行します。  
  
    ```  
    <SSO>  
       <application name="TestApp">  
          <description>An SSO Test Affiliate Application</description>  
          <contact>AffAppUser@ESSOV2.EBiz.Com</contact>  
          <appUserAccount>ORCH\TestAffAdminGroup</appUserAccount>  
          <appAdminAccount>ORCH\TestAffUserGroup</appAdminAccount>  
          <field ordinal="0" label="User ID" masked="no" />  
          <field ordinal="1" label="Password" masked="yes" />  
          <flags   
             groupApp="no"   
             configStoreApp="no"   
             allowTickets="no"   
             validateTickets="yes"   
             allowLocalGroups="yes"   
             ticketTimeout="yes"   
             adminGroupSame="no"   
             enableApp="yes"   
             hostInitiatedSSO="yes"   
             validatePassword="yes"/>  
       </application>  
    </SSO>  
  
    ```  
  
## <a name="see-also"></a>参照  
 [SSO 展開の概要](../core/sso-deployment-overview.md)