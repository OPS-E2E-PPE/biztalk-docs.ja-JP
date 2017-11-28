---
title: "SSO を理解する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- Windows Integrated Single Sign-On
- Extranet Single Sign-On (Web SSO)
- Server-Based Intranet Single Sign-On
ms.assetid: 03f78a7b-4880-408f-9733-d07e19775d21
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 736fee720f2abf0dd051b1f754dd0fd6b8c42ab6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="understanding-sso"></a><span data-ttu-id="7ec78-102">SSO について</span><span class="sxs-lookup"><span data-stu-id="7ec78-102">Understanding SSO</span></span>
<span data-ttu-id="7ec78-103">エンタープライズ シングル サインオンを理解するには、現在使用可能な 3 種類のシングル サインオン サービス (Windows 統合、エクストラネット、およびイントラネット) を知っておくと役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="7ec78-103">To understand Enterprise Single Sign-On, it is useful to look at the three types of Single Sign-On services available today: Windows integrated, extranet, and intranet.</span></span> <span data-ttu-id="7ec78-104">これら 3 種類のサービスについて以下で説明します。説明では、エンタープライズ シングル サインオンを 3 つのカテゴリに分けています。</span><span class="sxs-lookup"><span data-stu-id="7ec78-104">These are described below, with Enterprise Single Sign-On falling into the third category.</span></span>  
  
## <a name="windows-integrated-single-sign-on"></a><span data-ttu-id="7ec78-105">Windows 統合シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7ec78-105">Windows Integrated Single Sign-On</span></span>  
 <span data-ttu-id="7ec78-106">共通の認証メカニズムを使用するネットワーク内の複数のアプリケーションに接続できます。</span><span class="sxs-lookup"><span data-stu-id="7ec78-106">These services enable you to connect to multiple applications within your network that use a common authentication mechanism.</span></span> <span data-ttu-id="7ec78-107">この種のサービスでは、ネットワークへのログイン後に資格情報を要求して確認します。その後、ユーザーの資格情報を使用し、実行できる操作をユーザー権利に基づいて特定します。</span><span class="sxs-lookup"><span data-stu-id="7ec78-107">These services request and verify your credentials after you log into the network, and use your credentials to determine the actions that you can perform based on your user rights.</span></span> <span data-ttu-id="7ec78-108">たとえば、アプリケーションが Kerberos を使用して統合されている場合、ユーザーの資格情報がシステムによって認証された後、ユーザーは Kerberos で統合されているネットワーク内のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7ec78-108">For example, if applications integrate using Kerberos, after the system authenticates your user credentials you can access any resource in the network that is integrated with Kerberos.</span></span>  
  
## <a name="extranet-single-sign-on-web-sso"></a><span data-ttu-id="7ec78-109">エクストラネット シングル サインオン (Web SSO)</span><span class="sxs-lookup"><span data-stu-id="7ec78-109">Extranet Single Sign-On (Web SSO)</span></span>  
 <span data-ttu-id="7ec78-110">単一セットのユーザーの資格情報を使用して、インターネット経由でリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7ec78-110">These services enable you to access resources over the Internet by using a single set of user credentials.</span></span> <span data-ttu-id="7ec78-111">ユーザーは異なる組織に属している個別の Web サイトへのログオン時に一連の資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="7ec78-111">The user provides a set of credentials to log on to different Web sites that belong to different organizations.</span></span> <span data-ttu-id="7ec78-112">この種類のシングル サインオンの例には、顧客ベースのアプリケーション用の Windows Live ID があります。</span><span class="sxs-lookup"><span data-stu-id="7ec78-112">An example of this type of Single Sign-On is Windows Live ID for consumer based applications.</span></span> <span data-ttu-id="7ec78-113">連合シナリオの場合、Microsoft Active Directory フェデレーション サービスを使用すると、Web SSO が有効になります。</span><span class="sxs-lookup"><span data-stu-id="7ec78-113">For federated scenarios, Microsoft Active Directory Federation Services enables Web SSO.</span></span>  
  
## <a name="server-based-intranet-single-sign-on"></a><span data-ttu-id="7ec78-114">サーバー ベースのイントラネット シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7ec78-114">Server-Based Intranet Single Sign-On</span></span>  
 <span data-ttu-id="7ec78-115">複数の異種アプリケーションとシステムを、エンタープライズ環境内で統合できます。</span><span class="sxs-lookup"><span data-stu-id="7ec78-115">These services enable you to integrate multiple heterogeneous applications and systems within the enterprise environment.</span></span> <span data-ttu-id="7ec78-116">これらの異種アプリケーションとシステムでは、共通の認証を使用しない場合があり、</span><span class="sxs-lookup"><span data-stu-id="7ec78-116">These applications and systems may not use common authentication.</span></span> <span data-ttu-id="7ec78-117">各アプリケーションには、それぞれに固有のユーザー ディレクトリ ストアがあります。</span><span class="sxs-lookup"><span data-stu-id="7ec78-117">Each application has its own user directory store.</span></span> <span data-ttu-id="7ec78-118">たとえば、ある組織では Windows で Active Directory ディレクトリ サービスを使用してユーザーを認証し、メインフレームで IBM の Resource Access Control Facility (RACF) を使用して同一ユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="7ec78-118">For example, in an organization, Windows uses Active Directory directory service to authenticate users, and mainframes use IBM's Resource Access Control Facility (RACF) to authenticate the same users.</span></span> <span data-ttu-id="7ec78-119">その組織では、ミドルウェア アプリケーションで、フロントエンド アプリケーションとバックエンド アプリケーションを統合します。</span><span class="sxs-lookup"><span data-stu-id="7ec78-119">Within the enterprise, middleware applications integrate the front-end and back-end applications.</span></span> <span data-ttu-id="7ec78-120">エンタープライズ シングル サインオンを使用すると、企業内のユーザーがフロントエンドとバックエンドの両方のアプリケーションに 1 組の資格情報だけを使用して接続できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7ec78-120">Enterprise Single Sign-On enables users in the enterprise to connect to both the front end and back end while using only one set of credentials.</span></span> <span data-ttu-id="7ec78-121">Windows 側開始シングル サインオン (最初の要求が Windows ドメイン環境から行われます) およびホスト側開始シングル サインオン (最初の要求が Windows 以外のドメイン環境から行われます) の両方を使用して Windows ドメイン内のリソースにアクセスすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="7ec78-121">It enables both Windows Initiated Single Sign-On (in which the initial request is made from the Windows domain environment) and Host Initiated Single Sign-On (in which the initial request is made from a non-Windows domain environment) to access a resource in the Windows domain.</span></span>  
  
 <span data-ttu-id="7ec78-122">さらに、**パスワード同期**SSO データベースの管理を簡略化し、ユーザー ディレクトリ間のパスワードの同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="7ec78-122">In addition, **Password Synchronization** simplifies administration of the SSO database, and keeps passwords in sync across user directories.</span></span> <span data-ttu-id="7ec78-123">これは、パスワード同期アダプターを構成して、パスワード同期ツールを使用して管理を使用して行います。</span><span class="sxs-lookup"><span data-stu-id="7ec78-123">This is done through the use of password synchronization adapters, which you can configure and manage using the Password Synchronization tools.</span></span>  
  
## <a name="the-enterprise-single-sign-on-system"></a><span data-ttu-id="7ec78-124">エンタープライズ シングル サインオン システム</span><span class="sxs-lookup"><span data-stu-id="7ec78-124">The Enterprise Single Sign-On System</span></span>  
 <span data-ttu-id="7ec78-125">エンタープライズ シングル サインオン (SSO) には、ローカルおよびネットワークの境界 (ドメインの境界を含む) の間で暗号化されたユーザー資格情報を格納および転送するサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7ec78-125">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local and network boundaries, including domain boundaries.</span></span> <span data-ttu-id="7ec78-126">SSO では SSO データベースに資格情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="7ec78-126">SSO stores the credentials in the SSO database.</span></span> <span data-ttu-id="7ec78-127">SSO には汎用のシングル サインオン ソリューションが用意されているので、ミドルウェア アプリケーションとカスタム アダプターが SSO を活用して環境間でのユーザー資格情報の格納および転送を安全に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7ec78-127">Because SSO provides a generic single sign-on solution, middleware applications and custom adapters can leverage SSO to securely store and transmit user credentials across the environment.</span></span> <span data-ttu-id="7ec78-128">エンド ユーザーは、アプリケーションごとに個別の資格情報を覚えておく必要がありません。</span><span class="sxs-lookup"><span data-stu-id="7ec78-128">End users do not have to remember different credentials for different applications.</span></span>  
  
 <span data-ttu-id="7ec78-129">シングル サインオン システムは、SSO データベース (1 つ)、マスター シークレット サーバー (1 つ)、およびシングル サインオン サーバー (複数可) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="7ec78-129">The Single Sign-On system consists of an SSO database, a master secret server, and one or more Single Sign-On servers.</span></span>  
  
 <span data-ttu-id="7ec78-130">SSO システムには、管理者が定義する関連アプリケーションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="7ec78-130">The SSO system contains affiliate applications that an administrator defines.</span></span> <span data-ttu-id="7ec78-131">関連アプリケーションは、エンタープライズ シングル サインオンを使用して接続する、ホスト、バックエンド システム、または基幹業務アプリケーションなどのシステムやサブシステムを表す論理的なエンティティです。</span><span class="sxs-lookup"><span data-stu-id="7ec78-131">An affiliate application is a logical entity that represents a system or sub-system such as a host, back-end system, or line of business application to which you are connecting using Enterprise Single Sign-On.</span></span> <span data-ttu-id="7ec78-132">各関連アプリケーションには複数のユーザー マッピングがあります。たとえば、Active Directory 内のユーザーの資格情報とそれに対応する RACF 資格情報のマッピングがあります。</span><span class="sxs-lookup"><span data-stu-id="7ec78-132">Each affiliate application has multiple user mappings; for example, it has the mappings between the credentials for a user in Active Directory and their corresponding RACF credentials.</span></span>  
  
 <span data-ttu-id="7ec78-133">SSO データベースは、SQL Server データベースです。関連アプリケーションに関する情報とすべての関連アプリケーションへの暗号化されたすべてのユーザー資格情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="7ec78-133">The SSO database is the SQL Server database that stores the information about the affiliate applications, as well as all the encrypted user credentials to all the affiliate applications.</span></span>  
  
 <span data-ttu-id="7ec78-134">マスター シークレット サーバーは、マスター シークレットを格納するエンタープライズ シングル サインオン サーバーです。</span><span class="sxs-lookup"><span data-stu-id="7ec78-134">The master secret server is the Enterprise Single Sign-On server that stores the master secret.</span></span> <span data-ttu-id="7ec78-135">システム内のその他すべてのシングル サインオン サーバーでは、マスター シークレット サーバーからマスター シークレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="7ec78-135">All other Single Sign-On servers in the system get the master secret from the master secret server.</span></span>  
  
 <span data-ttu-id="7ec78-136">また、SSO システムには 1 台以上の SSO サーバーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7ec78-136">The SSO system also contains one or more SSO Servers.</span></span> <span data-ttu-id="7ec78-137">SSO サーバーでは、Windows 資格情報とバックエンド資格情報のマッピングが行われ、SSO データベース内の資格情報が検索されます。管理者はそれらの資格情報を使用して SSO システムを管理します。</span><span class="sxs-lookup"><span data-stu-id="7ec78-137">These servers do the mapping between the Windows and back-end credentials, look up the credentials in the SSO database, and administrators use them to maintain the SSO system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ec78-138">SSO システムに保持できるマスター シークレット サーバーと SSO データベースは 1 つずつです。</span><span class="sxs-lookup"><span data-stu-id="7ec78-138">You can have only one master secret server and only one SSO database in your SSO system.</span></span> <span data-ttu-id="7ec78-139">SSO データベースはマスター シークレット サーバーに対してリモートであってもかまいません。</span><span class="sxs-lookup"><span data-stu-id="7ec78-139">The SSO database can be remote to the master secret server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ec78-140">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7ec78-140">In This Section</span></span>  
  
-   [<span data-ttu-id="7ec78-141">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="7ec78-141">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="7ec78-142">SSO コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7ec78-142">SSO Components</span></span>](../core/sso-components.md)  
  
-   [<span data-ttu-id="7ec78-143">SSO サーバー</span><span class="sxs-lookup"><span data-stu-id="7ec78-143">SSO Server</span></span>](../core/sso-server.md)  
  
-   [<span data-ttu-id="7ec78-144">マスター シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="7ec78-144">Master Secret Server</span></span>](../core/master-secret-server.md)  
  
-   [<span data-ttu-id="7ec78-145">SSO 関連アプリケーション</span><span class="sxs-lookup"><span data-stu-id="7ec78-145">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  
  
-   [<span data-ttu-id="7ec78-146">SSO マッピング</span><span class="sxs-lookup"><span data-stu-id="7ec78-146">SSO Mappings</span></span>](../core/sso-mappings.md)  
  
-   [<span data-ttu-id="7ec78-147">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="7ec78-147">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="7ec78-148">SSO を構成します。</span><span class="sxs-lookup"><span data-stu-id="7ec78-148">Configuring SSO</span></span>](../core/configuring-sso.md)