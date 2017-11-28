---
title: "デジタル署名の証明書をインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 910ccd84-c022-46a5-a9de-b99046a480b8
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a755e59c7c916f3abe037513ddbc9e2a89892fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-certificates-for-digital-signatures"></a><span data-ttu-id="84523-102">デジタル署名用の証明書をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="84523-102">How to install the Certificates for Digital Signatures</span></span>
<span data-ttu-id="84523-103">署名付きのメッセージを送受信するための証明書をインストールする手順の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="84523-103">The following procedure lists the high-level steps that you have to follow to install the certificates for receiving and sending signed messages.</span></span>  
  
-   <span data-ttu-id="84523-104">署名付きメッセージを受信するための証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="84523-104">To install the certificates in the certificates store to receive signed messages</span></span>  
  
-   <span data-ttu-id="84523-105">署名付きメッセージを送信するための署名証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="84523-105">To install the signing certificates for sending signed messages in the certificates store</span></span>  
  
-   <span data-ttu-id="84523-106">署名付きメッセージを送信できるように BizTalk グループを構成するには</span><span class="sxs-lookup"><span data-stu-id="84523-106">To configure the BizTalk Group for sending signed messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84523-107">署名および解読操作の両方に 1 つの証明書を使用することも、機能ごとに 1 つの証明書を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="84523-107">You can use one certificate for both signing and decryption operations, or you can use one certificate for each function.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="84523-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がすべての送信メッセージの署名に使用する署名証明書は 1 つだけ指定できます。</span><span class="sxs-lookup"><span data-stu-id="84523-108">You can only specify one signing certificate with which [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] signs all outbound messages.</span></span> <span data-ttu-id="84523-109">つまり、メッセージの送信先によって異なる署名証明書を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="84523-109">In other words, you cannot use different signing certificates depending on who you are sending the message to.</span></span>  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a><span data-ttu-id="84523-110">署名付きメッセージを受信するための証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="84523-110">To install the certificates in the certificates store to receive signed messages</span></span>  
  
1.  <span data-ttu-id="84523-111">パートナー A は、証明機関 (CA) にデジタル署名用の公開キーと秘密キーのペアを要求します。</span><span class="sxs-lookup"><span data-stu-id="84523-111">Partner A requests a private-public key pair for digital signatures from the certification authority (CA).</span></span>  
  
2.  <span data-ttu-id="84523-112">パートナー A は、ユーザーにデジタル署名用の公開キーを送信します。</span><span class="sxs-lookup"><span data-stu-id="84523-112">Partner A sends you its public key for digital signatures.</span></span>  
  
3.  <span data-ttu-id="84523-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、パートナー A からのメッセージを受信するハンドラーを実行中のホスト インスタンスを含むサーバーにログオンします。パートナー A の公開キー証明書をインストールして、"その他のユーザー" ストアの署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="84523-113">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will receive messages from Partner A. Install the Partner A public key certificate to verify their signature in the Other People store.</span></span> <span data-ttu-id="84523-114">次の図に、証明書をインストールする証明書ストアを示します。</span><span class="sxs-lookup"><span data-stu-id="84523-114">The following figure shows the certificate store where you install the certificate.</span></span>  
  
     <span data-ttu-id="84523-115">![セキュリティで保護されたメッセージの受信に必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="84523-115">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4.  <span data-ttu-id="84523-116">パートナー A で、適切なストアでメッセージに署名するためにパートナー A の秘密キー証明書をインストールします </span><span class="sxs-lookup"><span data-stu-id="84523-116">In Partner A, install the Partner A private key certificate for signing messages in the appropriate store.</span></span> <span data-ttu-id="84523-117">(パートナー A が [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に送信されるメッセージに署名するアカウントの個人用ストアに秘密キーをインストールします)。</span><span class="sxs-lookup"><span data-stu-id="84523-117">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal store for the account that will sign messages sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
### <a name="to-install-the-signing-certificates-for-sending-signed-messages-in-the-certificates-store"></a><span data-ttu-id="84523-118">署名付きメッセージを送信するための署名証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="84523-118">To install the signing certificates for sending signed messages in the certificates store</span></span>  
  
1.  <span data-ttu-id="84523-119">組織の管理者は、使用する [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の CA に対してデジタル署名用の公開キーと秘密キーのペアを要求します。</span><span class="sxs-lookup"><span data-stu-id="84523-119">An administrator in your organization requests a private-public key pair for digital signatures from the CA for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use.</span></span>  
  
2.  <span data-ttu-id="84523-120">管理者はパートナー A (および他のすべてのパートナー) に、デジタル署名用の公開キーを送信します。</span><span class="sxs-lookup"><span data-stu-id="84523-120">The administrator sends Partner A (and all other partners) the public key for digital signatures.</span></span>  
  
3.  <span data-ttu-id="84523-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、パートナー A にメッセージを送信するハンドラーを実行中のホスト インスタンスのサービス アカウントとしてログオンします。サービス アカウントの個人用ストアでメッセージに署名するための [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 秘密キー証明書をインストールします。</span><span class="sxs-lookup"><span data-stu-id="84523-121">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on as service account for the host instance running the handler that will send messages to Partner A. Install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] private key certificate for signing messages in the personal store for the service account.</span></span> <span data-ttu-id="84523-122">次の図に、証明書をインストールする証明書ストアを示します。</span><span class="sxs-lookup"><span data-stu-id="84523-122">The following figure shows the certificate store where you install the certificate.</span></span>  
  
     <span data-ttu-id="84523-123">![セキュリティで保護されたメッセージの送信に必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span><span class="sxs-lookup"><span data-stu-id="84523-123">![Certificates required to send secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span></span>  
  
4.  <span data-ttu-id="84523-124">パートナー A で、適切なストアでデジタル署名を検証するために、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の公開キー証明書をインストールします</span><span class="sxs-lookup"><span data-stu-id="84523-124">In Partner A, install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] public key certificate for verifying its digital signature in the appropriate store.</span></span> <span data-ttu-id="84523-125">(パートナー A が [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] を使用している場合は、"その他のユーザー" ストアに公開キーをインストールします)。</span><span class="sxs-lookup"><span data-stu-id="84523-125">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the public key in the Other people store.)</span></span>  
  
### <a name="to-configure-the-biztalk-group-for-sending-signed-messages"></a><span data-ttu-id="84523-126">署名付きメッセージを送信できるように BizTalk グループを構成するには</span><span class="sxs-lookup"><span data-stu-id="84523-126">To configure the BizTalk Group for sending signed messages</span></span>  
  
1.  <span data-ttu-id="84523-127">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="84523-127">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="84523-128">右クリック**BizTalk グループ**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="84523-128">Right-click **BizTalk Group**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="84523-129">**グループのプロパティ**ダイアログ ボックスで、をクリックして**証明書**、 をクリックして**参照**です。</span><span class="sxs-lookup"><span data-stu-id="84523-129">On the **Group Properties** dialog box, click **Certificate**, click **Browse**.</span></span>  
  
4.  <span data-ttu-id="84523-130">**証明書の選択**ダイアログ ボックスは、インストールした署名証明書を選択し、すべてのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="84523-130">On the **Select Certificate** dialog box, select the signing certificate that you installed, and then close all of the dialog boxes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="84523-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="84523-131">Next Steps</span></span>  
 <span data-ttu-id="84523-132">署名付きメッセージを受信するためのパイプラインを作成する[署名付きメッセージの受信、BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="84523-132">You create a pipeline to receive signed messages in [How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).</span></span>  
  
 <span data-ttu-id="84523-133">署名付きメッセージを送信するためのパイプラインを作成する[署名付きメッセージを送信する、BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="84523-133">You create a pipeline to send signed messages in [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84523-134">参照</span><span class="sxs-lookup"><span data-stu-id="84523-134">See Also</span></span>  
 <span data-ttu-id="84523-135">[BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="84523-135">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 [<span data-ttu-id="84523-136">署名付きメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="84523-136">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)