---
title: SSO の理解 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, about SSO
- Windows Integrated Single Sign-On
- Extranet Single Sign-On (Web SSO)
- Server-Based Intranet Single Sign-On
ms.assetid: 03f78a7b-4880-408f-9733-d07e19775d21
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c8d312c008159d5eebede8e65909b5fef9ce442
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292729"
---
# <a name="understanding-sso"></a><span data-ttu-id="f366c-102">SSO について</span><span class="sxs-lookup"><span data-stu-id="f366c-102">Understanding SSO</span></span>
<span data-ttu-id="f366c-103">エンタープライズ シングル サインオンについてでシングル サインオン サービスの使用可能な 3 つの種類を確認して今すぐに便利です。Windows 統合、エクストラネット、およびイントラネットです。</span><span class="sxs-lookup"><span data-stu-id="f366c-103">To understand Enterprise Single Sign-On, it is useful to look at the three types of Single Sign-On services available today: Windows integrated, extranet, and intranet.</span></span> <span data-ttu-id="f366c-104">これらについてでエンタープライズ シングル サインオン、3 番目のカテゴリに以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="f366c-104">These are described below, with Enterprise Single Sign-On falling into the third category.</span></span>  
  
## <a name="windows-integrated-single-sign-on"></a><span data-ttu-id="f366c-105">Windows 統合シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f366c-105">Windows Integrated Single Sign-On</span></span>  
 <span data-ttu-id="f366c-106">これらのサービスを有効にする一般的な認証メカニズムを使用して、ネットワーク内の複数のアプリケーションに接続します。</span><span class="sxs-lookup"><span data-stu-id="f366c-106">These services enable you to connect to multiple applications within your network that use a common authentication mechanism.</span></span> <span data-ttu-id="f366c-107">これらのサービスでは、要求し、ネットワークにログインし、資格情報を使用して、ユーザー権利に基づいて、実行できるアクションを決定した後、資格情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="f366c-107">These services request and verify your credentials after you log into the network, and use your credentials to determine the actions that you can perform based on your user rights.</span></span> <span data-ttu-id="f366c-108">たとえば、アプリケーションの統合システム ユーザーの資格情報が認証されると、Kerberos を使用して場合は、Kerberos と統合されているネットワーク内のリソースをアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f366c-108">For example, if applications integrate using Kerberos, after the system authenticates your user credentials you can access any resource in the network that is integrated with Kerberos.</span></span>  
  
## <a name="extranet-single-sign-on-web-sso"></a><span data-ttu-id="f366c-109">エクストラネット シングル サインオン (Web SSO)</span><span class="sxs-lookup"><span data-stu-id="f366c-109">Extranet Single Sign-On (Web SSO)</span></span>  
 <span data-ttu-id="f366c-110">これらのサービスを使用すると、ユーザーの資格情報の 1 つのセットを使用して、インターネット経由でリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f366c-110">These services enable you to access resources over the Internet by using a single set of user credentials.</span></span> <span data-ttu-id="f366c-111">ユーザーは、一連の異なる組織に属している別の Web サイトにログオンするための資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f366c-111">The user provides a set of credentials to log on to different Web sites that belong to different organizations.</span></span> <span data-ttu-id="f366c-112">この種類のシングル サインオンの例は、コンシューマーの Windows Live ID ベースのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="f366c-112">An example of this type of Single Sign-On is Windows Live ID for consumer based applications.</span></span> <span data-ttu-id="f366c-113">フェデレーション シナリオでは、Microsoft Active Directory フェデレーション サービスは Web SSO を使用します。</span><span class="sxs-lookup"><span data-stu-id="f366c-113">For federated scenarios, Microsoft Active Directory Federation Services enables Web SSO.</span></span>  
  
## <a name="server-based-intranet-single-sign-on"></a><span data-ttu-id="f366c-114">サーバー ベースのイントラネット シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f366c-114">Server-Based Intranet Single Sign-On</span></span>  
 <span data-ttu-id="f366c-115">これらのサービスでは、複数の異種アプリケーションとエンタープライズ環境内のシステムの統合を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f366c-115">These services enable you to integrate multiple heterogeneous applications and systems within the enterprise environment.</span></span> <span data-ttu-id="f366c-116">これらのアプリケーションおよびシステムでは、一般的な認証は使用しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f366c-116">These applications and systems may not use common authentication.</span></span> <span data-ttu-id="f366c-117">各アプリケーションでは、独自のユーザー ディレクトリ ストアがあります。</span><span class="sxs-lookup"><span data-stu-id="f366c-117">Each application has its own user directory store.</span></span> <span data-ttu-id="f366c-118">など、組織で Windows Active Directory ディレクトリ サービスを使用してユーザーを認証して、メインフレームが IBM のリソースへのアクセス管理機能 (RACF) を使用して同じユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="f366c-118">For example, in an organization, Windows uses Active Directory directory service to authenticate users, and mainframes use IBM's Resource Access Control Facility (RACF) to authenticate the same users.</span></span> <span data-ttu-id="f366c-119">企業内では、ミドルウェア アプリケーションは、フロント エンドとバックエンドのアプリケーションを統合します。</span><span class="sxs-lookup"><span data-stu-id="f366c-119">Within the enterprise, middleware applications integrate the front-end and back-end applications.</span></span> <span data-ttu-id="f366c-120">エンタープライズ シングル サインオン資格情報の 1 つだけ使用しながら、フロント エンドとバックエンドの両方に接続する、エンタープライズ内のユーザーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f366c-120">Enterprise Single Sign-On enables users in the enterprise to connect to both the front end and back end while using only one set of credentials.</span></span> <span data-ttu-id="f366c-121">内のリソースにアクセスする Windows 側開始シングル サインオン (これで、初期要求が行われる Windows ドメイン環境から) とホストが開始したシングル サインオン (を初期要求が行われた非 Windows ドメイン環境から) の両方を有効にしますWindows ドメイン。</span><span class="sxs-lookup"><span data-stu-id="f366c-121">It enables both Windows Initiated Single Sign-On (in which the initial request is made from the Windows domain environment) and Host Initiated Single Sign-On (in which the initial request is made from a non-Windows domain environment) to access a resource in the Windows domain.</span></span>  
  
 <span data-ttu-id="f366c-122">さらに、**パスワード同期**SSO データベースの管理を簡素化し、ユーザー ディレクトリ間でパスワード同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="f366c-122">In addition, **Password Synchronization** simplifies administration of the SSO database, and keeps passwords in sync across user directories.</span></span> <span data-ttu-id="f366c-123">これは、パスワード同期アダプタを構成して、パスワード同期ツールを使用して管理を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="f366c-123">This is done through the use of password synchronization adapters, which you can configure and manage using the Password Synchronization tools.</span></span>  
  
## <a name="the-enterprise-single-sign-on-system"></a><span data-ttu-id="f366c-124">エンタープライズ シングル サインオン システム</span><span class="sxs-lookup"><span data-stu-id="f366c-124">The Enterprise Single Sign-On System</span></span>  
 <span data-ttu-id="f366c-125">エンタープライズ シングル サインオン (SSO) では、暗号化されたユーザー資格情報をローカルおよびドメインの境界など、ネットワークの境界を格納および転送するサービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f366c-125">Enterprise Single Sign-On (SSO) provides services to store and transmit encrypted user credentials across local and network boundaries, including domain boundaries.</span></span> <span data-ttu-id="f366c-126">SSO は、SSO データベースの資格情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="f366c-126">SSO stores the credentials in the SSO database.</span></span> <span data-ttu-id="f366c-127">SSO は、汎用的な 1 つのシングル サインオン ソリューションを提供するためのミドルウェア アプリケーションとカスタム アダプターは安全に格納し、環境全体でユーザーの資格情報を送信する SSO を活用できます。</span><span class="sxs-lookup"><span data-stu-id="f366c-127">Because SSO provides a generic single sign-on solution, middleware applications and custom adapters can leverage SSO to securely store and transmit user credentials across the environment.</span></span> <span data-ttu-id="f366c-128">エンドユーザーは、さまざまなアプリケーションのさまざまな資格情報を記憶する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f366c-128">End users do not have to remember different credentials for different applications.</span></span>  
  
 <span data-ttu-id="f366c-129">シングル サインオン システムは、SSO データベースをマスター シークレット サーバー、および 1 つ以上のシングル サインオン サーバーで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f366c-129">The Single Sign-On system consists of an SSO database, a master secret server, and one or more Single Sign-On servers.</span></span>  
  
 <span data-ttu-id="f366c-130">SSO システムには、管理者が定義される関連アプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f366c-130">The SSO system contains affiliate applications that an administrator defines.</span></span> <span data-ttu-id="f366c-131">関連アプリケーションは、システムまたはサブシステムなど、ホスト、バックエンド システム、または基幹業務アプリケーションを表す論理エンティティを接続するエンタープライズ シングル サインオンを使用します。</span><span class="sxs-lookup"><span data-stu-id="f366c-131">An affiliate application is a logical entity that represents a system or sub-system such as a host, back-end system, or line of business application to which you are connecting using Enterprise Single Sign-On.</span></span> <span data-ttu-id="f366c-132">各関連アプリケーションが複数のユーザー マッピングたとえば、Active Directory でユーザーの資格情報と、対応する RACF 資格情報の間のマッピングがあります。</span><span class="sxs-lookup"><span data-stu-id="f366c-132">Each affiliate application has multiple user mappings; for example, it has the mappings between the credentials for a user in Active Directory and their corresponding RACF credentials.</span></span>  
  
 <span data-ttu-id="f366c-133">SSO データベースは、すべての関連アプリケーションへのすべての暗号化されたユーザー資格情報と同様に、関連アプリケーションに関する情報を格納する SQL Server データベースです。</span><span class="sxs-lookup"><span data-stu-id="f366c-133">The SSO database is the SQL Server database that stores the information about the affiliate applications, as well as all the encrypted user credentials to all the affiliate applications.</span></span>  
  
 <span data-ttu-id="f366c-134">マスター シークレット サーバーは、マスター シークレットを格納するエンタープライズ シングル サインオン サーバーです。</span><span class="sxs-lookup"><span data-stu-id="f366c-134">The master secret server is the Enterprise Single Sign-On server that stores the master secret.</span></span> <span data-ttu-id="f366c-135">すべての他のシングル サインオン サーバー システムでは、マスター シークレット サーバーからマスター シークレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="f366c-135">All other Single Sign-On servers in the system get the master secret from the master secret server.</span></span>  
  
 <span data-ttu-id="f366c-136">SSO システムには、1 つまたは複数の SSO サーバーも含まれています。</span><span class="sxs-lookup"><span data-stu-id="f366c-136">The SSO system also contains one or more SSO Servers.</span></span> <span data-ttu-id="f366c-137">管理者、SSO システムを維持するために使用して、サーバーでは、Windows とバックエンド資格情報間のマッピング見て、SSO データベース内の資格情報。</span><span class="sxs-lookup"><span data-stu-id="f366c-137">These servers do the mapping between the Windows and back-end credentials, look up the credentials in the SSO database, and administrators use them to maintain the SSO system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f366c-138">SSO システムに 1 つだけのマスタ シークレット サーバーおよび SSO データベースを 1 つだけことができます。</span><span class="sxs-lookup"><span data-stu-id="f366c-138">You can have only one master secret server and only one SSO database in your SSO system.</span></span> <span data-ttu-id="f366c-139">SSO データベースは、マスター シークレット サーバーをリモートにすることはできます。</span><span class="sxs-lookup"><span data-stu-id="f366c-139">The SSO database can be remote to the master secret server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f366c-140">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f366c-140">In This Section</span></span>  
  
-   [<span data-ttu-id="f366c-141">SSO ユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="f366c-141">SSO User Groups</span></span>](../core/sso-user-groups.md)  
  
-   [<span data-ttu-id="f366c-142">SSO コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f366c-142">SSO Components</span></span>](../core/sso-components.md)  
  
-   [<span data-ttu-id="f366c-143">SSO サーバー</span><span class="sxs-lookup"><span data-stu-id="f366c-143">SSO Server</span></span>](../core/sso-server.md)  
  
-   [<span data-ttu-id="f366c-144">マスター シークレット サーバー</span><span class="sxs-lookup"><span data-stu-id="f366c-144">Master Secret Server</span></span>](../core/master-secret-server.md)  
  
-   [<span data-ttu-id="f366c-145">SSO 関連アプリケーション</span><span class="sxs-lookup"><span data-stu-id="f366c-145">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  
  
-   [<span data-ttu-id="f366c-146">SSO マッピング</span><span class="sxs-lookup"><span data-stu-id="f366c-146">SSO Mappings</span></span>](../core/sso-mappings.md)  
  
-   [<span data-ttu-id="f366c-147">SSO チケット</span><span class="sxs-lookup"><span data-stu-id="f366c-147">SSO Tickets</span></span>](../core/sso-tickets.md)  
  
-   [<span data-ttu-id="f366c-148">SSO の構成</span><span class="sxs-lookup"><span data-stu-id="f366c-148">Configuring SSO</span></span>](../core/configuring-sso.md)