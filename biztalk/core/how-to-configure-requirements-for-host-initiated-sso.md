---
title: "側開始 SSO のホストの要件を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20b14539edc6b9b1026ca048feb881ce0d8a6d1e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-requirements-for-host-initiated-sso"></a><span data-ttu-id="d0085-102">ホスト側開始 SSO の要件を構成する方法</span><span class="sxs-lookup"><span data-stu-id="d0085-102">How to Configure Requirements for Host Initiated SSO</span></span>
<span data-ttu-id="d0085-103">エンタープライズ SSO とホスト側開始 SSO にはある共通点がありますが、特定のプラットフォームおよび Active Directory の要件はホスト側開始 SSO に対して一意です。</span><span class="sxs-lookup"><span data-stu-id="d0085-103">Although Enterprise SSO and host initiated SSO have certain aspects in common, certain platform and Active Directory requirements are unique to host initiated SSO.</span></span> <span data-ttu-id="d0085-104">このトピックでは、これらの要件について説明し、システムで要件を確認または作成する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="d0085-104">This topic discusses those requirements, and lists the steps to check or create them on your system.</span></span>  
  
-   <span data-ttu-id="d0085-105">ホスト側開始 SSO は、ネイティブの Windows Server 2008 ドメイン環境でのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="d0085-105">Host initiated SSO can be executed only on a native Windows Server 2008 domain environment.</span></span>  
  
-   <span data-ttu-id="d0085-106">ホスト側開始 SSO を実行している SSO サービスのサービス アカウントは、TCB 特権が付与されるように構成する必要があります</span><span class="sxs-lookup"><span data-stu-id="d0085-106">The service account for SSO Service that is performing host initiated SSO must be configured to have TCB privileges.</span></span> <span data-ttu-id="d0085-107">(これは、ドメイン セキュリティ ポリシーのサービス アカウントに対して構成できます)。</span><span class="sxs-lookup"><span data-stu-id="d0085-107">(You can configure this for the service account in the domain security policy.)</span></span>  
  
 <span data-ttu-id="d0085-108">また、ホスト側開始処理にトランザクション インテグレータを使用する場合は、特定の要件が必要です。</span><span class="sxs-lookup"><span data-stu-id="d0085-108">In addition, certain requirements are necessary when using Transaction Integrator for Host Initiated Processing.</span></span> <span data-ttu-id="d0085-109">HIP の TI は、ホスト側開始 SSO を利用して、Windows 以外のユーザーのシングル サインオンを実現します。</span><span class="sxs-lookup"><span data-stu-id="d0085-109">TI for HIP leverages host initiated SSO to achieve Single Sign-On for non-Windows users.</span></span>  
  
 <span data-ttu-id="d0085-110">たとえば、HIP サービスの TI のサービス アカウントは、domainname\hipsvc サービス アカウントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="d0085-110">For example, service account for TI for HIP service runs under a service account domainname\hipsvc.</span></span> <span data-ttu-id="d0085-111">このサービスは、Windows 以外のアカウントに対応する Windows アカウントを使用して Windows 上のリモート リソースまたはローカル リソースにアクセスするアプリケーションをホストできます。</span><span class="sxs-lookup"><span data-stu-id="d0085-111">This service can host applications that want to access remote or local resources on Windows with the Windows account that correspond to the non-Windows account.</span></span>  
  
 <span data-ttu-id="d0085-112">domainname\hipsvc アカウントは、シングル サインオンに使用される関連アプリケーションのアプリケーション管理者グループ アカウントに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0085-112">The domainname\hipsvc account must belong to the Application Administrator group account for the Affiliate Application that is being used for Single Sign-On.</span></span>  
  
 <span data-ttu-id="d0085-113">domainname\hipsvc アカウントには、ホスト側開始シングル サインオンを使用するための制約付き委任の特権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d0085-113">The domainname\hipsvc account must have constrained delegation privileges to use host initiated Single Sign-On.</span></span> <span data-ttu-id="d0085-114">これは、Active Directory のドメイン管理者が構成できます。</span><span class="sxs-lookup"><span data-stu-id="d0085-114">This can be configured by the domain administrator in Active Directory.</span></span> <span data-ttu-id="d0085-115">委任は、SPN を登録したアカウントに対して構成できます。</span><span class="sxs-lookup"><span data-stu-id="d0085-115">Delegation can be configured for accounts that have registered SPNs.</span></span> <span data-ttu-id="d0085-116">制約付き委任が付与されたサービス アカウントは、管理者が指定するコンポーネントにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d0085-116">Constrained delegation allows the service account to access only components that are specified by the administrator.</span></span>  
  
### <a name="to-check-your-domain-function-level"></a><span data-ttu-id="d0085-117">ドメインの機能レベルを確認するには</span><span class="sxs-lookup"><span data-stu-id="d0085-117">To check your domain function level</span></span>  
  
1.  <span data-ttu-id="d0085-118">**Active Directory Domains and Trusts** MMC スナップインで、右側には、ノードをクリックして**Active Directory Domains and Trusts**、クリックして**フォレストの機能レベルを上げる**します。</span><span class="sxs-lookup"><span data-stu-id="d0085-118">In your **Active Directory Domains and Trusts** MMC snap-in, right click the node **Active Directory Domains and Trusts**, and then click **Raise Forest Functional Level**.</span></span>  
  
2.  <span data-ttu-id="d0085-119">機能レベルがあることを確認**Windows Server 2008**です。</span><span class="sxs-lookup"><span data-stu-id="d0085-119">Verify that the functional level is **Windows Server 2008**.</span></span> <span data-ttu-id="d0085-120">機能レベルが異なる場合は、設定を変更する前に Active Directory のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0085-120">If it is not, refer to your Active Directory documentation before you attempt to change the setting.</span></span>  
  
### <a name="to-create-an-spn"></a><span data-ttu-id="d0085-121">SPN を作成するには</span><span class="sxs-lookup"><span data-stu-id="d0085-121">To create an SPN</span></span>  
  
1.  <span data-ttu-id="d0085-122">ダウンロード、 **setspn**次の場所からユーティリティ: [http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178)です。</span><span class="sxs-lookup"><span data-stu-id="d0085-122">Download the **setspn** utility from the following location: [http://go.microsoft.com/fwlink/?LinkId=33178](http://go.microsoft.com/fwlink/?LinkId=33178).</span></span>  
  
2.  <span data-ttu-id="d0085-123">**[スタート]** メニューの **[ファイル名を指定して実行]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d0085-123">On the **Start** menu, click **Run**.</span></span>  
  
3.  <span data-ttu-id="d0085-124">**実行** ダイアログ ボックスで、「 **cmd**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="d0085-124">In the **Run** dialog box, type **cmd**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="d0085-125">コマンド ラインで、エンタープライズ シングル サインオンのインストール ディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="d0085-125">At the command line, go to the Enterprise Single Sign-On installation directory.</span></span> <span data-ttu-id="d0085-126">既定値は\<ドライブ\>: \program files \common files \enterprise シングル サインオンします。</span><span class="sxs-lookup"><span data-stu-id="d0085-126">The default is \<drive\>:\Program Files\Common Files\Enterprise Single Sign-On.</span></span>  
  
5.  <span data-ttu-id="d0085-127">型**setpsn hipsvc\computername.domain.com の domain \hissvc-**</span><span class="sxs-lookup"><span data-stu-id="d0085-127">Type **setpsn -a hipsvc\computername.domain.com domain\hissvc**</span></span>  
  
     <span data-ttu-id="d0085-128">ここで**hipsvc\computername.domain.com**で実行されているコンピューターと、操作を実行するサービスと**domain \hissvc** hipsvc のサービス アカウントは、します。</span><span class="sxs-lookup"><span data-stu-id="d0085-128">where **hipsvc\computername.domain.com** is the service that will perform the operation and the computer it is running on, and **domain\hissvc** is the service account for hipsvc.</span></span>  
  
 <span data-ttu-id="d0085-129">この操作後、Active Directory でこのサービス アカウント (domain\hissvc) 用の制約付き委任を、ネットワーク内の適切なリソースにアクセスするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="d0085-129">After doing this, you can configure constrained delegation in Active Directory for this service account (domain\hissvc) to access the appropriate resource in the network.</span></span>  
  
#### <a name="to-give-tcb-privileges-for-the-sso-service-account"></a><span data-ttu-id="d0085-130">SSO サービス アカウントの TCB 特権を付与するには</span><span class="sxs-lookup"><span data-stu-id="d0085-130">To give TCB privileges for the SSO service account</span></span>  
  
-   <span data-ttu-id="d0085-131">下にある、**ドメイン セキュリティ ポリシーのローカル ポリシー - ユーザー権利の割り当て**、SSO サービス アカウントを追加、**オペレーティング システムの一部として動作する**ポリシー。</span><span class="sxs-lookup"><span data-stu-id="d0085-131">Under your **Domain Security Policy - Local Policies - User Rights Assignment**, add the SSO Service account to the **Act as part of operating system** policy.</span></span>  
  
     <span data-ttu-id="d0085-132">Kerberos プロトコル遷移および制約付き委任の詳細についてを参照してください[http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484)です。</span><span class="sxs-lookup"><span data-stu-id="d0085-132">For more information about Kerberos Protocol Transition and Constrained Delegation, go to [http://go.microsoft.com/fwlink/?LinkId=195484](http://go.microsoft.com/fwlink/?LinkId=195484).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0085-133">参照</span><span class="sxs-lookup"><span data-stu-id="d0085-133">See Also</span></span>  
 [<span data-ttu-id="d0085-134">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="d0085-134">Host Initiated SSO</span></span>](../core/host-initiated-sso.md)