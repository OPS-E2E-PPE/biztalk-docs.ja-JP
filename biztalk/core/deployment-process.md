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
# <a name="deployment-process"></a><span data-ttu-id="6228c-102">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="6228c-102">Deployment Process</span></span>
<span data-ttu-id="6228c-103">次の手順では、エンタープライズ シングル サインオンのセキュリティで保護された展開の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="6228c-103">The following steps give a high-level overview of secure deployment of Enterprise Single Sign-On.</span></span> <span data-ttu-id="6228c-104">SQL Server で実行するアクションに関する詳細な手順は、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6228c-104">For detailed procedures on the actions to take in SQL Server, see your SQL Server documentation.</span></span>  
  
1.  <span data-ttu-id="6228c-105">SQL Server のドメイン コント ローラーで、次のプロパティで信頼を作成するのに、新しい信頼ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6228c-105">On the SQL Server domain controller, use the New Trust Wizard to create a trust with the following properties:</span></span>  
  
    -   <span data-ttu-id="6228c-106">**名:** ORCH.com</span><span class="sxs-lookup"><span data-stu-id="6228c-106">**Name:** ORCH.com</span></span>  
  
    -   <span data-ttu-id="6228c-107">**方向:** 双方向</span><span class="sxs-lookup"><span data-stu-id="6228c-107">**Direction:** Two-way</span></span>  
  
    -   <span data-ttu-id="6228c-108">**両側:** このドメインのみ</span><span class="sxs-lookup"><span data-stu-id="6228c-108">**Sides:** This domain only</span></span>  
  
    -   <span data-ttu-id="6228c-109">**出力方向の信頼認証レベル--ローカル ドメイン:** 認証の選択</span><span class="sxs-lookup"><span data-stu-id="6228c-109">**Outgoing Trust Authentication Level - Local Domain:** Selective authentication</span></span>  
  
    -   <span data-ttu-id="6228c-110">**パスワード:** パスワードを選択します。</span><span class="sxs-lookup"><span data-stu-id="6228c-110">**Password:** Choose a password</span></span>  
  
    -   <span data-ttu-id="6228c-111">**出力方向の信頼を確認します。** はい</span><span class="sxs-lookup"><span data-stu-id="6228c-111">**Confirm Outgoing Trust:** Yes</span></span>  
  
    -   <span data-ttu-id="6228c-112">**入力方向の信頼を確認します。** いいえ</span><span class="sxs-lookup"><span data-stu-id="6228c-112">**Confirm Incoming Trust:** No</span></span>  
  
2.  <span data-ttu-id="6228c-113">ORCH.com ドメイン コント ローラーで、次のプロパティで信頼を作成するのに、新しい信頼ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="6228c-113">On the ORCH.com domain controller, use the New Trust Wizard to create a trust with the following properties:</span></span>  
  
    -   <span data-ttu-id="6228c-114">**名:** SQL.com</span><span class="sxs-lookup"><span data-stu-id="6228c-114">**Name:** SQL.com</span></span>  
  
    -   <span data-ttu-id="6228c-115">**方向:** 双方向</span><span class="sxs-lookup"><span data-stu-id="6228c-115">**Direction:** Two-way</span></span>  
  
    -   <span data-ttu-id="6228c-116">**両側:** このドメインのみ</span><span class="sxs-lookup"><span data-stu-id="6228c-116">**Sides:** This domain only</span></span>  
  
    -   <span data-ttu-id="6228c-117">**出力方向の信頼認証レベル--ローカル ドメイン:** 認証の選択</span><span class="sxs-lookup"><span data-stu-id="6228c-117">**Outgoing Trust Authentication Level - Local Domain:** Selective authentication</span></span>  
  
    -   <span data-ttu-id="6228c-118">**パスワード:** ORCH.com のパスワードと同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6228c-118">**Password:** Must be the same as password for ORCH.com</span></span>  
  
    -   <span data-ttu-id="6228c-119">**出力方向の信頼を確認します。** はい</span><span class="sxs-lookup"><span data-stu-id="6228c-119">**Confirm Outgoing Trust:** Yes</span></span>  
  
    -   <span data-ttu-id="6228c-120">**入力方向の信頼を確認します。** いいえ</span><span class="sxs-lookup"><span data-stu-id="6228c-120">**Confirm Incoming Trust:** No</span></span>  
  
3.  <span data-ttu-id="6228c-121">ORCH.com ドメイン コント ローラーで、SQL.COM から受信ドメイン レベルの信頼関係を設定します。</span><span class="sxs-lookup"><span data-stu-id="6228c-121">On the ORCH.com domain controller, set the domain wide trust for Incoming from SQL.COM.</span></span>  
  
4.  <span data-ttu-id="6228c-122">SQL.com ドメイン コント ローラーで、ORCH.COM から送信に対してドメイン レベルの信頼関係を設定します。</span><span class="sxs-lookup"><span data-stu-id="6228c-122">On the SQL.com domain controller, set the domain wide trust for Outgoing from ORCH.COM.</span></span>  
  
5.  <span data-ttu-id="6228c-123">ORCH.com ドメイン コント ローラーには、Windows Server 2008 SP2 または Windows Server 2008 R2 ドメイン機能レベルを上げます。</span><span class="sxs-lookup"><span data-stu-id="6228c-123">On the ORCH.com domain controller, raise the domain functional level to Windows Server 2008 SP2 or Windows Server 2008 R2.</span></span>  
  
6.  <span data-ttu-id="6228c-124">ORCH ドメインでは、次の新しいユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6228c-124">In the ORCH domain, create the following new users:</span></span>  
  
    -   <span data-ttu-id="6228c-125">ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="6228c-125">ORCH\SSOSvcUser</span></span>  
  
    -   <span data-ttu-id="6228c-126">ORCH\TestAppUser</span><span class="sxs-lookup"><span data-stu-id="6228c-126">ORCH\TestAppUser</span></span>  
  
    -   <span data-ttu-id="6228c-127">ORCH\AffAppUser</span><span class="sxs-lookup"><span data-stu-id="6228c-127">ORCH\AffAppUser</span></span>  
  
7.  <span data-ttu-id="6228c-128">追加**オペレーティング システムの一部として機能**SSOSvcUser と TestAppUser にします。</span><span class="sxs-lookup"><span data-stu-id="6228c-128">Add **Act as part of the operating system** to SSOSvcUser and TestAppUser.</span></span>  
  
8.  <span data-ttu-id="6228c-129">追加**認証を許可されている**orch \testadmin する権限。</span><span class="sxs-lookup"><span data-stu-id="6228c-129">Add **Allowed to Authenticate** privilege to ORCH\TestAdmin.</span></span>  
  
9. <span data-ttu-id="6228c-130">SQL ドメインの SQL2 に \ssosvcuser を追加します。</span><span class="sxs-lookup"><span data-stu-id="6228c-130">Add ORCH\SSOSvcUser to SQL2 in the SQL domain.</span></span> <span data-ttu-id="6228c-131">(この手順が必要で Active Directory MMC 詳細ビューを使用します。)</span><span class="sxs-lookup"><span data-stu-id="6228c-131">(This step requires using Advanced View in Active Directory MMC.)</span></span>  
  
10. <span data-ttu-id="6228c-132">SQL2 コンピュータに、次の 2 つの新しいログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="6228c-132">On the SQL2 computer, create the following two new logins:</span></span>  
  
    -   <span data-ttu-id="6228c-133">ORCH\TestAdmin</span><span class="sxs-lookup"><span data-stu-id="6228c-133">ORCH\TestAdmin</span></span>  
  
    -   <span data-ttu-id="6228c-134">ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="6228c-134">ORCH\SSOSvcUser</span></span>  
  
11. <span data-ttu-id="6228c-135">SQL2 ドメインに、2 つのドメイン グローバル グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="6228c-135">On the SQL2 domain, create two domain global groups:</span></span>  
  
    -   <span data-ttu-id="6228c-136">ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="6228c-136">ORCH\SSOAdminGroup</span></span>  
  
    -   <span data-ttu-id="6228c-137">ORCH\SSOAffAdminGroup</span><span class="sxs-lookup"><span data-stu-id="6228c-137">ORCH\SSOAffAdminGroup</span></span>  
  
12. <span data-ttu-id="6228c-138">追加**認証を許可されている**\ssoadmingroup グループに特権。</span><span class="sxs-lookup"><span data-stu-id="6228c-138">Add **Allowed to Authenticate** privilege to the ORCH\SSOAdminGroup group.</span></span>  
  
13. <span data-ttu-id="6228c-139">SQL2 データベースでは、次の新しいログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="6228c-139">On the SQL2 database, create the following new login:</span></span>  
  
    -   <span data-ttu-id="6228c-140">ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="6228c-140">ORCH\SSOAdminGroup</span></span>  
  
14. <span data-ttu-id="6228c-141">次のように、マスター シークレット サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6228c-141">Install the Master Secret Server as follows:</span></span>  
  
    -   <span data-ttu-id="6228c-142">Orch \testadmin を使用して NTS5 にログオンします。</span><span class="sxs-lookup"><span data-stu-id="6228c-142">Log on to NTS5 using ORCH\TestAdmin.</span></span>  
  
    -   <span data-ttu-id="6228c-143">マスター シークレット サーバーとして SQL2 を使用して、ESSO をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6228c-143">Install ESSO, using SQL2 as the Master Secret Server.</span></span>  
  
15. <span data-ttu-id="6228c-144">Orch \testadmin を使用して HIS1 にログオンし、エンタープライズ シングル サインオンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6228c-144">Log onto HIS1 using ORCH\TestAdmin, and install Enterprise Single Sign-On.</span></span> <span data-ttu-id="6228c-145">データベース サーバー名 SQL2 を使用して、HIS2 に参加する SSO として ESSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="6228c-145">Configure ESSO as SSO join HIS2, using database server name SQL2.</span></span>  
  
16. <span data-ttu-id="6228c-146">Orch \testadmin を使用して HIS3 にエンタープライズ シングル サインオンの管理ユーティリティをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6228c-146">Install the Enterprise Single Sign-On Admin utility on HIS3 using ORCH\TestAdmin.</span></span>  
  
17. <span data-ttu-id="6228c-147">次のグループには、次のユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="6228c-147">Add the following users to the following groups:</span></span>  
  
    -   <span data-ttu-id="6228c-148">Orch \testappuser を \ssoadmingroup に追加します。</span><span class="sxs-lookup"><span data-stu-id="6228c-148">Add ORCH\TestAppUser to ORCH\SSOAdminGroup</span></span>  
  
    -   <span data-ttu-id="6228c-149">\Testaffusergroup に \affappuser を追加します。</span><span class="sxs-lookup"><span data-stu-id="6228c-149">Add ORCH\AffAppUser to ORCH\TestAffUserGroup</span></span>  
  
18. <span data-ttu-id="6228c-150">His3、SQL Server Enterprise Edition をインストールし、ログイン \affappuser を追加します。</span><span class="sxs-lookup"><span data-stu-id="6228c-150">Install SQL Server Enterprise Edition on HIS3, and add login ORCH\AffAppUser.</span></span>  
  
19. <span data-ttu-id="6228c-151">コマンド プロンプトを開き、HIS1 コンピュータでとを設定する、次のコマンドを使用して委任とプロトコル遷移の制限します。</span><span class="sxs-lookup"><span data-stu-id="6228c-151">On the HIS1 computer, open a command prompt and use the following commands to set constrain delegation and protocol transition:</span></span>  
  
    -   <span data-ttu-id="6228c-152">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**</span><span class="sxs-lookup"><span data-stu-id="6228c-152">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**</span></span>  
  
    -   <span data-ttu-id="6228c-153">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**</span><span class="sxs-lookup"><span data-stu-id="6228c-153">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**</span></span>  
  
20. <span data-ttu-id="6228c-154">**\Ssosvcuser**と**orch \testappuser**プロパティ ページでは、次のオプションを選択して両方のユーザー アカウントに対して適切な委任を設定します。</span><span class="sxs-lookup"><span data-stu-id="6228c-154">On the **ORCH\SSOSvcUser** and **ORCH\TestAppUser** property pages, set the proper delegation for both user accounts by selecting the following options:</span></span>  
  
    -   <span data-ttu-id="6228c-155">**指定されたサービスのみへの委任では、このユーザーを信頼します。**</span><span class="sxs-lookup"><span data-stu-id="6228c-155">**Trust this user for delegation to specified services only**</span></span>  
  
    -   <span data-ttu-id="6228c-156">**任意の認証プロトコルを使用して、**</span><span class="sxs-lookup"><span data-stu-id="6228c-156">**Use any authentication protocol**</span></span>  
  
21. <span data-ttu-id="6228c-157">Orch \testadmin を使用して、HIS1 コンピュータで、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="6228c-157">Using ORCH\TestAdmin on the HIS1 computer, perform the following:</span></span>  
  
    -   <span data-ttu-id="6228c-158">Orch \testappuser を Remote Desktop User グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="6228c-158">Add ORCH\TestAppUser to Remote Desktop User Group</span></span>  
  
    -   <span data-ttu-id="6228c-159">Grant**認証された後の権限を借用**\ssosvcuser する権限</span><span class="sxs-lookup"><span data-stu-id="6228c-159">Grant **Impersonate after authenticated** privilege to ORCH\SSOSvcUser</span></span>  
  
    -   <span data-ttu-id="6228c-160">Grant**認証された後の権限を借用**orch \testappuser を特権</span><span class="sxs-lookup"><span data-stu-id="6228c-160">Grant **Impersonate after authenticated** privilege to ORCH\TestAppUser</span></span>  
  
22. <span data-ttu-id="6228c-161">HIS1 にログオンして、デプロイを確認します。 orch \testappuser を使用すると、次のアプリケーションの構成を実行します。</span><span class="sxs-lookup"><span data-stu-id="6228c-161">Verify your deployment by logging onto HIS1 using ORCH\TestAppUser and running the following application configuration:</span></span>  
  
     <span data-ttu-id="6228c-162">LogonExternalUser テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="6228c-162">Run LogonExternalUser Test.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6228c-163">参照</span><span class="sxs-lookup"><span data-stu-id="6228c-163">See Also</span></span>  
 [<span data-ttu-id="6228c-164">SSO 展開の概要</span><span class="sxs-lookup"><span data-stu-id="6228c-164">SSO Deployment Overview</span></span>](../core/sso-deployment-overview.md)