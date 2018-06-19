---
title: Certificates1 を管理するためのベスト プラクティス |Microsoft ドキュメント
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
ms.openlocfilehash: e72d87530e5d080bd98ed55c2d29ca9554430375
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232090"
---
# <a name="best-practices-for-managing-certificates"></a><span data-ttu-id="6af24-102">証明書を管理するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="6af24-102">Best Practices for Managing Certificates</span></span>
<span data-ttu-id="6af24-103">ここでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で証明書を管理する際のベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6af24-103">This section provides best practices for managing certificates in your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
-   <span data-ttu-id="6af24-104">**環境内の脅威モデル分析を行う**</span><span class="sxs-lookup"><span data-stu-id="6af24-104">**Do a Threat Model Analysis of your environment**</span></span>  
  
     <span data-ttu-id="6af24-105">使用している環境の脅威モデル分析 (TMA) を実行して、署名証明書または暗号化証明書でセキュリティの脅威を緩和できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="6af24-105">Do a Threat Model Analysis (TMA) of your environment to determine whether signing or encryption certificates will help you mitigate security threats.</span></span>  
  
-   <span data-ttu-id="6af24-106">**パートナーと共に公開キー証明書の計画を作成します。**</span><span class="sxs-lookup"><span data-stu-id="6af24-106">**Create a plan for public key certificates with partners**</span></span>  
  
     <span data-ttu-id="6af24-107">パートナーと共に公開キーの証明書の送受信の計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="6af24-107">Create a plan for sending and receiving public key certificates with partners.</span></span> <span data-ttu-id="6af24-108">パーティの解決に署名証明書を使用しない場合は、パブリック証明書をメッセージに添付できます。この場合、使用するシステムで事前に証明書のコピーを用意する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6af24-108">If you are not using signing certificates for party resolution, the public certificate can be attached to the message, in which case you do not need a copy of the certificate in your system beforehand.</span></span>  
  
-   <span data-ttu-id="6af24-109">**設定された間隔で証明書失効リストをダウンロードします。**</span><span class="sxs-lookup"><span data-stu-id="6af24-109">**Download the certificate revocation list at set intervals**</span></span>  
  
     <span data-ttu-id="6af24-110">設定した間隔で、証明機関 (CA) から証明書の失効一覧 (CRL) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6af24-110">Download the certificate revocation list (CRL) from your certification authority (CA) at set intervals.</span></span> <span data-ttu-id="6af24-111">週に 1 度の実行をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6af24-111">We recommend doing this once a week.</span></span> <span data-ttu-id="6af24-112">BizTalk サーバーが参加しているドメインの CA がある場合、CRL は自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="6af24-112">The CRLs are downloaded automatically if there is a CA for the domain in which the BizTalk servers are joined.</span></span>  
  
-   <span data-ttu-id="6af24-113">**公開キーの送信のパートナーとガイドラインを確立します。**</span><span class="sxs-lookup"><span data-stu-id="6af24-113">**Establish guidelines with partners for submitting public keys**</span></span>  
  
     <span data-ttu-id="6af24-114">パートナーとのサービス レベル契約 (SLA) の一部として、公開キーの送信、証明書の有効期間の終了が近づいた際の通知の受信、証明書が無効になる場合の通知の受け取りに関して、ガイドラインを設定します。</span><span class="sxs-lookup"><span data-stu-id="6af24-114">As part of your Service Level Agreement (SLA) with your partner, establish guidelines for submitting public keys, notifying you when their certificates are about to expire, and notifying you when they revoke a certificate.</span></span>  
  
-   <span data-ttu-id="6af24-115">**署名証明書を確認してください。**</span><span class="sxs-lookup"><span data-stu-id="6af24-115">**Verify signing certificates**</span></span>  
  
     <span data-ttu-id="6af24-116">署名証明書を証明書の失効一覧と照合して確認します。</span><span class="sxs-lookup"><span data-stu-id="6af24-116">Make sure you verify the signing certificates against the certificate revocation list.</span></span> <span data-ttu-id="6af24-117">署名証明書を確認する方法の詳細については、次を参照してください。 [- MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="6af24-117">For more information about how to verify the signing certificates, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
-   <span data-ttu-id="6af24-118">**サービス拒否攻撃のデジタル署名用の回避します。**</span><span class="sxs-lookup"><span data-stu-id="6af24-118">**Avoid denial of service attacks for digital signatures**</span></span>  
  
     <span data-ttu-id="6af24-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がデジタル署名を検証できなかった場合に、そのメッセージをどのように取り扱うかについて決定します。</span><span class="sxs-lookup"><span data-stu-id="6af24-119">Determine what you want to do with messages when [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot validate the digital signature.</span></span> <span data-ttu-id="6af24-120">設定、**認証**受信ポートのプロパティにサービス拒否攻撃が防止されます。</span><span class="sxs-lookup"><span data-stu-id="6af24-120">Setting the **Authentication** property on the receive port will help prevent denial of service attacks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6af24-121">**認証]-[メッセージの削除**と**認証]-[メッセージの保持**受信ポートのフラグがパーティの解決パイプライン コンポーネントが正しく構成することを必要とし、パーティであります。BizTalk Server で定義されます。</span><span class="sxs-lookup"><span data-stu-id="6af24-121">The **Authentication - Drop messages** and **Authentication - Keep messages** flags on the receive port require that the Party Resolution pipeline component be configured correctly, and that the parties are defined in BizTalk Server.</span></span> <span data-ttu-id="6af24-122">パーティの解決パイプライン コンポーネントの構成の詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](../core/party-resolution-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="6af24-122">For more information about configuring the Party Resolution pipeline component, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>  
  
-   <span data-ttu-id="6af24-123">**独立した作成用暗号化および暗号化されていないメッセージの受信場所**</span><span class="sxs-lookup"><span data-stu-id="6af24-123">**Create separate receive locations for encrypted and unencrypted messages**</span></span>  
  
     <span data-ttu-id="6af24-124">パートナーから MIME 暗号化されているメッセージと暗号化されていないメッセージを受信することが予測される場合は、それぞれに対して異なるホストの異なる受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="6af24-124">If you plan to receive MIME-encrypted messages from some partners and unencrypted messages from other partners, create separate receive locations in different hosts for encrypted and unencrypted messages.</span></span> <span data-ttu-id="6af24-125">MIME 暗号化されたメッセージのみを行うには、構成、**非 MIME メッセージを許可する**オプションで、MIME/SMIME デコーダ パイプライン コンポーネントを**いいえ**です。</span><span class="sxs-lookup"><span data-stu-id="6af24-125">When you expect only MIME-encrypted messages, configure the **Allow Non MIME Message** option in the Decode MIME/SMIME pipeline component to **No**.</span></span>  
  
-   <span data-ttu-id="6af24-126">**パートナーと証明書を管理します。**</span><span class="sxs-lookup"><span data-stu-id="6af24-126">**Manage certificates with partners**</span></span>  
  
     <span data-ttu-id="6af24-127">パートナー管理に含まれる作業として、証明書の管理を行います。</span><span class="sxs-lookup"><span data-stu-id="6af24-127">Make certificate management part of your partner management practices.</span></span> <span data-ttu-id="6af24-128">BizTalk Server 環境でパーティの追加または削除を行う場合は、そのパートナーに関連付けられた証明書の追加または削除を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6af24-128">When you add or remove a party from the BizTalk Server environment, we recommend that you add or remove the certificates associated with that partner.</span></span>  
  
-   <span data-ttu-id="6af24-129">**ホスト インスタンスを削除する前に証明書を削除します。**</span><span class="sxs-lookup"><span data-stu-id="6af24-129">**Remove certificates before removing a host instance**</span></span>  
  
     <span data-ttu-id="6af24-130">BizTalk サーバーからホスト インスタンスを削除する前に、ホスト インスタンスの実行に使用されているアカウントの個人用ストアにある証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="6af24-130">Before removing a host instance from a BizTalk server, remove the certificates in the personal store of the account under which the host instance is running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af24-131">参照</span><span class="sxs-lookup"><span data-stu-id="6af24-131">See Also</span></span>  
 <span data-ttu-id="6af24-132">[BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md) </span><span class="sxs-lookup"><span data-stu-id="6af24-132">[Managing BizTalk Server Security](../core/managing-biztalk-server-security.md) </span></span>  
 [<span data-ttu-id="6af24-133">Windows グループとユーザー アカウントを管理するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="6af24-133">Best Practices for Managing Windows Groups and User Accounts</span></span>](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)