---
title: BizTalk Server パーティの解決を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ac330b9-3498-4c98-a6e8-d2c02cd641dd
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9d7a21b4edf5df4bd903763bcb3d1a8a8c6e1ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250090"
---
# <a name="how-to-configure-biztalk-server-for-party-resolution"></a><span data-ttu-id="8fd57-102">パーティの解決用に BizTalk Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="8fd57-102">How to Configure BizTalk Server for Party Resolution</span></span>
<span data-ttu-id="8fd57-103">次の手順では、パーティの解決用に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成するときの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fd57-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for party resolution.</span></span>  
  
-   <span data-ttu-id="8fd57-104">署名付きメッセージを受信するための証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="8fd57-104">To install the certificates in the certificates store to receive signed messages</span></span>  
  
-   <span data-ttu-id="8fd57-105">パートナーを表すパーティを作成するには</span><span class="sxs-lookup"><span data-stu-id="8fd57-105">To create a party to represent your partner</span></span>  
  
-   <span data-ttu-id="8fd57-106">証明書を使用してパーティの解決用のパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="8fd57-106">To create a pipeline for party resolution using certificates</span></span>  
  
-   <span data-ttu-id="8fd57-107">証明書を使用してパーティの解決の受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="8fd57-107">To configure the receive location for party resolution using certificates</span></span>  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a><span data-ttu-id="8fd57-108">署名付きメッセージを受信するための証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="8fd57-108">To install the certificates in the certificates store to receive signed messages</span></span>  
  
1.  <span data-ttu-id="8fd57-109">パートナー A は、証明機関 (CA) にデジタル署名用の公開キーと秘密キーのペアを要求します。</span><span class="sxs-lookup"><span data-stu-id="8fd57-109">Partner A requests a private-public key pair for digital signatures from the certification authority (CA).</span></span>  
  
2.  <span data-ttu-id="8fd57-110">パートナー A は、ユーザーにデジタル署名用の公開キーを送信します。</span><span class="sxs-lookup"><span data-stu-id="8fd57-110">Partner A sends you its public key for digital signatures.</span></span>  
  
3.  <span data-ttu-id="8fd57-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、パートナー A からのメッセージを受信するハンドラーを実行中のホスト インスタンスを含むサーバーにログオンします。パートナー A の公開キー証明書をインストールして、"その他のユーザー" ストアの署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="8fd57-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will receive messages from Partner A. Install the Partner A public key certificate to verify their signature in the Other People store.</span></span> <span data-ttu-id="8fd57-112">次の図に、証明書をインストールする証明書ストアを示します。</span><span class="sxs-lookup"><span data-stu-id="8fd57-112">The following figure shows the certificate store where you install the certificate.</span></span>  
  
     <span data-ttu-id="8fd57-113">![セキュリティで保護されたメッセージの受信に必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="8fd57-113">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4.  <span data-ttu-id="8fd57-114">パートナー A で、適切なストアでメッセージに署名するためにパートナー A の秘密キー証明書をインストールします </span><span class="sxs-lookup"><span data-stu-id="8fd57-114">In Partner A, install the Partner A private key certificate for signing messages in the appropriate store.</span></span> <span data-ttu-id="8fd57-115">(パートナー A が使用されている場合[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、または[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]に送信されるメッセージに署名するアカウントの個人用ストアに秘密キーをインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="8fd57-115">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], or [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal store for the account that will sign messages sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8fd57-116">この手順は署名付きメッセージを受信する証明書ストアに証明書のインストール"するには」の手順とまったく同じで[デジタル署名の証明書をインストールする方法](../core/how-to-install-the-certificates-for-digital-signatures.md)です。</span><span class="sxs-lookup"><span data-stu-id="8fd57-116">This step is exactly same as the step "To install the certificates in the certificates store to receive signed messages" in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span>  
  
### <a name="to-create-a-party-to-represent-your-partner"></a><span data-ttu-id="8fd57-117">パートナーを表すパーティを作成するには</span><span class="sxs-lookup"><span data-stu-id="8fd57-117">To create a party to represent your partner</span></span>  
  
1.  <span data-ttu-id="8fd57-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、パーティを A. のパートナーの作成パーティを作成する方法の詳細については、次を参照してください。[パーティを作成する方法](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)です。</span><span class="sxs-lookup"><span data-stu-id="8fd57-118">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a party for the Partner A. For more information about how to create a Party, see [How to Create a Party](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span></span>  
  
2.  <span data-ttu-id="8fd57-119">**証明書**プロパティ、署名証明書を使用してこのパーティでは、パートナー A. を識別する公開キーの選択</span><span class="sxs-lookup"><span data-stu-id="8fd57-119">In the **Certificates** properties, select the public key signing certificate to use to identify this party, Partner A.</span></span>  
  
### <a name="to-create-a-pipeline-for-party-resolution-using-certificates"></a><span data-ttu-id="8fd57-120">証明書を使用してパーティの解決用のパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="8fd57-120">To create a pipeline for party resolution using certificates</span></span>  
  
1.  <span data-ttu-id="8fd57-121">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="8fd57-121">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
    1.  <span data-ttu-id="8fd57-122">**ファイル** メニューのをクリックして**新しい項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="8fd57-122">On the **File** menu, click **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="8fd57-123">**新しい項目の追加** ダイアログ ボックスで BizTalk プロジェクトの項目を展開し、をクリックして**パイプライン ファイル**、をクリックし、**受信パイプライン**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="8fd57-123">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Receive Pipeline** template.</span></span>  
  
    3.  <span data-ttu-id="8fd57-124">**名前**フィールドに、パイプラインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8fd57-124">In the **Name** field, type a name for the pipeline.</span></span>  
  
    4.  <span data-ttu-id="8fd57-125">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fd57-125">Click **Add**.</span></span>  
  
         <span data-ttu-id="8fd57-126">新しいパイプラインがソリューション エクスプローラーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fd57-126">The new pipeline appears in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="8fd57-127">MIME/SMIME デコーダー パイプライン コンポーネントをドラッグして、**デコード**受信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="8fd57-127">Drag the MIME/SMIME Decoder pipeline component into the **Decode** stage of a receive pipeline.</span></span>  
  
     <span data-ttu-id="8fd57-128">![MIME & #47。SMIME デコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span><span class="sxs-lookup"><span data-stu-id="8fd57-128">![MIME&#47;SMIME Decoder pipeline component](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span></span>  
  
    -   <span data-ttu-id="8fd57-129">MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="8fd57-129">Configure the MIME/SMIME Decoder pipeline component properties in the **Properties** window.</span></span> <span data-ttu-id="8fd57-130">MIME/SMIME デコーダーの詳細については、次を参照してください。 [- MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="8fd57-130">For more information about the MIME/SMIME decoder, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8fd57-131">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8fd57-131">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="8fd57-132">BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8fd57-132">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span> <span data-ttu-id="8fd57-133">詳細については、次を参照してください。[受信場所のインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="8fd57-133">For more information, see [How to Configure Per-instance Pipeline Properties for a Receive Location](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8fd57-134">MIME/SMIME デコーダー パイプライン コンポーネントは、解読とデジタル署名の検証の両方を実行します (両方の機能を実行するように構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="8fd57-134">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="8fd57-135">したがって、暗号化および署名されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ受信パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fd57-135">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="8fd57-136">つまり、解読用とデジタル署名の検証用に異なるパイプラインを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8fd57-136">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
3.  <span data-ttu-id="8fd57-137">パーティの解決パイプライン コンポーネントをドラッグして、**パーティの解決**受信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="8fd57-137">Drag the Party Resolution pipeline component into the **ResolveParty** stage of a receive pipeline.</span></span> <span data-ttu-id="8fd57-138">パーティの解決パイプライン コンポーネントの詳細については、次を参照してください。[パーティの解決パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-party-resolution-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="8fd57-138">For more information about the Party Resolution pipeline component, see [How to Configure the Party Resolution Pipeline Component](../core/how-to-configure-the-party-resolution-pipeline-component.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8fd57-139">新しい受信パイプラインを作成する代わりに、既定の XMLReceive パイプラインを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8fd57-139">You can also use the default XMLReceive pipeline instead of creating a new receive pipeline.</span></span> <span data-ttu-id="8fd57-140">XMLReceive パイプラインには、証明書のサブジェクトをパーティ ID を解決するパーティの解決コンポーネントが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8fd57-140">The XMLReceive pipeline runs the Party Resolution component, which resolves the certificate subject to the party ID.</span></span> <span data-ttu-id="8fd57-141">XMLReceive パイプラインが空のデコード ステージ、したがって暗号化されたメッセージの受信やデジタル署名の検証に使用することはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8fd57-141">Note that the XMLReceive pipeline has an empty Decode stage, and therefore you cannot use it for receiving encrypted messages or verifying digital signatures.</span></span>  
  
    -   <span data-ttu-id="8fd57-142">[プロパティ] ウィンドウで、パーティの解決パイプライン プロパティを構成する**証明書によるパーティの解決**に`True`です。</span><span class="sxs-lookup"><span data-stu-id="8fd57-142">In the Properties window, configure the Party Resolution pipeline property **Resolve party by certificate** to `True`.</span></span>  
  
4.  <span data-ttu-id="8fd57-143">受信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="8fd57-143">Build and deploy the receive pipeline.</span></span>  
  
### <a name="to-configure-the-receive-location-for-party-resolution-using-certificates"></a><span data-ttu-id="8fd57-144">証明書を使用してパーティの解決の受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="8fd57-144">To configure the receive location for party resolution using certificates</span></span>  
  
1.  <span data-ttu-id="8fd57-145">前の手順で作成した BizTalk アセンブリを、署名付きメッセージの受信場所を含む BizTalk アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="8fd57-145">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to receive signed messages.</span></span> <span data-ttu-id="8fd57-146">BizTalk アセンブリを追加する方法の詳細については、次を参照してください。 [BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="8fd57-146">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="8fd57-147">前の手順で作成した受信パイプラインを使用して、BizTalk アプリケーションの受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="8fd57-147">Configure the receive locations in the BizTalk Application with the receive pipeline that you created in previous procedure.</span></span> <span data-ttu-id="8fd57-148">受信場所の構成方法の詳細についてを参照してください[受信場所のプロパティを編集する方法](../core/how-to-edit-the-properties-of-a-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="8fd57-148">For more information about how to configure receive locations, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd57-149">参照</span><span class="sxs-lookup"><span data-stu-id="8fd57-149">See Also</span></span>  
 <span data-ttu-id="8fd57-150">[署名付きメッセージを受信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8fd57-150">[How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span></span>  
 <span data-ttu-id="8fd57-151">[BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8fd57-151">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="8fd57-152">[受信メッセージの認証](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="8fd57-152">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 [<span data-ttu-id="8fd57-153">パーティの解決の証明書の使用</span><span class="sxs-lookup"><span data-stu-id="8fd57-153">Using Certificates for Party Resolution</span></span>](../core/using-certificates-for-party-resolution.md)