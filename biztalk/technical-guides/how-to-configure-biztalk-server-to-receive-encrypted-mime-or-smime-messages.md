---
title: "暗号化された MIME または SMIME メッセージを受信する BizTalk Server を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d72002c8-6bd8-458f-8149-1c0c4cbbb682
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e996ea258b8f3ab1c7df2d30ed12aa0d0150b35
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-to-receive-encrypted-mime-or-smime-messages"></a><span data-ttu-id="53de6-102">暗号化された MIME または SMIME メッセージを受信する BizTalk Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="53de6-102">How to Configure BizTalk Server to Receive Encrypted MIME or SMIME Messages</span></span>
<span data-ttu-id="53de6-103">このトピックは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]暗号化 MIME/SMIME メッセージを受信する証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="53de6-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to receive encrypted MIME/SMIME messages.</span></span> <span data-ttu-id="53de6-104">以下の手順は、AS2 トランスポート経由での暗号化されたメッセージの受信の構成にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="53de6-104">The procedure below also applies to configuring the receiving of encrypted messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="53de6-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="53de6-105">Prerequisites</span></span>  
 <span data-ttu-id="53de6-106">このトピックの手順を実行する必要がありますログインする必要がのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="53de6-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-receive-encrypted-messages"></a><span data-ttu-id="53de6-107">暗号化されたメッセージを受信する BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="53de6-107">To configure BizTalk Server to receive encrypted messages</span></span>  
  
1.  <span data-ttu-id="53de6-108">次のように、暗号化されたメッセージを受信するためのパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="53de6-108">Create a pipeline to receive encrypted messages, as follows:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53de6-109">この手順に含まれるので、AS2Receive と AS2EdiReceive パイプラインを暗号化されたメッセージを受信するため、AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="53de6-109">This step is not necessary when configuring AS2 transport for receiving encrypted messages because the AS2Receive and AS2EdiReceive pipelines that are included in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] serve this function.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53de6-110">MIME/SMIME デコーダー パイプライン コンポーネントは、解読とデジタル署名の検証の両方を実行します (両方の機能を実行するように構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="53de6-110">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="53de6-111">したがって、暗号化および署名されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ受信パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="53de6-111">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="53de6-112">つまり、解読用とデジタル署名の検証用に異なるパイプラインを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="53de6-112">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
    1.  <span data-ttu-id="53de6-113">受信パイプラインを作成し、パイプラインのデコード ステージに MIME/SMIME デコーダー パイプライン コンポーネントをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="53de6-113">Create a receive pipeline and then drag the MIME/SMIME Decoder pipeline component into the Decode stage of the pipeline.</span></span>  
  
    2.  <span data-ttu-id="53de6-114">**プロパティ**ウィンドウで、MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="53de6-114">In the **Properties** window, configure the MIME/SMIME Decoder pipeline component properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="53de6-115">MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成するには、失効リストを確認プロパティを送信者がに送信されるメッセージに署名するのに使用される証明書の証明書失効リストを確認する場合はTrueに設定が含まれます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53de6-115">Configuring the MIME/SMIME Decoder pipeline component properties includes setting the Check Revocation List property to True if you want to check the certificate revocation list for the certificates that senders use for signing messages that are being sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="53de6-116">このオプションを無効にすると、コンポーネントのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="53de6-116">Disabling this option increases the performance of the component.</span></span> <span data-ttu-id="53de6-117">証明書に関連付けられている証明書失効リストは、適切な証明書サービスの Web サイトからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="53de6-117">The certificate revocation list associated with a certificate is downloaded from the appropriate certificate services Web site.</span></span> <span data-ttu-id="53de6-118">場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パイプラインでメッセージが失敗する、リモート Web サイトに接続できません。</span><span class="sxs-lookup"><span data-stu-id="53de6-118">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot connect to the remote Web site, the message fails in the pipeline.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="53de6-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="53de6-119">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="53de6-120">BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="53de6-120">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
    3.  <span data-ttu-id="53de6-121">受信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="53de6-121">Build and deploy the receive pipeline.</span></span>  
  
2.  <span data-ttu-id="53de6-122">次のように、暗号化されたメッセージを受信するため、受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="53de6-122">Configure the receive location for receiving encrypted messages, as follows:</span></span>  
  
    1.  <span data-ttu-id="53de6-123">暗号化されたメッセージを受信する受信場所を含む BizTalk アプリケーションに、受信パイプラインを含むに作成した BizTalk アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="53de6-123">Add the BizTalk assembly that you created containing the receive pipeline to the BizTalk application including the receive locations to receive encrypted messages.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="53de6-124">この手順は、AS2Receive パイプラインと AS2EdiReceive パイプラインが BizTalk EDI アプリケーションに含まれるために、暗号化されたメッセージを受信するための AS2 トランスポートを構成するときに必要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="53de6-124">This step is not necessary when configuring AS2 transport for receiving encrypted messages because the AS2Receive and AS2EdiReceive pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="53de6-125">前の手順で作成した受信パイプラインを使用して BizTalk アプリケーションで受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="53de6-125">Configure the receive locations in the BizTalk application with the receive pipeline that you created in the previous step.</span></span>  
  
3.  <span data-ttu-id="53de6-126">次のように暗号化解除証明書が、受信場所の受信ハンドラーとして使用するホストを構成します。</span><span class="sxs-lookup"><span data-stu-id="53de6-126">Configure the host used as the receive handler for the receive location with the decryption certificate, as follows:</span></span>  
  
    1.  <span data-ttu-id="53de6-127">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを右クリック、BizTalk は、暗号化されたメッセージの受信ハンドラーでホストされているし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="53de6-127">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click a BizTalk host that is the handler for receiving the encrypted messages, and then click **Properties**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="53de6-128">この手順は、AS2 トランスポートで使用できるは適用されません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="53de6-128">This procedure does not apply for AS2 transport available with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="53de6-129">BizTalk MIME デコーダーの AS2 デコーダーではないため、適用されます。</span><span class="sxs-lookup"><span data-stu-id="53de6-129">It applies for the BizTalk MIME Decoder, not the AS2 Decoder.</span></span> <span data-ttu-id="53de6-130">AS2 デコーダーは、メッセージの証明書情報に基づく証明書を決定します。</span><span class="sxs-lookup"><span data-stu-id="53de6-130">The AS2 Decoder will determine the certificate based on certificate information in the message.</span></span>  
  
    2.  <span data-ttu-id="53de6-131">**ホストのプロパティ**ダイアログ ボックスで、をクリックして**証明書**、順にクリック**参照**です。</span><span class="sxs-lookup"><span data-stu-id="53de6-131">In the **Host Properties** dialog box, click **Certificate**, and then click **Browse**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="53de6-132">上記の手順では、構成することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境だけであるため特定のホストが受信し、特定のメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="53de6-132">The above procedure enables you to configure your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment so that only certain hosts can receive and process particular messages.</span></span> <span data-ttu-id="53de6-133">メッセージのデコードおよび解読を行うに使用する証明書の拇印を持つホストを構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースには、そのホストのアプリケーションのプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="53de6-133">When you configure a host with the thumbprint of a certificate to use for message decoding and decryption, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] creates an application property for that host in the MessageBox database.</span></span> <span data-ttu-id="53de6-134">受信したメッセージをセキュリティで保護し、この拇印を使用して復号化されたが、ルーティングのみ、この拇印で構成されている他のホストにします。</span><span class="sxs-lookup"><span data-stu-id="53de6-134">Secure messages that are received and decrypted using this thumbprint are then only routed to this and other hosts that are configured with this thumbprint.</span></span>  
  
    3.  <span data-ttu-id="53de6-135">**証明書の選択** ダイアログ ボックスは、インストールした解読証明書を選択し、すべてのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="53de6-135">In the **Select Certificate** dialog box, select the decryption certificate that you installed, and then close all the dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53de6-136">参照</span><span class="sxs-lookup"><span data-stu-id="53de6-136">See Also</span></span>  
 [<span data-ttu-id="53de6-137">MIME または SMIME メッセージの証明書の構成</span><span class="sxs-lookup"><span data-stu-id="53de6-137">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)