---
title: "Certificates2 を管理するためのベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71fa00cc-2e0c-46b3-ae62-f130a5b5f4f5
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 39f47159fbeacb1b4975cf9f1aa0a8c9a030ecc3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-managing-certificates"></a><span data-ttu-id="a724d-102">証明書を管理するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="a724d-102">Best Practices for Managing Certificates</span></span>
<span data-ttu-id="a724d-103">このセクションでは、Microsoft の証明書を管理するためのベスト プラクティスを説明[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]環境。</span><span class="sxs-lookup"><span data-stu-id="a724d-103">This section provides best practices for managing certificates in your Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] environment.</span></span>  
  
## <a name="assess-and-plan-your-use-of-certificates"></a><span data-ttu-id="a724d-104">評価し、証明書の使用を計画</span><span class="sxs-lookup"><span data-stu-id="a724d-104">Assess and Plan Your Use of Certificates</span></span>  
 <span data-ttu-id="a724d-105">**環境内の脅威モデル分析を行う**</span><span class="sxs-lookup"><span data-stu-id="a724d-105">**Do a Threat Model Analysis of your environment**</span></span>  
  
-   <span data-ttu-id="a724d-106">使用している環境の脅威モデル分析 (TMA) を実行して、署名証明書または暗号化証明書でセキュリティの脅威を緩和できるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="a724d-106">Do a Threat Model Analysis (TMA) of your environment to determine whether signing or encryption certificates will help you mitigate security threats.</span></span>  
  
 <span data-ttu-id="a724d-107">**パートナーと共に公開キー証明書の計画を作成します。**</span><span class="sxs-lookup"><span data-stu-id="a724d-107">**Create a plan for public key certificates with partners**</span></span>  
  
-   <span data-ttu-id="a724d-108">公開キー証明書を送信して、パートナーから公開キー証明書を受信する計画を作成します。</span><span class="sxs-lookup"><span data-stu-id="a724d-108">Create a plan for sending public key certificates to and receiving public key certificates from partners.</span></span> <span data-ttu-id="a724d-109">パーティの解決に署名証明書を使用しない場合は、パブリック証明書をメッセージに添付できます。この場合、使用するシステムで事前に証明書のコピーを用意する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a724d-109">If you are not using signing certificates for party resolution, the public certificate can be attached to the message, in which case you do not need a copy of the certificate in your system beforehand.</span></span>  
  
 <span data-ttu-id="a724d-110">**公開キーの送信のパートナーとガイドラインを確立します。**</span><span class="sxs-lookup"><span data-stu-id="a724d-110">**Establish guidelines with partners for submitting public keys**</span></span>  
  
-   <span data-ttu-id="a724d-111">パートナーとのサービス レベル契約 (SLA) の一部として、公開キーの送信、証明書の有効期間の終了が近づいた際の通知の受信、証明書が無効になる場合の通知の受け取りに関して、ガイドラインを設定します。</span><span class="sxs-lookup"><span data-stu-id="a724d-111">As part of your Service Level Agreement (SLA) with your partner, establish guidelines for submitting public keys, notifying you when their certificates are about to expire, and notifying you when they revoke a certificate.</span></span>  
  
## <a name="install-certificates"></a><span data-ttu-id="a724d-112">証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a724d-112">Install Certificates</span></span>  
 <span data-ttu-id="a724d-113">**設定された間隔で証明書失効リストをダウンロードします。**</span><span class="sxs-lookup"><span data-stu-id="a724d-113">**Download the certificate revocation list at set intervals**</span></span>  
  
-   <span data-ttu-id="a724d-114">設定した間隔で、証明機関 (CA) から証明書の失効一覧 (CRL) をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a724d-114">Download the certificate revocation list (CRL) from your certification authority (CA) at set intervals.</span></span> <span data-ttu-id="a724d-115">週に 1 度の実行をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a724d-115">We recommend doing this once a week.</span></span> <span data-ttu-id="a724d-116">BizTalk サーバーが参加しているドメインの CA がある場合、CRL は自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="a724d-116">The CRLs are downloaded automatically if there is a CA for the domain in which the BizTalk servers are joined.</span></span>  
  
 <span data-ttu-id="a724d-117">**署名証明書を確認してください。**</span><span class="sxs-lookup"><span data-stu-id="a724d-117">**Verify signing certificates**</span></span>  
  
-   <span data-ttu-id="a724d-118">署名証明書を証明書の失効一覧と照合して確認します。</span><span class="sxs-lookup"><span data-stu-id="a724d-118">Make sure you verify the signing certificates against the certificate revocation list.</span></span> <span data-ttu-id="a724d-119">署名証明書を確認する方法の詳細については、次を参照してください。 [MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](http://go.microsoft.com/fwlink/?LinkId=155145)(http://go.microsoft.com/fwlink/?LinkId=155145) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="a724d-119">For more information about how to verify the signing certificates, see [How to Configure the MIME/SMIME Decoder Pipeline Component](http://go.microsoft.com/fwlink/?LinkId=155145) (http://go.microsoft.com/fwlink/?LinkId=155145) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="a724d-120">**パートナーと証明書を管理します。**</span><span class="sxs-lookup"><span data-stu-id="a724d-120">**Manage certificates with partners**</span></span>  
  
-   <span data-ttu-id="a724d-121">パートナー管理に含まれる作業として、証明書の管理を行います。</span><span class="sxs-lookup"><span data-stu-id="a724d-121">Make certificate management part of your partner management practices.</span></span> <span data-ttu-id="a724d-122">BizTalk Server 環境でパーティの追加または削除を行う場合は、そのパートナーに関連付けられた証明書の追加または削除を行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a724d-122">When you add or remove a party from the BizTalk Server environment, we recommend that you add or remove the certificates associated with that partner.</span></span>  
  
 <span data-ttu-id="a724d-123">**ホスト インスタンスを削除する前に証明書を削除します。**</span><span class="sxs-lookup"><span data-stu-id="a724d-123">**Remove certificates before removing a host instance**</span></span>  
  
-   <span data-ttu-id="a724d-124">BizTalk サーバーからホスト インスタンスを削除する前に、ホスト インスタンスの実行に使用されているアカウントの個人用ストアにある証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="a724d-124">Before removing a host instance from a BizTalk server, remove the certificates in the personal store of the account under which the host instance is running.</span></span>  
  
## <a name="configure-biztalk-server-to-use-certificates-for-mimesmime"></a><span data-ttu-id="a724d-125">MIME/SMIME の証明書を使用する BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="a724d-125">Configure BizTalk Server to Use Certificates for MIME/SMIME</span></span>  
 <span data-ttu-id="a724d-126">**サービス拒否攻撃のデジタル署名用の回避します。**</span><span class="sxs-lookup"><span data-stu-id="a724d-126">**Avoid denial of service attacks for digital signatures**</span></span>  
  
-   <span data-ttu-id="a724d-127">BizTalk Server は、デジタル署名を検証できない場合に、メッセージで実行する対象を決定します。</span><span class="sxs-lookup"><span data-stu-id="a724d-127">Determine what you want to do with messages when BizTalk Server cannot validate the digital signature.</span></span> <span data-ttu-id="a724d-128">受信ポートで認証プロパティを設定すると、サービス拒否攻撃を防ぐに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a724d-128">Setting the Authentication property on the receive port will help prevent denial of service attacks.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a724d-129">認証 - メッセージの削除と認証 - 受信ポートのフラグは、パーティの解決パイプライン コンポーネントが正しく構成することと、BizTalk Server でパーティが定義されている必要があります。 メッセージの保持します。</span><span class="sxs-lookup"><span data-stu-id="a724d-129">The Authentication - Drop messages and Authentication - Keep messages flags on the receive port require that the Party Resolution pipeline component be configured correctly, and that the parties are defined in BizTalk Server.</span></span> <span data-ttu-id="a724d-130">詳細については、次を参照してください。[パーティの解決パイプライン コンポーネント](http://go.microsoft.com/fwlink/?LinkId=155146)(http://go.microsoft.com/fwlink/?LinkId=155146) で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="a724d-130">For more information, see [Party Resolution Pipeline Component](http://go.microsoft.com/fwlink/?LinkId=155146) (http://go.microsoft.com/fwlink/?LinkId=155146) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="a724d-131">**独立した作成用暗号化および暗号化されていないメッセージの受信場所**</span><span class="sxs-lookup"><span data-stu-id="a724d-131">**Create separate receive locations for encrypted and unencrypted messages**</span></span>  
  
-   <span data-ttu-id="a724d-132">パートナーから MIME 暗号化されているメッセージと暗号化されていないメッセージを受信することが予測される場合は、それぞれに対して異なるホストの異なる受信場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="a724d-132">If you plan to receive MIME-encrypted messages from some partners and unencrypted messages from other partners, create separate receive locations in different hosts for encrypted and unencrypted messages.</span></span> <span data-ttu-id="a724d-133">MIME 暗号化されたメッセージのみを行うには非 MIME メッセージを許可するオプションは [いいえ] に、MIME/SMIME デコーダ パイプライン コンポーネントで構成します。</span><span class="sxs-lookup"><span data-stu-id="a724d-133">When you expect only MIME-encrypted messages, configure the Allow Non MIME Message option in the Decode MIME/SMIME pipeline component to No.</span></span>  
  
## <a name="configure-a-biztalk-adapter-to-use-certificates"></a><span data-ttu-id="a724d-134">証明書を使用する BizTalk アダプターを構成します。</span><span class="sxs-lookup"><span data-stu-id="a724d-134">Configure a BizTalk Adapter to Use Certificates</span></span>  
 <span data-ttu-id="a724d-135">**ターゲットの Web サイトへの接続をテストします。**</span><span class="sxs-lookup"><span data-stu-id="a724d-135">**Test your connection to the target Web site**</span></span>  
  
-   <span data-ttu-id="a724d-136">SSL を使用している場合は、HTTP または SOAP トランスポートを持つターゲットの Web サイトに接続する前に、Microsoft Internet Explorer® でターゲットの Web サイトに接続できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a724d-136">If you are using SSL, ensure that you can connect to the target Web site with Microsoft Internet Explorer® before attempting to connect to the target Web site with the HTTP or SOAP transports.</span></span> <span data-ttu-id="a724d-137">ダイアログ ボックスが表示されないこと Internet Explorer でターゲットの Web サイトに接続する場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="a724d-137">Verify that no dialog boxes are displayed in Internet Explorer when you connect to the target Web site.</span></span> <span data-ttu-id="a724d-138">BizTalk Server には、ターゲットの web サイトに接続するときに表示されるダイアログ ボックスをやりとりするためのメカニズムはありません。</span><span class="sxs-lookup"><span data-stu-id="a724d-138">BizTalk Server has no mechanism for interfacing with any dialog boxes that might be displayed when connecting to the target web site.</span></span> <span data-ttu-id="a724d-139">ターゲットの Web サイト名が SSL 証明書、Web サイトに指定された名前と一致しない場合、または SSL 証明書のルート証明機関が適切な信頼されたルート証明書でない場合、Internet Explorer で、ダイアログ ボックスを表示可能性があります。機関のストア。</span><span class="sxs-lookup"><span data-stu-id="a724d-139">A dialog box may be displayed by Internet Explorer if the target Web site name does not match the name specified for the Web site in the SSL certificate or if the Root Certification Authority for the SSL certificate is not in the appropriate Trusted Root Certification Authorities store.</span></span>  
  
 <span data-ttu-id="a724d-140">**SSL 診断ツールを使用して、SSL 接続の問題を分析するには**</span><span class="sxs-lookup"><span data-stu-id="a724d-140">**Use the SSL Diagnostics tool to analyze SSL connection issues**</span></span>  
  
-   <span data-ttu-id="a724d-141">SSL 診断ツールは、IIS 診断ツールキットのオプションのコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="a724d-141">The SSL Diagnostics tool is an optional component of the IIS Diagnostics Toolkit.</span></span> <span data-ttu-id="a724d-142">IIS 診断ツールキットをダウンロードすることができます、[インターネット情報サービスの診断ツール](http://go.microsoft.com/fwlink/?LinkID=64426)ページ (http://go.microsoft.com/fwlink/?LinkID=64426)。</span><span class="sxs-lookup"><span data-stu-id="a724d-142">You can download the IIS Diagnostics Toolkit from the [Internet Information Services Diagnostics Tools](http://go.microsoft.com/fwlink/?LinkID=64426) page (http://go.microsoft.com/fwlink/?LinkID=64426).</span></span>  
  
## <a name="exporting-a-certificate-from-one-biztalk-group-to-another"></a><span data-ttu-id="a724d-143">1 つの BizTalk グループから別の証明書のエクスポート</span><span class="sxs-lookup"><span data-stu-id="a724d-143">Exporting a Certificate from One BizTalk Group to Another</span></span>  
 <span data-ttu-id="a724d-144">**本来の目的、インポートされた証明書を使用していることを確認してください。**</span><span class="sxs-lookup"><span data-stu-id="a724d-144">**Ensure that an imported certificate is being used for its intended purpose**</span></span>  
  
-   <span data-ttu-id="a724d-145">グループに証明書をインポートした場合、インポートした証明書は、意図された用途と整合性がある使用法プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="a724d-145">If you import a certificate into a group, the imported certificate must have a usage property that is consistent with its intended use.</span></span> <span data-ttu-id="a724d-146">使用法プロパティを確認するで証明書をダブルクリック、**証明書管理コンソール**インターフェイスをクリックして、**詳細**のタブ、**証明書**ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a724d-146">To check the usage property, double-click the certificate in the **Certificates Management Console** interface, and then click the **Details** tab of the **Certificate** dialog box.</span></span> <span data-ttu-id="a724d-147">をクリックして、**すべて**オプションを**表示**ドロップダウン リストをクリックし、選択、**キー使用法**や**拡張キー使用法**フィールド使用目的を確認します。</span><span class="sxs-lookup"><span data-stu-id="a724d-147">Then click the **All** option for the **Show** drop-down list, and then click to select the **Key Usage** and/or **Enhanced Key Usage** fields to verify the intended purpose.</span></span> <span data-ttu-id="a724d-148">BizTalk Server が、その使用目的以外の証明書を使用しようとしています。 ランタイム エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a724d-148">If BizTalk Server attempts to use a certificate for other than its intended purpose a runtime error will occur.</span></span>