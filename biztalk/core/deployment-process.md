---
title: 展開プロセス |Microsoft ドキュメント
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
ms.openlocfilehash: 21be32ec58c90c1fb95134a002bee82ef5d78fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240666"
---
# <a name="deployment-process"></a>展開プロセス
次の手順は、エンタープライズ シングル サインオンの、セキュリティで保護された展開の概要です。 SQL Server で実行する操作の詳細な手順については、SQL Server のドキュメントを参照してください。  
  
1.  SQL Server ドメイン コントローラで、新しい信頼ウィザードを実行して、次のプロパティを指定した信頼関係を作成します。  
  
    -   **[名前]:** ORCH.com  
  
    -   **方向:** 双方向  
  
    -   **辺:** このドメインのみ  
  
    -   **出力方向の信頼認証レベル--ローカル ドメイン:** 認証の選択  
  
    -   **パスワード:** のパスワードを選択  
  
    -   **出力方向の信頼の確認:** [はい]  
  
    -   **入力方向の信頼の確認:** なし  
  
2.  ORCH.com ドメイン コントローラで新しい信頼ウィザードを実行し、次のプロパティを指定した信頼関係を作成します。  
  
    -   **[名前]:** SQL.com  
  
    -   **方向:** 双方向  
  
    -   **辺:** このドメインのみ  
  
    -   **出力方向の信頼認証レベル--ローカル ドメイン:** 認証の選択  
  
    -   **パスワード:** ORCH.com のパスワードと同じである必要があります  
  
    -   **出力方向の信頼の確認:** [はい]  
  
    -   **入力方向の信頼の確認:** なし  
  
3.  ORCH.com ドメイン コントローラで、SQL.com からの着信に対してドメイン レベルの信頼関係を設定します。  
  
4.  SQL.com ドメイン コントローラで、ORCH.com からの送信に対してドメイン レベルの信頼関係を設定します。  
  
5.  ORCH.com ドメイン コントローラーで、ドメインの機能レベルを Windows Server 2008 SP2 または Windows Server 2008 R2 に上げます。  
  
6.  ORCH.com ドメインに次の新しいユーザーを作成します。  
  
    -   ORCH\SSOSvcUser  
  
    -   ORCH\TestAppUser  
  
    -   ORCH\AffAppUser  
  
7.  追加**オペレーティング システムの一部として動作する**SSOSvcUser と TestAppUser にします。  
  
8.  追加**認証を許可されている**orch \testadmin する権限です。  
  
9. ORCH\SSOSvcUser ユーザーを SQL.com ドメインの SQL2 コンピューターに追加します  (この手順では、Active Directory MMC の詳細ビューを使用する必要があります)。  
  
10. SQL2 コンピュータに、次の 2 つの新しいログインを作成します。  
  
    -   ORCH\TestAdmin  
  
    -   ORCH\SSOSvcUser  
  
11. SQL2 ドメインに、次の 2 つのドメイン グローバル グループを作成します。  
  
    -   ORCH\SSOAdminGroup  
  
    -   ORCH\SSOAffAdminGroup  
  
12. 追加**認証を許可されている**\ssoadmingroup グループに権限です。  
  
13. SQL2 データベースに、次の新しいログインを作成します。  
  
    -   ORCH\SSOAdminGroup  
  
14. 次の手順に従って、マスタ シークレット サーバーをインストールします。  
  
    -   ORCH\TestAdmin を使用して NTS5 にログオンします。  
  
    -   SQL2 コンピュータをマスタ シークレット サーバーとして使用して、ESSO をインストールします。  
  
15. ORCH\TestAdmin を使用して HIS1 にログオンし、エンタープライズ シングル サインオンをインストールします。 データベース サーバー名 SQL2 を使用して、ESSO を HIS2 に参加する SSO として構成します。  
  
16. ORCH\TestAdmin を使用して HIS3 にエンタープライズ シングル サインオンの管理ユーティリティをインストールします。  
  
17. 次のようにユーザーをグループに追加します。  
  
    -   ORCH\TestAppUser ユーザーを ORCH\SSOAdminGroup グループに追加します  
  
    -   ORCH\AffAppUser ユーザーを ORCH\TestAffUserGroup グループに追加します  
  
18. HIS3 に SQL Server Enterprise Edition をインストールし、ログイン ORCH\AffAppUser を追加します。  
  
19. HIS1 コンピュータでコマンド プロンプトを開き、次のコマンドを使用して制約付き委任とプロトコル遷移を設定します。  
  
    -   **setspn-a MSSQLSvc/HIS3.ORCH.com:1433 \ssosvcuser**  
  
    -   **setspn-a MSSQLSvc/HIS3.ORCH.com:1433 orch \testappuser**  
  
20. **\Ssosvcuser**と**orch \testappuser**プロパティ ページは、次のオプションを選択して両方のユーザー アカウントに対して適切な委任を設定します。  
  
    -   **このユーザーに指定されたサービスのみ委任に対して信頼します。**  
  
    -   **任意の認証プロトコルを使用します。**  
  
21. ORCH\TestAdmin を使用して、HIS1 コンピュータで次の手順を実行します。  
  
    -   ORCH\TestAppUser を Remote Desktop User グループに追加します。  
  
    -   Grant**が認証された後の権限を借用**\ssosvcuser する権限  
  
    -   Grant**が認証された後の権限を借用**orch \testappuser する権限  
  
22. ORCH\TestAppUser を使用して HIS1 にログオンし、次のアプリケーション構成を実行して、展開の状態を確認します。  
  
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