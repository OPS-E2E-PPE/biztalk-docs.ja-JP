---
title: "展開プロセス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, deploying
- deploying, SSO
- LogonExternalUser test [SSO]
- security, SSO
- SSO, LogonExternalUser test
- SSO, security
ms.assetid: 7dd4c022-c70b-467a-bf94-dc4ac6029f81
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21be32ec58c90c1fb95134a002bee82ef5d78fa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deployment-process"></a><span data-ttu-id="a6fb9-102">展開プロセス</span><span class="sxs-lookup"><span data-stu-id="a6fb9-102">Deployment Process</span></span>
<span data-ttu-id="a6fb9-103">次の手順は、エンタープライズ シングル サインオンの、セキュリティで保護された展開の概要です。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-103">The following steps give a high-level overview of secure deployment of Enterprise Single Sign-On.</span></span> <span data-ttu-id="a6fb9-104">SQL Server で実行する操作の詳細な手順については、SQL Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-104">For detailed procedures on the actions to take in SQL Server, see your SQL Server documentation.</span></span>  
  
1.  <span data-ttu-id="a6fb9-105">SQL Server ドメイン コントローラで、新しい信頼ウィザードを実行して、次のプロパティを指定した信頼関係を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-105">On the SQL Server domain controller, use the New Trust Wizard to create a trust with the following properties:</span></span>  
  
    -   <span data-ttu-id="a6fb9-106">**[名前]:** ORCH.com</span><span class="sxs-lookup"><span data-stu-id="a6fb9-106">**Name:** ORCH.com</span></span>  
  
    -   <span data-ttu-id="a6fb9-107">**方向:**双方向</span><span class="sxs-lookup"><span data-stu-id="a6fb9-107">**Direction:** Two-way</span></span>  
  
    -   <span data-ttu-id="a6fb9-108">**辺:**このドメインのみ</span><span class="sxs-lookup"><span data-stu-id="a6fb9-108">**Sides:** This domain only</span></span>  
  
    -   <span data-ttu-id="a6fb9-109">**出力方向の信頼認証レベル--ローカル ドメイン:**認証の選択</span><span class="sxs-lookup"><span data-stu-id="a6fb9-109">**Outgoing Trust Authentication Level - Local Domain:** Selective authentication</span></span>  
  
    -   <span data-ttu-id="a6fb9-110">**パスワード:**のパスワードを選択</span><span class="sxs-lookup"><span data-stu-id="a6fb9-110">**Password:** Choose a password</span></span>  
  
    -   <span data-ttu-id="a6fb9-111">**出力方向の信頼の確認:** [はい]</span><span class="sxs-lookup"><span data-stu-id="a6fb9-111">**Confirm Outgoing Trust:** Yes</span></span>  
  
    -   <span data-ttu-id="a6fb9-112">**入力方向の信頼の確認:**なし</span><span class="sxs-lookup"><span data-stu-id="a6fb9-112">**Confirm Incoming Trust:** No</span></span>  
  
2.  <span data-ttu-id="a6fb9-113">ORCH.com ドメイン コントローラで新しい信頼ウィザードを実行し、次のプロパティを指定した信頼関係を作成します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-113">On the ORCH.com domain controller, use the New Trust Wizard to create a trust with the following properties:</span></span>  
  
    -   <span data-ttu-id="a6fb9-114">**[名前]:** SQL.com</span><span class="sxs-lookup"><span data-stu-id="a6fb9-114">**Name:** SQL.com</span></span>  
  
    -   <span data-ttu-id="a6fb9-115">**方向:**双方向</span><span class="sxs-lookup"><span data-stu-id="a6fb9-115">**Direction:** Two-way</span></span>  
  
    -   <span data-ttu-id="a6fb9-116">**辺:**このドメインのみ</span><span class="sxs-lookup"><span data-stu-id="a6fb9-116">**Sides:** This domain only</span></span>  
  
    -   <span data-ttu-id="a6fb9-117">**出力方向の信頼認証レベル--ローカル ドメイン:**認証の選択</span><span class="sxs-lookup"><span data-stu-id="a6fb9-117">**Outgoing Trust Authentication Level - Local Domain:** Selective authentication</span></span>  
  
    -   <span data-ttu-id="a6fb9-118">**パスワード:** ORCH.com のパスワードと同じである必要があります</span><span class="sxs-lookup"><span data-stu-id="a6fb9-118">**Password:** Must be the same as password for ORCH.com</span></span>  
  
    -   <span data-ttu-id="a6fb9-119">**出力方向の信頼の確認:** [はい]</span><span class="sxs-lookup"><span data-stu-id="a6fb9-119">**Confirm Outgoing Trust:** Yes</span></span>  
  
    -   <span data-ttu-id="a6fb9-120">**入力方向の信頼の確認:**なし</span><span class="sxs-lookup"><span data-stu-id="a6fb9-120">**Confirm Incoming Trust:** No</span></span>  
  
3.  <span data-ttu-id="a6fb9-121">ORCH.com ドメイン コントローラで、SQL.com からの着信に対してドメイン レベルの信頼関係を設定します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-121">On the ORCH.com domain controller, set the domain wide trust for Incoming from SQL.COM.</span></span>  
  
4.  <span data-ttu-id="a6fb9-122">SQL.com ドメイン コントローラで、ORCH.com からの送信に対してドメイン レベルの信頼関係を設定します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-122">On the SQL.com domain controller, set the domain wide trust for Outgoing from ORCH.COM.</span></span>  
  
5.  <span data-ttu-id="a6fb9-123">ORCH.com ドメイン コントローラーで、ドメインの機能レベルを Windows Server 2008 SP2 または Windows Server 2008 R2 に上げます。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-123">On the ORCH.com domain controller, raise the domain functional level to Windows Server 2008 SP2 or Windows Server 2008 R2.</span></span>  
  
6.  <span data-ttu-id="a6fb9-124">ORCH.com ドメインに次の新しいユーザーを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-124">In the ORCH domain, create the following new users:</span></span>  
  
    -   <span data-ttu-id="a6fb9-125">ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="a6fb9-125">ORCH\SSOSvcUser</span></span>  
  
    -   <span data-ttu-id="a6fb9-126">ORCH\TestAppUser</span><span class="sxs-lookup"><span data-stu-id="a6fb9-126">ORCH\TestAppUser</span></span>  
  
    -   <span data-ttu-id="a6fb9-127">ORCH\AffAppUser</span><span class="sxs-lookup"><span data-stu-id="a6fb9-127">ORCH\AffAppUser</span></span>  
  
7.  <span data-ttu-id="a6fb9-128">追加**オペレーティング システムの一部として動作する**SSOSvcUser と TestAppUser にします。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-128">Add **Act as part of the operating system** to SSOSvcUser and TestAppUser.</span></span>  
  
8.  <span data-ttu-id="a6fb9-129">追加**認証を許可されている**orch \testadmin する権限です。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-129">Add **Allowed to Authenticate** privilege to ORCH\TestAdmin.</span></span>  
  
9. <span data-ttu-id="a6fb9-130">ORCH\SSOSvcUser ユーザーを SQL.com ドメインの SQL2 コンピューターに追加します </span><span class="sxs-lookup"><span data-stu-id="a6fb9-130">Add ORCH\SSOSvcUser to SQL2 in the SQL domain.</span></span> <span data-ttu-id="a6fb9-131">(この手順では、Active Directory MMC の詳細ビューを使用する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-131">(This step requires using Advanced View in Active Directory MMC.)</span></span>  
  
10. <span data-ttu-id="a6fb9-132">SQL2 コンピュータに、次の 2 つの新しいログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-132">On the SQL2 computer, create the following two new logins:</span></span>  
  
    -   <span data-ttu-id="a6fb9-133">ORCH\TestAdmin</span><span class="sxs-lookup"><span data-stu-id="a6fb9-133">ORCH\TestAdmin</span></span>  
  
    -   <span data-ttu-id="a6fb9-134">ORCH\SSOSvcUser</span><span class="sxs-lookup"><span data-stu-id="a6fb9-134">ORCH\SSOSvcUser</span></span>  
  
11. <span data-ttu-id="a6fb9-135">SQL2 ドメインに、次の 2 つのドメイン グローバル グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-135">On the SQL2 domain, create two domain global groups:</span></span>  
  
    -   <span data-ttu-id="a6fb9-136">ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="a6fb9-136">ORCH\SSOAdminGroup</span></span>  
  
    -   <span data-ttu-id="a6fb9-137">ORCH\SSOAffAdminGroup</span><span class="sxs-lookup"><span data-stu-id="a6fb9-137">ORCH\SSOAffAdminGroup</span></span>  
  
12. <span data-ttu-id="a6fb9-138">追加**認証を許可されている**\ssoadmingroup グループに権限です。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-138">Add **Allowed to Authenticate** privilege to the ORCH\SSOAdminGroup group.</span></span>  
  
13. <span data-ttu-id="a6fb9-139">SQL2 データベースに、次の新しいログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-139">On the SQL2 database, create the following new login:</span></span>  
  
    -   <span data-ttu-id="a6fb9-140">ORCH\SSOAdminGroup</span><span class="sxs-lookup"><span data-stu-id="a6fb9-140">ORCH\SSOAdminGroup</span></span>  
  
14. <span data-ttu-id="a6fb9-141">次の手順に従って、マスタ シークレット サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-141">Install the Master Secret Server as follows:</span></span>  
  
    -   <span data-ttu-id="a6fb9-142">ORCH\TestAdmin を使用して NTS5 にログオンします。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-142">Log on to NTS5 using ORCH\TestAdmin.</span></span>  
  
    -   <span data-ttu-id="a6fb9-143">SQL2 コンピュータをマスタ シークレット サーバーとして使用して、ESSO をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-143">Install ESSO, using SQL2 as the Master Secret Server.</span></span>  
  
15. <span data-ttu-id="a6fb9-144">ORCH\TestAdmin を使用して HIS1 にログオンし、エンタープライズ シングル サインオンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-144">Log onto HIS1 using ORCH\TestAdmin, and install Enterprise Single Sign-On.</span></span> <span data-ttu-id="a6fb9-145">データベース サーバー名 SQL2 を使用して、ESSO を HIS2 に参加する SSO として構成します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-145">Configure ESSO as SSO join HIS2, using database server name SQL2.</span></span>  
  
16. <span data-ttu-id="a6fb9-146">ORCH\TestAdmin を使用して HIS3 にエンタープライズ シングル サインオンの管理ユーティリティをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-146">Install the Enterprise Single Sign-On Admin utility on HIS3 using ORCH\TestAdmin.</span></span>  
  
17. <span data-ttu-id="a6fb9-147">次のようにユーザーをグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-147">Add the following users to the following groups:</span></span>  
  
    -   <span data-ttu-id="a6fb9-148">ORCH\TestAppUser ユーザーを ORCH\SSOAdminGroup グループに追加します</span><span class="sxs-lookup"><span data-stu-id="a6fb9-148">Add ORCH\TestAppUser to ORCH\SSOAdminGroup</span></span>  
  
    -   <span data-ttu-id="a6fb9-149">ORCH\AffAppUser ユーザーを ORCH\TestAffUserGroup グループに追加します</span><span class="sxs-lookup"><span data-stu-id="a6fb9-149">Add ORCH\AffAppUser to ORCH\TestAffUserGroup</span></span>  
  
18. <span data-ttu-id="a6fb9-150">HIS3 に SQL Server Enterprise Edition をインストールし、ログイン ORCH\AffAppUser を追加します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-150">Install SQL Server Enterprise Edition on HIS3, and add login ORCH\AffAppUser.</span></span>  
  
19. <span data-ttu-id="a6fb9-151">HIS1 コンピュータでコマンド プロンプトを開き、次のコマンドを使用して制約付き委任とプロトコル遷移を設定します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-151">On the HIS1 computer, open a command prompt and use the following commands to set constrain delegation and protocol transition:</span></span>  
  
    -   <span data-ttu-id="a6fb9-152">**setspn-a MSSQLSvc/HIS3.ORCH.com:1433 \ssosvcuser**</span><span class="sxs-lookup"><span data-stu-id="a6fb9-152">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\SSOSvcUser**</span></span>  
  
    -   <span data-ttu-id="a6fb9-153">**setspn-a MSSQLSvc/HIS3.ORCH.com:1433 orch \testappuser**</span><span class="sxs-lookup"><span data-stu-id="a6fb9-153">**setspn -A MSSQLSvc/HIS3.ORCH.com:1433 ORCH\TestAppUser**</span></span>  
  
20. <span data-ttu-id="a6fb9-154">**\Ssosvcuser**と**orch \testappuser**プロパティ ページは、次のオプションを選択して両方のユーザー アカウントに対して適切な委任を設定します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-154">On the **ORCH\SSOSvcUser** and **ORCH\TestAppUser** property pages, set the proper delegation for both user accounts by selecting the following options:</span></span>  
  
    -   <span data-ttu-id="a6fb9-155">**このユーザーに指定されたサービスのみ委任に対して信頼します。**</span><span class="sxs-lookup"><span data-stu-id="a6fb9-155">**Trust this user for delegation to specified services only**</span></span>  
  
    -   <span data-ttu-id="a6fb9-156">**任意の認証プロトコルを使用します。**</span><span class="sxs-lookup"><span data-stu-id="a6fb9-156">**Use any authentication protocol**</span></span>  
  
21. <span data-ttu-id="a6fb9-157">ORCH\TestAdmin を使用して、HIS1 コンピュータで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-157">Using ORCH\TestAdmin on the HIS1 computer, perform the following:</span></span>  
  
    -   <span data-ttu-id="a6fb9-158">ORCH\TestAppUser を Remote Desktop User グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-158">Add ORCH\TestAppUser to Remote Desktop User Group</span></span>  
  
    -   <span data-ttu-id="a6fb9-159">Grant**が認証された後の権限を借用**\ssosvcuser する権限</span><span class="sxs-lookup"><span data-stu-id="a6fb9-159">Grant **Impersonate after authenticated** privilege to ORCH\SSOSvcUser</span></span>  
  
    -   <span data-ttu-id="a6fb9-160">Grant**が認証された後の権限を借用**orch \testappuser する権限</span><span class="sxs-lookup"><span data-stu-id="a6fb9-160">Grant **Impersonate after authenticated** privilege to ORCH\TestAppUser</span></span>  
  
22. <span data-ttu-id="a6fb9-161">ORCH\TestAppUser を使用して HIS1 にログオンし、次のアプリケーション構成を実行して、展開の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-161">Verify your deployment by logging onto HIS1 using ORCH\TestAppUser and running the following application configuration:</span></span>  
  
     <span data-ttu-id="a6fb9-162">LogonExternalUser テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="a6fb9-162">Run LogonExternalUser Test.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a6fb9-163">参照</span><span class="sxs-lookup"><span data-stu-id="a6fb9-163">See Also</span></span>  
 [<span data-ttu-id="a6fb9-164">SSO 展開の概要</span><span class="sxs-lookup"><span data-stu-id="a6fb9-164">SSO Deployment Overview</span></span>](../core/sso-deployment-overview.md)