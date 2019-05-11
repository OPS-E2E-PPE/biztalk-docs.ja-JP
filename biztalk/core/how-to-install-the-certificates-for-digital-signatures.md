---
title: デジタル署名用証明書をインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 910ccd84-c022-46a5-a9de-b99046a480b8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bec4fd58532201efc430855464a90f03a824400
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384906"
---
# <a name="how-to-install-the-certificates-for-digital-signatures"></a><span data-ttu-id="416a1-102">デジタル署名用証明書をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="416a1-102">How to install the Certificates for Digital Signatures</span></span>
<span data-ttu-id="416a1-103">次の手順では、署名付きメッセージの送受信用の証明書をインストールするために従う必要のある手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="416a1-103">The following procedure lists the high-level steps that you have to follow to install the certificates for receiving and sending signed messages.</span></span>  
  
-   <span data-ttu-id="416a1-104">署名付きメッセージを受信するための証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="416a1-104">To install the certificates in the certificates store to receive signed messages</span></span>  
  
-   <span data-ttu-id="416a1-105">証明書ストアに署名付きメッセージを送信するための署名証明書をインストールするには</span><span class="sxs-lookup"><span data-stu-id="416a1-105">To install the signing certificates for sending signed messages in the certificates store</span></span>  
  
-   <span data-ttu-id="416a1-106">署名付きメッセージを送信するための BizTalk グループを構成するには</span><span class="sxs-lookup"><span data-stu-id="416a1-106">To configure the BizTalk Group for sending signed messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="416a1-107">署名および解読操作の両方に 1 つの証明書を使用することも、機能ごとに 1 つの証明書を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="416a1-107">You can use one certificate for both signing and decryption operations, or you can use one certificate for each function.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="416a1-108">1 つの署名証明書を指定できますのみ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]すべての送信メッセージに署名します。</span><span class="sxs-lookup"><span data-stu-id="416a1-108">You can only specify one signing certificate with which [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] signs all outbound messages.</span></span> <span data-ttu-id="416a1-109">つまりにメッセージを送信するユーザーによって別の署名証明書を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="416a1-109">In other words, you cannot use different signing certificates depending on who you are sending the message to.</span></span>  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a><span data-ttu-id="416a1-110">署名付きメッセージを受信するための証明書を証明書ストアにインストールするには</span><span class="sxs-lookup"><span data-stu-id="416a1-110">To install the certificates in the certificates store to receive signed messages</span></span>  
  
1. <span data-ttu-id="416a1-111">パートナー A は、証明機関 (CA) にデジタル署名用の公開キーと秘密キーのペアを要求します。</span><span class="sxs-lookup"><span data-stu-id="416a1-111">Partner A requests a private-public key pair for digital signatures from the certification authority (CA).</span></span>  
  
2. <span data-ttu-id="416a1-112">パートナー A は、ユーザーにデジタル署名用の公開キーを送信します。</span><span class="sxs-lookup"><span data-stu-id="416a1-112">Partner A sends you its public key for digital signatures.</span></span>  
  
3. <span data-ttu-id="416a1-113">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、パートナー A からのメッセージを受信するハンドラーを実行中のホスト インスタンスを含むサーバーにログオンします。パートナー A の公開キー証明書をインストールして、"その他のユーザー" ストアの署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="416a1-113">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will receive messages from Partner A. Install the Partner A public key certificate to verify their signature in the Other People store.</span></span> <span data-ttu-id="416a1-114">次の図に、証明書をインストールする証明書ストアを示します。</span><span class="sxs-lookup"><span data-stu-id="416a1-114">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="416a1-115">![セキュリティで保護されたメッセージを受信するために必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="416a1-115">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4. <span data-ttu-id="416a1-116">パートナー A で、適切なストアでメッセージに署名するためにパートナー A の秘密キー証明書をインストールします </span><span class="sxs-lookup"><span data-stu-id="416a1-116">In Partner A, install the Partner A private key certificate for signing messages in the appropriate store.</span></span> <span data-ttu-id="416a1-117">(パートナー A が使用されている場合[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]に送信されるメッセージに署名するアカウントの個人用ストアに秘密キーをインストール[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。</span><span class="sxs-lookup"><span data-stu-id="416a1-117">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal store for the account that will sign messages sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
### <a name="to-install-the-signing-certificates-for-sending-signed-messages-in-the-certificates-store"></a><span data-ttu-id="416a1-118">証明書ストアに署名付きメッセージを送信するための署名証明書をインストールするには</span><span class="sxs-lookup"><span data-stu-id="416a1-118">To install the signing certificates for sending signed messages in the certificates store</span></span>  
  
1. <span data-ttu-id="416a1-119">組織の管理者の CA に対してデジタル署名用の/秘密キー ペアを要求する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を使用します。</span><span class="sxs-lookup"><span data-stu-id="416a1-119">An administrator in your organization requests a private-public key pair for digital signatures from the CA for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use.</span></span>  
  
2. <span data-ttu-id="416a1-120">管理者は、パートナー A (およびその他のすべてのパートナー) にもデジタル署名の公開キーを送信します。</span><span class="sxs-lookup"><span data-stu-id="416a1-120">The administrator sends Partner A (and all other partners) the public key for digital signatures.</span></span>  
  
3. <span data-ttu-id="416a1-121">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、A. をインストール パートナーにメッセージを送信するハンドラーを実行するホスト インスタンスのサービス アカウントとしてログオン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービス アカウントの個人用ストア内のメッセージに署名するための秘密キー証明書。</span><span class="sxs-lookup"><span data-stu-id="416a1-121">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on as service account for the host instance running the handler that will send messages to Partner A. Install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] private key certificate for signing messages in the personal store for the service account.</span></span> <span data-ttu-id="416a1-122">次の図に、証明書をインストールする証明書ストアを示します。</span><span class="sxs-lookup"><span data-stu-id="416a1-122">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="416a1-123">![セキュリティで保護されたメッセージを送信するために必要な証明書](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span><span class="sxs-lookup"><span data-stu-id="416a1-123">![Certificates required to send secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span></span>  
  
4. <span data-ttu-id="416a1-124">パートナー A では、インストール、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]適切なストアでデジタル署名を検証するための公開キー証明書。</span><span class="sxs-lookup"><span data-stu-id="416a1-124">In Partner A, install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] public key certificate for verifying its digital signature in the appropriate store.</span></span> <span data-ttu-id="416a1-125">(パートナー A が使用されている場合[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、他のユーザー ストアで公開キーをインストールします)。</span><span class="sxs-lookup"><span data-stu-id="416a1-125">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the public key in the Other people store.)</span></span>  
  
### <a name="to-configure-the-biztalk-group-for-sending-signed-messages"></a><span data-ttu-id="416a1-126">署名付きメッセージを送信するための BizTalk グループを構成するには</span><span class="sxs-lookup"><span data-stu-id="416a1-126">To configure the BizTalk Group for sending signed messages</span></span>  
  
1. <span data-ttu-id="416a1-127">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="416a1-127">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="416a1-128">右クリック**BizTalk グループ**、 をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="416a1-128">Right-click **BizTalk Group**, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="416a1-129">**グループのプロパティ**ダイアログ ボックスで、をクリックして**証明書**、 をクリックして**参照**します。</span><span class="sxs-lookup"><span data-stu-id="416a1-129">On the **Group Properties** dialog box, click **Certificate**, click **Browse**.</span></span>  
  
4. <span data-ttu-id="416a1-130">**証明書の選択**ダイアログ ボックスがインストールした署名証明書を選択し、すべてのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="416a1-130">On the **Select Certificate** dialog box, select the signing certificate that you installed, and then close all of the dialog boxes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="416a1-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="416a1-131">Next Steps</span></span>  
 <span data-ttu-id="416a1-132">署名付きメッセージを受信するためのパイプラインを作成する[署名付きメッセージの受信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="416a1-132">You create a pipeline to receive signed messages in [How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).</span></span>  
  
 <span data-ttu-id="416a1-133">署名付きメッセージを送信するためのパイプラインを作成する[署名付きメッセージの送信用の BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="416a1-133">You create a pipeline to send signed messages in [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="416a1-134">参照</span><span class="sxs-lookup"><span data-stu-id="416a1-134">See Also</span></span>  
 <span data-ttu-id="416a1-135">[BizTalk Server は、署名付きメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="416a1-135">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 [<span data-ttu-id="416a1-136">署名付きメッセージの送受信</span><span class="sxs-lookup"><span data-stu-id="416a1-136">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)