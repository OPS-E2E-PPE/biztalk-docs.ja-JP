---
title: 側開始 SSO のホストの要件を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service accounts, granting privileges [SSO]
- host initiated SSO, configuring
- domain function level [SSO]
- host initiated SSO, Transaction Integrator (TI)
- SPN [SSO]
- managing [SSO], granting TCB privileges
- Transaction Integrator (TI)
- host initiated SSO, SPN
- host initiated SSO, TCB privileges
- configuring, host initiated SSO
- creating, SPNs [SSO]
- TCB privileges [SSO]
- managing [SSO], host initiated
- host initiated SSO, domain function level
- service accounts, SSO
- SSO, host initiated
- managing [SSO], creating SPNs
- SSO, service accounts
ms.assetid: 91d77c9f-bab2-4f6e-8bce-e31c59cebb20
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f3319c0d8157ebe0c71c36a2494b3bda641181c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341220"
---
# <a name="how-to-configure-requirements-for-host-initiated-sso"></a><span data-ttu-id="3ef84-102">側開始 SSO のホストの要件を構成する方法</span><span class="sxs-lookup"><span data-stu-id="3ef84-102">How to Configure Requirements for Host Initiated SSO</span></span>
<span data-ttu-id="3ef84-103">エンタープライズ SSO とホスト側開始 SSO 共通の特定の側面がありますが、特定のプラットフォームおよび Active Directory の要件はホスト側開始 SSO に固有です。</span><span class="sxs-lookup"><span data-stu-id="3ef84-103">Although Enterprise SSO and host initiated SSO have certain aspects in common, certain platform and Active Directory requirements are unique to host initiated SSO.</span></span> <span data-ttu-id="3ef84-104">このトピックでは、これらの要件について説明しを確認するか、システムを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3ef84-104">This topic discusses those requirements, and lists the steps to check or create them on your system.</span></span>  
  
- <span data-ttu-id="3ef84-105">ホスト側開始 SSO は、ネイティブの Windows Server 2008 ドメイン環境でのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="3ef84-105">Host initiated SSO can be executed only on a native Windows Server 2008 domain environment.</span></span>  
  
- <span data-ttu-id="3ef84-106">ホストが実行している SSO サービスのサービス アカウント側開始 SSO は、TCB 特権を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ef84-106">The service account for SSO Service that is performing host initiated SSO must be configured to have TCB privileges.</span></span> <span data-ttu-id="3ef84-107">(することができますこれを構成、ドメイン セキュリティ ポリシー内のサービス アカウント。)</span><span class="sxs-lookup"><span data-stu-id="3ef84-107">(You can configure this for the service account in the domain security policy.)</span></span>  
  
  <span data-ttu-id="3ef84-108">さらに、ホスト側開始処理をトランザクション インテグレーターを使用する場合は、特定の要件は必要です。</span><span class="sxs-lookup"><span data-stu-id="3ef84-108">In addition, certain requirements are necessary when using Transaction Integrator for Host Initiated Processing.</span></span> <span data-ttu-id="3ef84-109">TI ホストが Windows 以外のユーザーのシングル サインオンを実現するために SSO を開始の HIP を活用します。</span><span class="sxs-lookup"><span data-stu-id="3ef84-109">TI for HIP leverages host initiated SSO to achieve Single Sign-On for non-Windows users.</span></span>  
  
  <span data-ttu-id="3ef84-110">たとえば、HIP サービスの TI のサービス アカウントは、domainname \hipsvc サービス アカウントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3ef84-110">For example, service account for TI for HIP service runs under a service account domainname\hipsvc.</span></span> <span data-ttu-id="3ef84-111">このサービスは、リソースにアクセスするリモートまたはローカル Windows で Windows アカウントを使用して、Windows 以外のアカウントに対応する必要があるアプリケーションをホストできます。</span><span class="sxs-lookup"><span data-stu-id="3ef84-111">This service can host applications that want to access remote or local resources on Windows with the Windows account that correspond to the non-Windows account.</span></span>  
  
  <span data-ttu-id="3ef84-112">Domainname \hipsvc アカウントは、シングル サインオン用に使用されている関連アプリケーションのアプリケーション管理者グループのアカウントに属する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ef84-112">The domainname\hipsvc account must belong to the Application Administrator group account for the Affiliate Application that is being used for Single Sign-On.</span></span>  
  
  <span data-ttu-id="3ef84-113">Domainname \hipsvc アカウントに委任を制限する必要がありますが、シングル サインオンが開始したホストを使用する特権。</span><span class="sxs-lookup"><span data-stu-id="3ef84-113">The domainname\hipsvc account must have constrained delegation privileges to use host initiated Single Sign-On.</span></span> <span data-ttu-id="3ef84-114">これは、Active Directory でドメイン管理者によって構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ef84-114">This can be configured by the domain administrator in Active Directory.</span></span> <span data-ttu-id="3ef84-115">Spn を登録したアカウントの委任を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ef84-115">Delegation can be configured for accounts that have registered SPNs.</span></span> <span data-ttu-id="3ef84-116">制約付き委任は、管理者が指定されているコンポーネントのみにアクセスするサービス アカウントを許可します。</span><span class="sxs-lookup"><span data-stu-id="3ef84-116">Constrained delegation allows the service account to access only components that are specified by the administrator.</span></span>  
  
### <a name="to-check-your-domain-function-level"></a><span data-ttu-id="3ef84-117">ドメインの機能レベルを確認するには</span><span class="sxs-lookup"><span data-stu-id="3ef84-117">To check your domain function level</span></span>  
  
1.  <span data-ttu-id="3ef84-118">**Active Directory Domains and Trusts** MMC スナップインで、適切なノードをクリックします。 **Active Directory Domains and Trusts**、 をクリックし、**フォレスト機能レベルを上げる**します。</span><span class="sxs-lookup"><span data-stu-id="3ef84-118">In your **Active Directory Domains and Trusts** MMC snap-in, right click the node **Active Directory Domains and Trusts**, and then click **Raise Forest Functional Level**.</span></span>  
  
2.  <span data-ttu-id="3ef84-119">機能レベルがあることを確認**Windows Server 2008**します。</span><span class="sxs-lookup"><span data-stu-id="3ef84-119">Verify that the functional level is **Windows Server 2008**.</span></span> <span data-ttu-id="3ef84-120">そうでない場合は、設定を変更しようとする前に、Active Directory のドキュメントを参照します。</span><span class="sxs-lookup"><span data-stu-id="3ef84-120">If it is not, refer to your Active Directory documentation before you attempt to change the setting.</span></span>  
  
### <a name="to-create-an-spn"></a><span data-ttu-id="3ef84-121">SPN を作成するには</span><span class="sxs-lookup"><span data-stu-id="3ef84-121">To create an SPN</span></span>  
  
1. <span data-ttu-id="3ef84-122">ダウンロード、 **setspn**次の場所からユーティリティ: [ http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178)します。</span><span class="sxs-lookup"><span data-stu-id="3ef84-122">Download the **setspn** utility from the following location: [http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178).</span></span>  
  
2. <span data-ttu-id="3ef84-123">**[スタート]** メニューの **[ファイル名を指定して実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ef84-123">On the **Start** menu, click **Run**.</span></span>  
  
3. <span data-ttu-id="3ef84-124">**実行**ダイアログ ボックスに「 **cmd**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3ef84-124">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
4. <span data-ttu-id="3ef84-125">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="3ef84-125">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="3ef84-126">既定値は\<ドライブ\>: \Program Files\Common \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="3ef84-126">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
5. <span data-ttu-id="3ef84-127">型**setpsn hipsvc\computername.domain.com の domain \hissvc-**</span><span class="sxs-lookup"><span data-stu-id="3ef84-127">Type **setpsn -a hipsvc\computername.domain.com domain\hissvc**</span></span>  
  
    <span data-ttu-id="3ef84-128">場所**hipsvc\computername.domain.com**で実行されているコンピューターと、操作を実行するサービスと**domain \hissvc** hipsvc のサービス アカウントします。</span><span class="sxs-lookup"><span data-stu-id="3ef84-128">where **hipsvc\computername.domain.com** is the service that will perform the operation and the computer it is running on, and **domain\hissvc** is the service account for hipsvc.</span></span>  
  
   <span data-ttu-id="3ef84-129">これを行うには、ネットワーク内の適切なリソースにアクセスするこのサービス アカウント (domain \hissvc) 用の Active Directory で制約付き委任を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3ef84-129">After doing this, you can configure constrained delegation in Active Directory for this service account (domain\hissvc) to access the appropriate resource in the network.</span></span>  
  
#### <a name="to-give-tcb-privileges-for-the-sso-service-account"></a><span data-ttu-id="3ef84-130">SSO サービス アカウントの TCB 特権を付与するには</span><span class="sxs-lookup"><span data-stu-id="3ef84-130">To give TCB privileges for the SSO service account</span></span>  
  
-   <span data-ttu-id="3ef84-131">で、**ドメイン セキュリティ ポリシー - ローカル ポリシー - ユーザー権利の割り当て**、SSO サービス アカウントを追加、**オペレーティング システムの一部として機能**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="3ef84-131">Under your **Domain Security Policy - Local Policies - User Rights Assignment**, add the SSO Service account to the **Act as part of operating system** policy.</span></span>  
  
     <span data-ttu-id="3ef84-132">Kerberos プロトコル遷移および制約付き委任の詳細についてを参照してください[ http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484)します。</span><span class="sxs-lookup"><span data-stu-id="3ef84-132">For more information about Kerberos Protocol Transition and Constrained Delegation, go to [http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef84-133">参照</span><span class="sxs-lookup"><span data-stu-id="3ef84-133">See Also</span></span>  
 [<span data-ttu-id="3ef84-134">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="3ef84-134">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)