---
title: 潜在的な脅威を識別する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- planning, security
- security, potential threats
- security, planning
ms.assetid: 1d70a0c1-6daf-47bb-af15-a4b35a7bafc2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbd2feb0b6a09905efb7275b1cc6f0e6ef2b13d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972571"
---
# <a name="identifying-potential-threats"></a><span data-ttu-id="9f9db-102">潜在的な脅威を識別します。</span><span class="sxs-lookup"><span data-stu-id="9f9db-102">Identifying Potential Threats</span></span>
<span data-ttu-id="9f9db-103">STRIDE モデルを使用すると、BizTalk Server の展開に存在する可能性がある脅威を特定できます。</span><span class="sxs-lookup"><span data-stu-id="9f9db-103">You can use the STRIDE model to identify potential threats to your BizTalk Server deployment.</span></span> <span data-ttu-id="9f9db-104">STRIDE は、次のカテゴリから派生した頭字語: *S*poofing identity、 *T*データ、ampering *R*、これが否認*は*情報漏えい、 *D*サービス、および特権の昇格のービスを拒否します。</span><span class="sxs-lookup"><span data-stu-id="9f9db-104">STRIDE is an acronym derived from the following categories: *S*poofing identity, *T*ampering with data, *R*epudiation, *I*nformation disclosure, *D*enial of service, and Elevation of privileges.</span></span> <span data-ttu-id="9f9db-105">このセクションには、BizTalk Server 環境に存在する可能性がある脅威の例と、脅威を緩和するメカニズムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9f9db-105">This section contains examples of potential threats to a BizTalk Server environment, and mechanisms to mitigate them.</span></span>  
  
 <span data-ttu-id="9f9db-106">**Id を偽装**</span><span class="sxs-lookup"><span data-stu-id="9f9db-106">**Spoofing identity**</span></span>  
  
- <span data-ttu-id="9f9db-107">バインド ファイルにパスワードを格納して保存すると、未認証のユーザーがパスワードを読み取り、そのパスワードを使用して BizTalk Server に接続することがあります。そのため、悪影響が及ぶ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9f9db-107">If you save passwords in the binding files, and save these binding files, unauthorized users could read the passwords and use them to connect to the BizTalk Servers, and possibly cause harm.</span></span> <span data-ttu-id="9f9db-108">バインド ファイルにパスワードを格納しないでください。また、随意アクセス制御リスト (DACL) を使用して、機密データを含んでいると考えられるファイルへのアクセスを制限してください。</span><span class="sxs-lookup"><span data-stu-id="9f9db-108">You should not save passwords in binding files, and you should use discretionary access control lists (DACLs) to restrict access to files that may contain sensitive data.</span></span>  
  
  <span data-ttu-id="9f9db-109">**データの改ざん**</span><span class="sxs-lookup"><span data-stu-id="9f9db-109">**Tampering with data**</span></span>  
  
- <span data-ttu-id="9f9db-110">悪意のあるユーザーが、パートナーから BizTalk Server に送信されたメッセージを傍受し、メッセージの内容を変更することがあります。</span><span class="sxs-lookup"><span data-stu-id="9f9db-110">Malicious users can intercept messages from partners to BizTalk Server, and modify the content of the message.</span></span> <span data-ttu-id="9f9db-111">デジタル署名を使用すると、悪意のあるユーザーがメッセージの送信中にメッセージを改ざんするのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="9f9db-111">You can use digital signatures to prevent malicious users from tampering with messages while they are in transit.</span></span>  
  
  <span data-ttu-id="9f9db-112">**否認不可**</span><span class="sxs-lookup"><span data-stu-id="9f9db-112">**Repudiation**</span></span>  
  
- <span data-ttu-id="9f9db-113">BizTalk で送受信するメッセージを追跡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f9db-113">You need to keep track of messages that BizTalk sends and receives.</span></span> <span data-ttu-id="9f9db-114">デジタル署名を使用すると、ユーザーがメッセージを送信したこと、およびパートナーがメッセージを送信したことを証明できます。</span><span class="sxs-lookup"><span data-stu-id="9f9db-114">You can use digital signatures to prove that you sent a message and that your partners sent you a message.</span></span>  
  
  <span data-ttu-id="9f9db-115">**情報漏えいが起こる**</span><span class="sxs-lookup"><span data-stu-id="9f9db-115">**Information disclosure**</span></span>  
  
- <span data-ttu-id="9f9db-116">悪意のあるユーザーが、BizTalk Server と Microsoft SQL Server™ 間のクリア テキスト形式の通信を読み取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="9f9db-116">Malicious users can read clear-text communication between BizTalk Server and Microsoft SQL Server™.</span></span> <span data-ttu-id="9f9db-117">サーバー間の通信をセキュリティで保護するのにインターネット プロトコル セキュリティ (IPSec) または Secure Sockets Layer (SSL) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f9db-117">You can use Internet Protocol security (IPSec), or Secure Sockets Layer (SSL) to help secure the communication between servers.</span></span> <span data-ttu-id="9f9db-118">各サーバーへのアクセスを制限するには、ファイアウォールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f9db-118">You can use firewalls to limit access to each server.</span></span> <span data-ttu-id="9f9db-119">メッセージの送信中にメッセージのプライバシーを保証するには、暗号化を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f9db-119">You can use encryption to help ensure the privacy of the message while it is in transit.</span></span>  
  
- <span data-ttu-id="9f9db-120">未認証のユーザーが、ネットワーク共有またはディレクトリ上の情報にアクセスすることがあります。</span><span class="sxs-lookup"><span data-stu-id="9f9db-120">Unauthorized users may access information on network shares or directories.</span></span> <span data-ttu-id="9f9db-121">強力な随意アクセス制御リスト (DACL) を使用すると、リソースを使用するアカウントへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="9f9db-121">You can use strong discretionary access control lists (DACLs) to limit access to the accounts that use the resources.</span></span>  
  
- <span data-ttu-id="9f9db-122">BizTalk ホスト インスタンスを実行しているコンピュータの Windows 管理者が、不正を行ってさまざまなレベルの攻撃 (情報の漏えいやサービスの拒否など) を実行することがあります。</span><span class="sxs-lookup"><span data-stu-id="9f9db-122">The Windows administrator on a computer running a BizTalk Host instance can misbehave and carry out different levels of attacks (for example, information disclosure, or denial of service).</span></span> <span data-ttu-id="9f9db-123">ただし、ほとんどの場合、このような攻撃は攻撃者が侵入したコンピュータの特定のホストに制限できます。</span><span class="sxs-lookup"><span data-stu-id="9f9db-123">However, in most cases you can limit these attacks to the particular host whose computer the attacker compromised.</span></span>  
  
  <span data-ttu-id="9f9db-124">**サービス拒否が起こる**</span><span class="sxs-lookup"><span data-stu-id="9f9db-124">**Denial of service**</span></span>  
  
- <span data-ttu-id="9f9db-125">悪意のあるユーザーが、BizTalk Server に大量のメッセージを送信し、BizTalk が有効なメッセージを受信できなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="9f9db-125">A malicious user can send a large number of messages to BizTalk Server, which could prevent BizTalk from receiving valid messages.</span></span> <span data-ttu-id="9f9db-126">この脅威を緩和する方法の詳細については、次を参照してください。[拒否のサービス攻撃の緩和](../core/mitigating-denial-of-service-attacks.md)します。</span><span class="sxs-lookup"><span data-stu-id="9f9db-126">For more information about mitigation techniques to this threat, see [Mitigating Denial of Service Attacks](../core/mitigating-denial-of-service-attacks.md).</span></span>  
  
  <span data-ttu-id="9f9db-127">**特権の昇格**</span><span class="sxs-lookup"><span data-stu-id="9f9db-127">**Elevation of privileges**</span></span>  
  
- <span data-ttu-id="9f9db-128">権限の昇格という脅威は通常、信頼していないコードが信頼されている環境で実行されたとき、または悪意のあるユーザーがソフトウェアや構成の不具合を悪用したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="9f9db-128">Elevation of privileges threats typically occur when code you do not trust runs in a trusted environment, or when a malicious user exploits a software or configuration flaw.</span></span> <span data-ttu-id="9f9db-129">環境に展開しているアセンブリやその他のコンポーネントが信頼されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f9db-129">You must ensure that you trust the assemblies and other components you deploy in your environment.</span></span> <span data-ttu-id="9f9db-130">権限の昇格攻撃の可能性を最小限に抑えるには、最小限のアクセス許可が与えられた一意のアカウントを使用し、ランタイム サービスやランタイム操作に管理者アカウントを使用しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f9db-130">To minimize the possibility of an elevation of privileges attack, you should use non-overlapping, least permission accounts, and you should avoid the use of administrative accounts for run time services and operations.</span></span> <span data-ttu-id="9f9db-131">また、環境内で実行するコンポーネント、アプリケーション、サービスの数を最小限にしてください。</span><span class="sxs-lookup"><span data-stu-id="9f9db-131">You should also minimize the number of components, applications, and services running in the environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f9db-132">参照</span><span class="sxs-lookup"><span data-stu-id="9f9db-132">See Also</span></span>  
 <span data-ttu-id="9f9db-133">[攻撃のサービス拒否攻撃の緩和](../core/mitigating-denial-of-service-attacks.md) </span><span class="sxs-lookup"><span data-stu-id="9f9db-133">[Mitigating Denial of Service Attacks](../core/mitigating-denial-of-service-attacks.md) </span></span>  
 <span data-ttu-id="9f9db-134">[BizTalk Server の展開のセキュリティに関する推奨事項](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span><span class="sxs-lookup"><span data-stu-id="9f9db-134">[Security Recommendations for a BizTalk Server Deployment](../core/security-recommendations-for-a-biztalk-server-deployment.md) </span></span>  
 [<span data-ttu-id="9f9db-135">セキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="9f9db-135">Planning for Security</span></span>](../core/planning-for-security.md)