---
title: BizTalk Server のセキュリティの管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, security
- security, user accounts
- security, passwords
- certificates, security
- security, certificates
- security, BizTalk Server
- passwords, security
- user accounts, security
ms.assetid: adc89b0a-9846-4c99-b0fc-a32fc56ed769
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7486a23d5d606a1347c60b2971ebed66c354946
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000051"
---
# <a name="managing-biztalk-server-security"></a><span data-ttu-id="2aa9b-102">BizTalk Server のセキュリティを管理します。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-102">Managing BizTalk Server Security</span></span>
<span data-ttu-id="2aa9b-103">セキュリティで保護された Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境を維持するには、アカウント、証明書、およびパスワードを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-103">Maintaining a secure Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment requires that you manage accounts, certificates, and passwords.</span></span> <span data-ttu-id="2aa9b-104">BizTalk Server が処理するビジネス ドキュメントのセキュリティを確保できるよう、BizTalk Server 管理者は次のアカウントと証明書を管理します。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-104">To help ensure the security of the business documents handled by BizTalk Server, BizTalk Server administrators manage the following accounts and certificates:</span></span>  
  
- <span data-ttu-id="2aa9b-105">**BizTalk Server 管理者グループ**します。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-105">**BizTalk Server Administrators group**.</span></span> <span data-ttu-id="2aa9b-106">BizTalk 管理コンソールまたは Microsoft Windows Management Instrumentation (WMI) プロバイダを使用して管理タスクを実行するユーザーは、Microsoft SQL Server および Microsoft Windows の適切な権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-106">For users to perform administrative tasks either through the BizTalk Administration console or by using the Microsoft Windows Management Instrumentation (WMI) provider, they must be granted the proper privileges in Microsoft SQL Server and Microsoft Windows.</span></span> <span data-ttu-id="2aa9b-107">管理タスクの特権の詳細については、[最小セキュリティ ユーザー権限](../core/minimum-security-user-rights.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-107">For more information about the privileges for administrative tasks, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
   <span data-ttu-id="2aa9b-108">BizTalk Server 管理者グループにユーザーを追加または BizTalk Server 管理者グループからユーザーを削除する方法については、[BizTalk Server 管理者グループの管理方法](../core/how-to-manage-the-biztalk-server-administrators-group.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-108">For information about adding users to the BizTalk Server Administrators group or removing users from the BizTalk Server Administrators group, see [How to Manage the BizTalk Server Administrators Group](../core/how-to-manage-the-biztalk-server-administrators-group.md).</span></span>  
  
   <span data-ttu-id="2aa9b-109">エンタープライズ シングル サインオンに関する詳細については、[を使用して SSO](../core/using-sso.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-109">For more information about Enterprise Single Sign-On, see [Using SSO](../core/using-sso.md).</span></span>  
  
- <span data-ttu-id="2aa9b-110">**BizTalk Server Operators グループ**します。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-110">**BizTalk Server Operators group**.</span></span> <span data-ttu-id="2aa9b-111">BizTalk Server Operator は権限レベルの低いロールで、監視操作とトラブルシューティング操作にのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-111">The BizTalk Server Operator is a low privileged role that only has access to monitoring and troubleshooting actions.</span></span>  
  
   <span data-ttu-id="2aa9b-112">BizTalk Server Operator グループのメンバは、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-112">Members of the BizTalk Server Operators group can do the following:</span></span>  
  
  - <span data-ttu-id="2aa9b-113">サービスの状態とメッセージ フローの表示。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-113">View service state and message flow.</span></span>  
  
  - <span data-ttu-id="2aa9b-114">アプリケーションの開始または停止。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-114">Start or stop applications.</span></span>  
  
  - <span data-ttu-id="2aa9b-115">オーケストレーションの開始または停止。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-115">Start or stop orchestrations.</span></span>  
  
  - <span data-ttu-id="2aa9b-116">送信ポートまたは送信ポート グループの開始または停止。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-116">Start or stop send ports or send port groups.</span></span>  
  
  - <span data-ttu-id="2aa9b-117">受信場所の有効化または無効化。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-117">Enable or disable receive locations.</span></span> <span data-ttu-id="2aa9b-118">変更は、次回のキャッシュ更新の後で有効になります。キャッシュの更新間隔は既定では 60 秒で、</span><span class="sxs-lookup"><span data-stu-id="2aa9b-118">The changes do not take effect until the next cache refresh interval of 60 seconds, which is the default.</span></span> <span data-ttu-id="2aa9b-119">BizTalk Server のグループ レベルで設定できます。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-119">The cache refresh interval is set at the BizTalk Server group level.</span></span>  
  
  - <span data-ttu-id="2aa9b-120">サービス インスタンスの終了と再開。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-120">Terminate and resume service instances.</span></span>  
  
    <span data-ttu-id="2aa9b-121">BizTalk Server Operators グループのメンバは、次の操作を実行できません。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-121">Members of the BizTalk Server Operators group cannot do the following:</span></span>  
  
  - <span data-ttu-id="2aa9b-122">BizTalk Server の構成の変更。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-122">Modify the configuration for BizTalk Server.</span></span>  
  
  - <span data-ttu-id="2aa9b-123">個人情報 (PII) に分類されるメッセージ コンテキストのプロパティまたはメッセージ本文の表示。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-123">View message context properties classified as Personally Identifiable Information (PII) or message bodies.</span></span>  
  
  - <span data-ttu-id="2aa9b-124">実行中のシステムに対するサブスクリプションを削除や追加など、メッセージ ルーティングのコースを変更する操作。これには BizTalk Server ランタイムへのメッセージの公開も含まれます。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-124">Modify the course of message routing, such as removing or adding new subscriptions to the running system, including the ability to publish messages into the BizTalk Server runtime.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="2aa9b-125">BizTalk Server Operators グループのメンバであるユーザーが、BizTalk Server を実行しているコンピュータのローカル管理者でもある場合、このユーザーは、Operators グループ ロールの制限を受けずにこれらのコンピュータのデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-125">If a user who is a member of the BizTalk Server Operators group is also a local administrator on the computers running BizTalk Server, this user can access data beyond the role of the Operators group on these computers.</span></span> <span data-ttu-id="2aa9b-126">詳細については、[最小セキュリティ ユーザー権限](../core/minimum-security-user-rights.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-126">For more information, see [Minimum Security User Rights](../core/minimum-security-user-rights.md).</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="2aa9b-127">BizTalk Server Operators グループのメンバであるユーザーに対して、リモートの BizTalk Server の監視を許可する場合、このユーザーはリモート コンピュータのローカル管理者グループのメンバになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-127">If you want to allow a user who is a member of the BizTalk Server Operators group to monitor remote BizTalk servers, this user must also be a member of the local Administrators group on the remote computers.</span></span>  
  
- <span data-ttu-id="2aa9b-128">**ホストとサービス アカウント**します。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-128">**Hosts and service accounts**.</span></span> <span data-ttu-id="2aa9b-129">ホストとそれに関連するホスト インスタンスを作成するときには、ホストの Windows グループと、各ホスト インスタンスのサービス アカウント資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-129">When creating a host and its associated host instances, you must provide the Windows group for the host and the service account credentials for each host instance.</span></span> <span data-ttu-id="2aa9b-130">ホスト インスタンスのサービス アカウントは、ホストの Windows グループのメンバである必要があります。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-130">You must ensure that the host instance service accounts are members of the Windows group for the host.</span></span>  
  
- <span data-ttu-id="2aa9b-131">**署名証明書**します。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-131">**Signing certificates**.</span></span> <span data-ttu-id="2aa9b-132">署名証明書 (秘密キー証明書) は、BizTalk グループに対して指定するものです。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-132">Signing certificates (private key certificates) are specified for the BizTalk group.</span></span> <span data-ttu-id="2aa9b-133">これらは省略可能で、BizTalk Server 管理者がいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-133">These are optional and can be changed at any time by a BizTalk Server administrator.</span></span>  
  
  <span data-ttu-id="2aa9b-134">BizTalk Server で使用される Windows アカウントの詳細については、[Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2aa9b-134">For more complete information about Windows accounts that BizTalk Server uses, see [Windows Groups and User Accounts in BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2aa9b-135">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2aa9b-135">In This Section</span></span>  
  
-   [<span data-ttu-id="2aa9b-136">Windows グループおよびユーザー アカウントの管理のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="2aa9b-136">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)  
  
-   [<span data-ttu-id="2aa9b-137">証明書を管理するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="2aa9b-137">Best Practices for Managing Certificates</span></span>](../core/best-practices-for-managing-certificates1.md)  
  
-   [<span data-ttu-id="2aa9b-138">Windows ループおよびユーザー アカウントの管理</span><span class="sxs-lookup"><span data-stu-id="2aa9b-138">Managing Windows Groups and User Accounts</span></span>](../core/managing-windows-groups-and-user-accounts.md)