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
# <a name="how-to-update-the-sso-database"></a><span data-ttu-id="3e661-102">SSO データベースを更新する方法</span><span class="sxs-lookup"><span data-stu-id="3e661-102">How to Update the SSO Database</span></span>
<span data-ttu-id="3e661-103">MMC スナップインまたはコマンドラインを使用して、データベース、チケットのタイムアウト、および資格情報キャッシュ タイムアウト、監査などのアカウント名をマスター シークレット サーバー id、SSO データベースのグローバル情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="3e661-103">You can change the global information in the SSO database, such as the master secret server identification, the account names, auditing in the database, ticket timeout, and credential cache timeout, by using either the MMC Snap-In or the command line.</span></span>  
  
## <a name="changing-timeouts-for-the-sso-system"></a><span data-ttu-id="3e661-104">SSO システムのタイムアウトを変更します。</span><span class="sxs-lookup"><span data-stu-id="3e661-104">Changing timeouts for the SSO System</span></span>  
 <span data-ttu-id="3e661-105">エンタープライズ シングル サインオン (SSO) システム レベルの 2 つのタイムアウトを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3e661-105">You can modify two timeouts at the Enterprise Single Sign-On (SSO) system level:</span></span>  
  
 <span data-ttu-id="3e661-106">**チケットのタイムアウト。**</span><span class="sxs-lookup"><span data-stu-id="3e661-106">**Ticket timeout.**</span></span> <span data-ttu-id="3e661-107">このプロパティは、チケットの SSO の問題の有効期間の長さを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e661-107">This property specifies the length of time for which a ticket SSO issues is valid.</span></span> <span data-ttu-id="3e661-108">ほとんどの企業での SSO を使用するシナリオを満たすために既定のチケットのタイムアウトは 2 分です。</span><span class="sxs-lookup"><span data-stu-id="3e661-108">To satisfy most of the scenarios in an enterprise that use SSO, the default ticket timeout is 2 minutes.</span></span> <span data-ttu-id="3e661-109">SSO 管理者は、アプリケーションの要件に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="3e661-109">The SSO administrator can change this based on the application requirements.</span></span>  
  
 <span data-ttu-id="3e661-110">**資格情報キャッシュ タイムアウト。**</span><span class="sxs-lookup"><span data-stu-id="3e661-110">**Credential Cache timeout.**</span></span> <span data-ttu-id="3e661-111">このプロパティは、すべての SSO サーバーの資格情報キャッシュのタイムアウトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e661-111">This property specifies the credential cache timeout for all SSO Servers.</span></span> <span data-ttu-id="3e661-112">SSO サーバーを最初に検索した後、資格情報をキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="3e661-112">SSO Servers cache the credentials after the first lookup.</span></span> <span data-ttu-id="3e661-113">既定では、資格情報キャッシュ タイムアウトは 60 分です。</span><span class="sxs-lookup"><span data-stu-id="3e661-113">By default, the credential cache timeout is 60 minutes.</span></span> <span data-ttu-id="3e661-114">SSO 管理者は、セキュリティ要件に基づいて適切な値にこれを変更できます。</span><span class="sxs-lookup"><span data-stu-id="3e661-114">The SSO administrator can change this to a suitable value based on the security requirements.</span></span>  
  
 <span data-ttu-id="3e661-115">これらのタイムアウトの両方を変更するには、SSO データベースを更新することで。</span><span class="sxs-lookup"><span data-stu-id="3e661-115">You change both of these timeouts by updating the SSO database.</span></span>  
  
 <span data-ttu-id="3e661-116">SSO データベースを更新するためのサンプル XML ファイルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3e661-116">A sample XML file for updating the SSO database is:</span></span>  
  
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
  
#### <a name="to-change-timeouts-using-the-mmc-snap-in"></a><span data-ttu-id="3e661-117">MMC スナップインを使用してタイムアウトを変更するには</span><span class="sxs-lookup"><span data-stu-id="3e661-117">To change timeouts using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="3e661-118">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="3e661-118">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="3e661-119">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="3e661-119">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="3e661-120">右クリックして**システム**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="3e661-120">Right-click **System**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="3e661-121">**システム プロパティ**ダイアログ ボックスで、をクリックして、**全般** タブ。</span><span class="sxs-lookup"><span data-stu-id="3e661-121">On the **System Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="3e661-122">適切な設定を入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3e661-122">Enter the appropriate settings, and click **OK**.</span></span>  
  
#### <a name="to-update-the-sso-database-using-the-mmc-snap-in"></a><span data-ttu-id="3e661-123">MMC スナップインを使用して SSO データベースを更新するには</span><span class="sxs-lookup"><span data-stu-id="3e661-123">To update the SSO database using the MMC Snap-In</span></span>  
  
1.  <span data-ttu-id="3e661-124">**開始** メニューのをクリックして**すべてのプログラム**、 をクリックして**Microsoft エンタープライズ シングル サインオン**、 をクリックし、 **SSO 管理**。</span><span class="sxs-lookup"><span data-stu-id="3e661-124">On the **Start** menu, click **All Programs**, click **Microsoft Enterprise Single Sign-On**, and then click **SSO Administration**.</span></span>  
  
2.  <span data-ttu-id="3e661-125">ENTSSO MMC スナップインの [スコープ] ウィンドウで、**エンタープライズ シングル サインオン**ノード。</span><span class="sxs-lookup"><span data-stu-id="3e661-125">In the scope pane of the ENTSSO MMC Snap-In, expand the **Enterprise Single Sign-On** node.</span></span>  
  
3.  <span data-ttu-id="3e661-126">右クリックして**システム**、 をクリックし、**データベースのアップグレード**します。</span><span class="sxs-lookup"><span data-stu-id="3e661-126">Right-click **System**, and then click **Upgrade Database**.</span></span>  
  
#### <a name="to-update-the-sso-database-using-the-command-line"></a><span data-ttu-id="3e661-127">コマンドラインを使用して SSO データベースを更新するには</span><span class="sxs-lookup"><span data-stu-id="3e661-127">To update the SSO database using the command line</span></span>  
  
1.  <span data-ttu-id="3e661-128">クリックして**開始**、 をクリックして**実行**、し、入力**cmd**します。</span><span class="sxs-lookup"><span data-stu-id="3e661-128">Click **Start**, click **Run**, and then type **cmd**.</span></span>  
  
2.  <span data-ttu-id="3e661-129">コマンド ライン プロンプトで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e661-129">At the command line prompt, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="3e661-130">既定のインストール ディレクトリは*\<ドライブ\>*: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="3e661-130">The default installation directory is *\<drive\>*:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
3.  <span data-ttu-id="3e661-131">型**ssomanage – updatedb\<更新ファイル\>** ここで、 **\<更新ファイル\>** はパスとファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="3e661-131">Type **ssomanage –updatedb \<update file\>**, where **\<update file\>** is the path and name of the file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e661-132">ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="3e661-132">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e661-133">参照</span><span class="sxs-lookup"><span data-stu-id="3e661-133">See Also</span></span>  
 <span data-ttu-id="3e661-134">[SSO チケットを構成する方法](../core/how-to-configure-the-sso-tickets.md) </span><span class="sxs-lookup"><span data-stu-id="3e661-134">[How to Configure the SSO Tickets](../core/how-to-configure-the-sso-tickets.md) </span></span>  
 [<span data-ttu-id="3e661-135">SSO の使用</span><span class="sxs-lookup"><span data-stu-id="3e661-135">Using SSO</span></span>](../core/using-sso.md)