---
title: MMC を使用してインポートされた証明書の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- decryption certificates
- certificates, decryption certificates
- certificates, signing certificates
- importing certificates
- signing certificates
- certificates, importing
ms.assetid: 64dbfbcf-6026-4c68-a93a-f483ec52deac
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7663d5df833635e557af699dd5ce5fc7de9c7d9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996123"
---
# <a name="configuring-certificates-imported-using-mmc"></a><span data-ttu-id="0c36b-102">MMC を使用してインポートされた証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-102">Configuring Certificates Imported Using MMC</span></span>
<span data-ttu-id="0c36b-103">Microsoft 管理コンソール (MMC) の証明書スナップインを使用して証明書をインポートした後は、その使用を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c36b-103">After you have imported certificates using the Certificates snap-in for the Microsoft Management Console (MMC), you must configure their use.</span></span> <span data-ttu-id="0c36b-104">そのためには、BizTalk グループ、BizTalk ホストと分離ホスト サービス アカウント、PIP (Partner Interface Processes)、取引先アグリーメント、およびパートナーを構成します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-104">This requires configuring the BizTalk Group, the BizTalk Host and Isolated Host service accounts, Partner Interface Processes (PIPs), trading partner agreements, and partners.</span></span> <span data-ttu-id="0c36b-105">次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c36b-105">You must perform the following steps:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c36b-106">CertWizard ユーティリティを使用して証明書をインポートおよび構成する場合は、これらの手動の手順を実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0c36b-106">If you use the CertWizard utility to import and configure a certificate, you do not have to perform these manual steps.</span></span>  
  
- <span data-ttu-id="0c36b-107">ホーム組織について署名証明書の使用法を構成します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-107">Configure the use of a signing certificate for the home organization.</span></span> <span data-ttu-id="0c36b-108">つまり、秘密キーを使用して、送信メッセージのホーム組織を識別します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-108">This means that you use a private key to identify the home organization in outgoing messages.</span></span> <span data-ttu-id="0c36b-109">これを行うには、BizTalk グループに対して署名証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-109">To do this, you configure the signing certificate for the BizTalk Group.</span></span>  
  
- <span data-ttu-id="0c36b-110">ホーム組織について暗号化解除証明書の使用法を構成します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-110">Configure the use of a decryption certificate for the home organization.</span></span> <span data-ttu-id="0c36b-111">つまり、パートナーの公開キーに対応する秘密キーを使用して、着信メッセージの暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-111">This means that you use a private key, which corresponds to the partner's public key, to decrypt incoming messages.</span></span> <span data-ttu-id="0c36b-112">これを行うには、BizTalk ホストと BizTalk 分離ホストのサービス アカウントごとに暗号化解除証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-112">To do this, you configure the decryption certificate for each BizTalk Host and the BizTalk Isolated Host service accounts.</span></span> <span data-ttu-id="0c36b-113">ホストと分離ホストの両方のサービス アカウントに、同じ暗号化解除証明書を入力してください。[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] では、これらに同じアカウントを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c36b-113">You must enter the same decryption certificate for both the host and isolated host service accounts, which for [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] you must set to the same account.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="0c36b-114">BizTalk ホストと BizTalk 分離ホストは、暗号化された同じ着信メッセージの暗号化を解除できるように、同じ暗号化解除証明書を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c36b-114">The BizTalk Hosts and the Isolated Host must have the same decryption certificate so that they can both decrypt the same encrypted incoming messages.</span></span> <span data-ttu-id="0c36b-115">HTTP アダプターを実行する BizTalk 分離ホストは、ホスト証明書にアクセスできないため、メッセージを受信する証明書を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c36b-115">The BizTalk Isolated Host that runs the HTTP adapter must have the certificate to receive the messages, because it does not have access to the Host certificate.</span></span> <span data-ttu-id="0c36b-116">BizTalk ホストも、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] がメッセージを受信した後でそのメッセージを処理する証明書を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c36b-116">The BizTalk Host also must have the certificate to process the messages after [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] has received them.</span></span>  
  
- <span data-ttu-id="0c36b-117">各パートナーに対して暗号化証明書および署名証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-117">Configure encryption and signing certificates for each partner.</span></span> <span data-ttu-id="0c36b-118">これを行うには、証明書を入力する、**全般**のタブ、**パートナー**プロパティ ページで、Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="0c36b-118">To do this, you enter the certificates on the **General** tab of the **Partner** properties page in the Microsoft [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span></span> <span data-ttu-id="0c36b-119">証明書には、パートナーへの送信メッセージを暗号化する公開キー暗号化証明書、および着信メッセージに記されたパートナーの ID を確認する公開キー署名証明書があります。</span><span class="sxs-lookup"><span data-stu-id="0c36b-119">These include a public-key encryption certificate to encrypt outgoing messages to a partner, and a public-key signing certificate to verify the partner's identity on incoming messages.</span></span> <span data-ttu-id="0c36b-120">詳細については、次を参照してください。[を作成または編集するパートナー](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-120">For more information, see [Creating or Editing a Partner](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md).</span></span>  
  
- <span data-ttu-id="0c36b-121">ホーム組織と取引先の間における暗号化ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-121">Configure the encryption policy between a home organization and a trading partner.</span></span> <span data-ttu-id="0c36b-122">取引先アグリーメントを構成するには、**プロトコル**のタブ、**アグリーメントのプロパティ**ページで、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="0c36b-122">To do this, you configure the trading partner agreement on the **Protocol** tab of the **Agreement Properties** page in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="0c36b-123">詳細については、次を参照してください。[を作成または編集するアグリーメント](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-123">For more information, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
### <a name="to-configure-the-signing-certificate-for-a-biztalk-group-or-the-decryption-certificate-for-a-biztalk-host"></a><span data-ttu-id="0c36b-124">BizTalk グループの署名証明書または BizTalk ホストの暗号化解除証明書を構成するには</span><span class="sxs-lookup"><span data-stu-id="0c36b-124">To configure the signing certificate for a BizTalk Group or the decryption certificate for a BizTalk Host</span></span>  
  
1. <span data-ttu-id="0c36b-125">をクリックして**開始**、 をクリックして**実行**、型**runas/user:\<サービスをホスト\>mmc**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-125">Click **Start**, click **Run**, type **runas /user:\<host service\> mmc**, and then click **OK**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0c36b-126">\<*サービスをホスト*\>、インストールしたときにホスト サービスに関連するサービスの名前を入力[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-126">For \<*host service*\>, type the name of the service that you associated with the host service when you installed [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span>  
  
2. <span data-ttu-id="0c36b-127">パスワードを入力します\<*サービスをホスト*\>、し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-127">Type the password for \<*host service*\>, and then press ENTER.</span></span>  
  
3. <span data-ttu-id="0c36b-128">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、順にクリックします[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-128">Click **Start**, point to **All Programs**, point to [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
4. <span data-ttu-id="0c36b-129">展開**証明書 - 現在のユーザー**、展開**個人**、 をクリックし、**証明書**します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-129">Expand **Certificates - Current User**, expand **Personal**, and then click **Certificates**.</span></span>  
  
5. <span data-ttu-id="0c36b-130">右側のペインで、プライベート証明書をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c36b-130">In the right pane, double-click a private certificate.</span></span>  
  
6. <span data-ttu-id="0c36b-131">証明書 ウィンドウで、上、**詳細** タブで、をクリックして**拇印**、表示ウィンドウで、16 進数の識別番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-131">In the Certificate window, on the **Details** tab, click **Thumbprint**, and then select the hexadecimal identification number in the display window.</span></span> <span data-ttu-id="0c36b-132">Ctrl + C キーを押してコピーします。</span><span class="sxs-lookup"><span data-stu-id="0c36b-132">Press CTRL+C to copy it.</span></span>  
  
7. <span data-ttu-id="0c36b-133">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-133">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
8. <span data-ttu-id="0c36b-134">BizTalk グループに対して署名証明書を構成するには右クリック**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**、] をクリックし、**プロパティ**。</span><span class="sxs-lookup"><span data-stu-id="0c36b-134">To configure the signing certificate for a BizTalk Group, right-click **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]**(Local)**, and then click **Properties**.</span></span> <span data-ttu-id="0c36b-135">右側にテキスト ボックス内をクリックして**拇印**、クリックして、テキスト ボックスに拇印番号を貼り付けるには、CTRL + V キーを押して**OK**します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-135">Click in the text box to the right of **Thumbprint**, press CTRL+V to paste the thumbprint number into the text box, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="0c36b-136">BizTalk ホストの暗号化解除証明書を構成するには、展開**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**、展開**ホスト**、するホストを右クリックして構成、およびクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0c36b-136">To configure the decryption certificate for a BizTalk Host, expand **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)] **(Local)**, expand **Hosts**, right-click the host that you want to configure, and then click **Properties**.</span></span>  
  
10. <span data-ttu-id="0c36b-137">**証明書**] タブ、[テキスト ボックスの右側に**拇印**、クリックして、テキスト ボックスに拇印番号を貼り付けるには、CTRL + V キーを押します**OK**。</span><span class="sxs-lookup"><span data-stu-id="0c36b-137">On the **Certificate** tab, click in the text box to the right of **Thumbprint**, press CTRL+V to paste the thumbprint number into the text box, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0c36b-138">暗号化解除証明書は、BizTalk ホスト (BizTalkServerApplication) と BizTalk 分離ホスト (BizTalkServerIsolatedHost) の両方に対して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c36b-138">You must configure the decrypting certificates on both the BizTalk Host (BizTalkServerApplication) and the BizTalk Isolated Host (BizTalkServerIsolatedHost).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c36b-139">参照</span><span class="sxs-lookup"><span data-stu-id="0c36b-139">See Also</span></span>  
 [<span data-ttu-id="0c36b-140">証明書の管理</span><span class="sxs-lookup"><span data-stu-id="0c36b-140">Managing Certificates</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/managing-certificates1.md)