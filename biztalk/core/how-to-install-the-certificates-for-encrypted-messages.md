---
title: "暗号化されたメッセージの証明書をインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e11fdb81-041c-4ba6-849d-d511ead0e8be
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b1df2e9e5bf42a215420dac155fafac8e92ae21
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-certificates-for-encrypted-messages"></a><span data-ttu-id="9ea26-102">暗号化されたメッセージ用の証明書をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="9ea26-102">How to Install the Certificates for Encrypted Messages</span></span>
<span data-ttu-id="9ea26-103">暗号化されたメッセージを送受信するための証明書をインストールする手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="9ea26-103">The following procedure lists the high-level steps that you have to follow to install the certificates for receiving and sending encrypted messages.</span></span>  
  
-   <span data-ttu-id="9ea26-104">解読に使用する証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="9ea26-104">To install certificates in the certificates store for decryption</span></span>  
  
-   <span data-ttu-id="9ea26-105">暗号化に使用する証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="9ea26-105">To install certificates in the certificates store for encryption</span></span>  
  
-   <span data-ttu-id="9ea26-106">暗号化されたメッセージを受信するために BizTalk ホストを構成するには</span><span class="sxs-lookup"><span data-stu-id="9ea26-106">To configure BizTalk hosts for receiving encrypted messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ea26-107">署名および解読操作の両方に 1 つの証明書を使用することも、機能ごとに 1 つの証明書を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9ea26-107">You can use one certificate for both signing and decryption operations, or you can use one certificate for each function.</span></span>  
  
### <a name="to-install-the-decryption-certificates-in-the-certificates-store"></a><span data-ttu-id="9ea26-108">解読証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="9ea26-108">To install the decryption certificates in the certificates store</span></span>  
  
1.  <span data-ttu-id="9ea26-109">組織の管理者が、使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の証明機関 (CA) に対して、暗号化用の公開キーと秘密キーのペアを要求します。</span><span class="sxs-lookup"><span data-stu-id="9ea26-109">An administrator in your organization requests a private-public key pair for encryption from the certification authority (CA) for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use.</span></span>  
  
2.  <span data-ttu-id="9ea26-110">管理者が、パートナー A に暗号化用の公開キーを送信します。</span><span class="sxs-lookup"><span data-stu-id="9ea26-110">The administrator sends the public key for encryption to Partner A.</span></span>  
  
3.  <span data-ttu-id="9ea26-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、A. をインストール パートナーからメッセージを受信するハンドラーを実行しているホスト インスタンスのサービス アカウントとしてログオン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス アカウントの個人用ストア内のメッセージを解読するための秘密キー証明書。</span><span class="sxs-lookup"><span data-stu-id="9ea26-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on as the service account for the host instance running the handler that will receive messages from Partner A. Install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] private key certificate for decrypting messages in the personal store for the service account.</span></span> <span data-ttu-id="9ea26-112">次の図に、証明書をインストールする証明書ストアを示します。</span><span class="sxs-lookup"><span data-stu-id="9ea26-112">The following figure shows the certificate store where you install the certificate.</span></span>  
  
     <span data-ttu-id="9ea26-113">![セキュリティで保護されたメッセージの受信に必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="9ea26-113">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4.  <span data-ttu-id="9ea26-114">パートナー A で、パートナー A に送信したメッセージを暗号化できるように、適切なストアに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の公開キー証明書をインストールします </span><span class="sxs-lookup"><span data-stu-id="9ea26-114">In Partner A, install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] public key certificate for encrypting messages sent to Partner A in the appropriate store.</span></span> <span data-ttu-id="9ea26-115">(パートナー A が使用されている場合[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、その他のユーザー ストアに公開キーをインストールします)。</span><span class="sxs-lookup"><span data-stu-id="9ea26-115">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the public key in the Other People store.)</span></span>  
  
### <a name="to-install-the-encryption-certificates-in-the-certificates-store"></a><span data-ttu-id="9ea26-116">暗号化証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="9ea26-116">To install the encryption certificates in the certificates store</span></span>  
  
1.  <span data-ttu-id="9ea26-117">パートナー A が、CA に対して暗号化のための公開キーと秘密キーのペアを要求します。</span><span class="sxs-lookup"><span data-stu-id="9ea26-117">Partner A requests a private-public key pair for encryption from the CA.</span></span>  
  
2.  <span data-ttu-id="9ea26-118">パートナー A が、メッセージを解読するための秘密キー証明書を適切なストアにインストールします </span><span class="sxs-lookup"><span data-stu-id="9ea26-118">Partner A installs the private key certificate for decrypting the messages in the appropriate store.</span></span> <span data-ttu-id="9ea26-119">(パートナー A が [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、"個人用証明書" ストアに秘密キーをインストールします)。</span><span class="sxs-lookup"><span data-stu-id="9ea26-119">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal certificate store.)</span></span>  
  
3.  <span data-ttu-id="9ea26-120">パートナー A に送信したメッセージの暗号化のための公開キーが、パートナー A から送信されます。</span><span class="sxs-lookup"><span data-stu-id="9ea26-120">Partner A sends you its public key for encrypting messages sent to Partner A.</span></span>  
  
4.  <span data-ttu-id="9ea26-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、パートナー A にメッセージを送信するハンドラーを実行中のホスト インスタンスがあるサーバーにログオンします。パートナー A に送信したメッセージの暗号化に使用する、パートナー A の公開キー証明書を "その他のユーザー" ストアにインストールします。</span><span class="sxs-lookup"><span data-stu-id="9ea26-121">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will send messages to Partner A. Install the Partner A public key certificate for encrypting messages sent to Partner A in the Other People store.</span></span> <span data-ttu-id="9ea26-122">次の図に、証明書をインストールする証明書ストアを示します。</span><span class="sxs-lookup"><span data-stu-id="9ea26-122">The following figure shows the certificate store where you install the certificate.</span></span>  
  
     <span data-ttu-id="9ea26-123">![セキュリティで保護されたメッセージの送信に必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span><span class="sxs-lookup"><span data-stu-id="9ea26-123">![Certificates required to send secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span></span>  
  
### <a name="to-configure-biztalk-hosts-for-receiving-encrypted-messages"></a><span data-ttu-id="9ea26-124">暗号化されたメッセージを受信するために BizTalk ホストを構成するには</span><span class="sxs-lookup"><span data-stu-id="9ea26-124">To configure BizTalk hosts for receiving encrypted messages</span></span>  
  
1.  <span data-ttu-id="9ea26-125">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="9ea26-125">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="9ea26-126">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、**プラットフォームの設定**、展開**ホスト**です。</span><span class="sxs-lookup"><span data-stu-id="9ea26-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Platform Settings**, expand **Hosts**.</span></span>  
  
    1.  <span data-ttu-id="9ea26-127">右側のウィンドウでは、暗号化されたメッセージの受信ハンドラーである BizTalk ホストを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="9ea26-127">On the right pane, right-click a BizTalk host that is the handler for receiving the encrypted messages, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="9ea26-128">**ホストのプロパティ**ダイアログ ボックスで、をクリックして**証明書**、 をクリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="9ea26-128">On the **Host Properties** dialog box, click **Certificate**, click **Browse**.</span></span>  
  
    3.  <span data-ttu-id="9ea26-129">**証明書の選択** ダイアログ ボックスが、インストールした解読証明書を選択し、すべてのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9ea26-129">On the **Select Certificate** dialog box, select the decryption certificate that you installed, and then close all of the dialog boxes.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="9ea26-130">詳細については、次を参照してください。[ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="9ea26-130">For more information, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9ea26-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="9ea26-131">Next Steps</span></span>  
 <span data-ttu-id="9ea26-132">暗号化されたメッセージを受信するためのパイプラインを作成する[暗号化されたメッセージの受信、BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="9ea26-132">You create a pipeline to receive encrypted messages in [How to Configure BizTalk Server for Receiving Encrypted Messages](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)</span></span>  
  
 <span data-ttu-id="9ea26-133">暗号化されたメッセージを送信するためのパイプラインを作成する[暗号化されたメッセージの送信の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="9ea26-133">You create a pipeline to send encrypted messages in [How to Configure BizTalk Server for Sending Encrypted Messages](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea26-134">参照</span><span class="sxs-lookup"><span data-stu-id="9ea26-134">See Also</span></span>  
 <span data-ttu-id="9ea26-135">[BizTalk Server は暗号化されたメッセージを使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9ea26-135">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 [<span data-ttu-id="9ea26-136">暗号化されたメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="9ea26-136">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)