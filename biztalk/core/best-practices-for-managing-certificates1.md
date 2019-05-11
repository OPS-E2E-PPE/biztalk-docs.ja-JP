---
title: Certificates1 を管理するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, certificates
- certificates, security
- security, certificates
- certificates, best practices
- best practices, security
- security, best practices
ms.assetid: cd182df4-0fcd-409c-9221-89f92e069f07
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b01936259f9259335f43b39ed19b741b20bf25b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358211"
---
# <a name="best-practices-for-managing-certificates"></a><span data-ttu-id="d0c3a-102">証明書を管理するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="d0c3a-102">Best Practices for Managing Certificates</span></span>
<span data-ttu-id="d0c3a-103">ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で証明書を管理する際のベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-103">This section provides best practices for managing certificates in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
- <span data-ttu-id="d0c3a-104">**環境内の脅威モデル分析を行う**</span><span class="sxs-lookup"><span data-stu-id="d0c3a-104">**Do a Threat Model Analysis of your environment**</span></span>  
  
   <span data-ttu-id="d0c3a-105">使用している環境の脅威モデル分析 (TMA) を実行して、署名証明書または暗号化証明書でセキュリティの脅威を緩和できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-105">Do a Threat Model Analysis (TMA) of your environment to determine whether signing or encryption certificates will help you mitigate security threats.</span></span>  
  
- <span data-ttu-id="d0c3a-106">**パートナーと共に公開キー証明書の計画を作成します。**</span><span class="sxs-lookup"><span data-stu-id="d0c3a-106">**Create a plan for public key certificates with partners**</span></span>  
  
   <span data-ttu-id="d0c3a-107">パートナーと共に公開キーの証明書の送受信の計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-107">Create a plan for sending and receiving public key certificates with partners.</span></span> <span data-ttu-id="d0c3a-108">パーティの解決に署名証明書を使用しない場合は、パブリック証明書をメッセージに添付できます。この場合、使用するシステムで事前に証明書のコピーを用意する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-108">If you are not using signing certificates for party resolution, the public certificate can be attached to the message, in which case you do not need a copy of the certificate in your system beforehand.</span></span>  
  
- <span data-ttu-id="d0c3a-109">**設定された間隔で、証明書失効リストをダウンロードします。**</span><span class="sxs-lookup"><span data-stu-id="d0c3a-109">**Download the certificate revocation list at set intervals**</span></span>  
  
   <span data-ttu-id="d0c3a-110">設定した間隔で、証明機関 (CA) から証明書の失効一覧 (CRL) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-110">Download the certificate revocation list (CRL) from your certification authority (CA) at set intervals.</span></span> <span data-ttu-id="d0c3a-111">週に 1 度の実行をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-111">We recommend doing this once a week.</span></span> <span data-ttu-id="d0c3a-112">BizTalk サーバーが参加しているドメインの CA がある場合、CRL は自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-112">The CRLs are downloaded automatically if there is a CA for the domain in which the BizTalk servers are joined.</span></span>  
  
- <span data-ttu-id="d0c3a-113">**パートナーと公開キーを送信するためのガイドラインを確立します。**</span><span class="sxs-lookup"><span data-stu-id="d0c3a-113">**Establish guidelines with partners for submitting public keys**</span></span>  
  
   <span data-ttu-id="d0c3a-114">パートナーとのサービス レベル契約 (SLA) の一部として、公開キーの送信、証明書の有効期間の終了が近づいた際の通知の受信、証明書が無効になる場合の通知の受け取りに関して、ガイドラインを設定します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-114">As part of your Service Level Agreement (SLA) with your partner, establish guidelines for submitting public keys, notifying you when their certificates are about to expire, and notifying you when they revoke a certificate.</span></span>  
  
- <span data-ttu-id="d0c3a-115">**署名証明書を確認します。**</span><span class="sxs-lookup"><span data-stu-id="d0c3a-115">**Verify signing certificates**</span></span>  
  
   <span data-ttu-id="d0c3a-116">署名証明書を証明書の失効一覧と照合して確認します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-116">Make sure you verify the signing certificates against the certificate revocation list.</span></span> <span data-ttu-id="d0c3a-117">署名証明書を確認する方法の詳細については、次を参照してください。 [MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-117">For more information about how to verify the signing certificates, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
- <span data-ttu-id="d0c3a-118">**デジタル署名に対するサービス拒否攻撃の拒否を防ぐ**</span><span class="sxs-lookup"><span data-stu-id="d0c3a-118">**Avoid denial of service attacks for digital signatures**</span></span>  
  
   <span data-ttu-id="d0c3a-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がデジタル署名を検証できなかった場合に、そのメッセージをどのように取り扱うかについて決定します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-119">Determine what you want to do with messages when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot validate the digital signature.</span></span> <span data-ttu-id="d0c3a-120">設定、**認証**受信ポートのプロパティにサービス拒否攻撃が防止されます。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-120">Setting the **Authentication** property on the receive port will help prevent denial of service attacks.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="d0c3a-121">**認証 - メッセージの削除**と**認証 - メッセージの保持**受信ポートのフラグは、パーティの解決パイプライン コンポーネントを正しく構成することが必要ですし、パーティであります。BizTalk Server で定義されます。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-121">The **Authentication - Drop messages** and **Authentication - Keep messages** flags on the receive port require that the Party Resolution pipeline component be configured correctly, and that the parties are defined in BizTalk Server.</span></span> <span data-ttu-id="d0c3a-122">パーティの解決パイプライン コンポーネントの構成の詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-122">For more information about configuring the Party Resolution pipeline component, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
- <span data-ttu-id="d0c3a-123">**別の作成用暗号化および暗号化されていないメッセージの受信場所**</span><span class="sxs-lookup"><span data-stu-id="d0c3a-123">**Create separate receive locations for encrypted and unencrypted messages**</span></span>  
  
   <span data-ttu-id="d0c3a-124">パートナーから MIME 暗号化されているメッセージと暗号化されていないメッセージを受信することが予測される場合は、それぞれに対して異なるホストの異なる受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-124">If you plan to receive MIME-encrypted messages from some partners and unencrypted messages from other partners, create separate receive locations in different hosts for encrypted and unencrypted messages.</span></span> <span data-ttu-id="d0c3a-125">MIME 暗号化されたメッセージのみが予想される場合は、構成、**非 MIME メッセージを許可する**オプションにデコード MIME/SMIME パイプライン コンポーネントで**いいえ**します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-125">When you expect only MIME-encrypted messages, configure the **Allow Non MIME Message** option in the Decode MIME/SMIME pipeline component to **No**.</span></span>  
  
- <span data-ttu-id="d0c3a-126">**パートナーと証明書を管理します。**</span><span class="sxs-lookup"><span data-stu-id="d0c3a-126">**Manage certificates with partners**</span></span>  
  
   <span data-ttu-id="d0c3a-127">パートナー管理に含まれる作業として、証明書の管理を行います。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-127">Make certificate management part of your partner management practices.</span></span> <span data-ttu-id="d0c3a-128">BizTalk Server 環境でパーティの追加または削除を行う場合は、そのパートナーに関連付けられた証明書の追加または削除を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-128">When you add or remove a party from the BizTalk Server environment, we recommend that you add or remove the certificates associated with that partner.</span></span>  
  
- <span data-ttu-id="d0c3a-129">**ホスト インスタンスを削除する前に証明書を削除します。**</span><span class="sxs-lookup"><span data-stu-id="d0c3a-129">**Remove certificates before removing a host instance**</span></span>  
  
   <span data-ttu-id="d0c3a-130">BizTalk サーバーからホスト インスタンスを削除する前に、ホスト インスタンスの実行に使用されているアカウントの個人用ストアにある証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="d0c3a-130">Before removing a host instance from a BizTalk server, remove the certificates in the personal store of the account under which the host instance is running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0c3a-131">参照</span><span class="sxs-lookup"><span data-stu-id="d0c3a-131">See Also</span></span>  
 <span data-ttu-id="d0c3a-132">[BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="d0c3a-132">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 [<span data-ttu-id="d0c3a-133">Windows グループおよびユーザー アカウントの管理のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="d0c3a-133">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)