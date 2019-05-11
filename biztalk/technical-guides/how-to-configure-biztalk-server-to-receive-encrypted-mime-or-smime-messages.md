---
title: 暗号化された MIME または SMIME メッセージを受信する BizTalk Server を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d72002c8-6bd8-458f-8149-1c0c4cbbb682
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b785e85f4d53feda47f4ebf4bf0ab34c56b830d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242624"
---
# <a name="how-to-configure-biztalk-server-to-receive-encrypted-mime-or-smime-messages"></a><span data-ttu-id="ed343-102">暗号化された MIME または SMIME メッセージを受信する BizTalk Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="ed343-102">How to Configure BizTalk Server to Receive Encrypted MIME or SMIME Messages</span></span>
<span data-ttu-id="ed343-103">このトピックでは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]証明書を使用して暗号化された MIME/SMIME メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="ed343-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to receive encrypted MIME/SMIME messages.</span></span> <span data-ttu-id="ed343-104">以下の手順は、AS2 トランスポート経由の暗号化されたメッセージの受信の構成にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="ed343-104">The procedure below also applies to configuring the receiving of encrypted messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ed343-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="ed343-105">Prerequisites</span></span>  
 <span data-ttu-id="ed343-106">このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="ed343-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-receive-encrypted-messages"></a><span data-ttu-id="ed343-107">暗号化されたメッセージを受信する BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="ed343-107">To configure BizTalk Server to receive encrypted messages</span></span>  
  
1. <span data-ttu-id="ed343-108">次のように、暗号化されたメッセージを受信するためのパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed343-108">Create a pipeline to receive encrypted messages, as follows:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ed343-109">BizTalk Server に含まれている AS2Receive と AS2EdiReceive パイプラインは、この機能を提供するために、暗号化されたメッセージを受信するための AS2 トランスポートを構成するときに、この手順は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="ed343-109">This step is not necessary when configuring AS2 transport for receiving encrypted messages because the AS2Receive and AS2EdiReceive pipelines that are included in BizTalk Server serve this function.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="ed343-110">MIME/SMIME デコーダー パイプライン コンポーネントは、解読とデジタル署名の検証の両方を実行します (両方の機能を実行するように構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="ed343-110">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="ed343-111">したがって、暗号化および署名されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ受信パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ed343-111">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="ed343-112">つまり、解読用とデジタル署名の検証用に異なるパイプラインを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ed343-112">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
   1. <span data-ttu-id="ed343-113">受信パイプラインを作成し、パイプラインのデコード ステージに MIME/SMIME デコーダー パイプライン コンポーネントをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="ed343-113">Create a receive pipeline and then drag the MIME/SMIME Decoder pipeline component into the Decode stage of the pipeline.</span></span>  
  
   2. <span data-ttu-id="ed343-114">**プロパティ**ウィンドウで、MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="ed343-114">In the **Properties** window, configure the MIME/SMIME Decoder pipeline component properties.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="ed343-115">MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成するには、失効リストを確認プロパティを送信者のに送信されるメッセージの署名に使用される証明書の証明書失効リストを確認したい場合はTrueに設定が含まれます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed343-115">Configuring the MIME/SMIME Decoder pipeline component properties includes setting the Check Revocation List property to True if you want to check the certificate revocation list for the certificates that senders use for signing messages that are being sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ed343-116">このオプションを無効にすると、コンポーネントのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="ed343-116">Disabling this option increases the performance of the component.</span></span> <span data-ttu-id="ed343-117">証明書に関連付けられている証明書失効リストは、適切な証明書サービスの Web サイトからダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="ed343-117">The certificate revocation list associated with a certificate is downloaded from the appropriate certificate services Web site.</span></span> <span data-ttu-id="ed343-118">場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]リモートの Web サイトのパイプラインでメッセージが失敗に接続できません。</span><span class="sxs-lookup"><span data-stu-id="ed343-118">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot connect to the remote Web site, the message fails in the pipeline.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="ed343-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ed343-119">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ed343-120">BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ed343-120">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
   3. <span data-ttu-id="ed343-121">受信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="ed343-121">Build and deploy the receive pipeline.</span></span>  
  
2. <span data-ttu-id="ed343-122">次のように、暗号化されたメッセージを受信するための受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="ed343-122">Configure the receive location for receiving encrypted messages, as follows:</span></span>  
  
   1. <span data-ttu-id="ed343-123">暗号化されたメッセージを受信する受信場所を含む BizTalk アプリケーションに受信パイプラインを含むに作成した BizTalk アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="ed343-123">Add the BizTalk assembly that you created containing the receive pipeline to the BizTalk application including the receive locations to receive encrypted messages.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="ed343-124">この手順は、AS2Receive と AS2EdiReceive パイプラインが BizTalk EDI アプリケーションに含まれているために、暗号化されたメッセージを受信するための AS2 トランスポートを構成するときに必要ない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ed343-124">This step is not necessary when configuring AS2 transport for receiving encrypted messages because the AS2Receive and AS2EdiReceive pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   2. <span data-ttu-id="ed343-125">BizTalk アプリケーションを前の手順で作成した受信パイプラインで受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="ed343-125">Configure the receive locations in the BizTalk application with the receive pipeline that you created in the previous step.</span></span>  
  
3. <span data-ttu-id="ed343-126">次のように復号化証明書が、受信場所の受信ハンドラーとして使用するホストを構成します。</span><span class="sxs-lookup"><span data-stu-id="ed343-126">Configure the host used as the receive handler for the receive location with the decryption certificate, as follows:</span></span>  
  
   1. <span data-ttu-id="ed343-127">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、BizTalk は、暗号化されたメッセージの受信ハンドラーでホストされている、クリックして右クリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="ed343-127">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, right-click a BizTalk host that is the handler for receiving the encrypted messages, and then click **Properties**.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="ed343-128">この手順は、AS2 トランスポートで使用できるは適用されません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ed343-128">This procedure does not apply for AS2 transport available with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ed343-129">BizTalk MIME デコーダー、AS2 デコーダーではないが適用されます。</span><span class="sxs-lookup"><span data-stu-id="ed343-129">It applies for the BizTalk MIME Decoder, not the AS2 Decoder.</span></span> <span data-ttu-id="ed343-130">AS2 デコーダーでは、メッセージ内の証明書情報に基づく証明書を決定します。</span><span class="sxs-lookup"><span data-stu-id="ed343-130">The AS2 Decoder will determine the certificate based on certificate information in the message.</span></span>  
  
   2. <span data-ttu-id="ed343-131">**ホストのプロパティ**ダイアログ ボックスで、をクリックして**証明書**、順にクリックします**参照**します。</span><span class="sxs-lookup"><span data-stu-id="ed343-131">In the **Host Properties** dialog box, click **Certificate**, and then click **Browse**.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="ed343-132">上記の手順では、構成することができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境のためだけである特定のホストは受信し、特定のメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="ed343-132">The above procedure enables you to configure your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment so that only certain hosts can receive and process particular messages.</span></span> <span data-ttu-id="ed343-133">メッセージのデコードおよび解読を行うに使用する証明書の拇印を持つホストを構成するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースでは、そのホストのアプリケーション プロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="ed343-133">When you configure a host with the thumbprint of a certificate to use for message decoding and decryption, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] creates an application property for that host in the MessageBox database.</span></span> <span data-ttu-id="ed343-134">受信したメッセージをセキュリティで保護し、この拇印を使用して復号化されたが、ルーティングのみ、この拇印で構成されている他のホストにします。</span><span class="sxs-lookup"><span data-stu-id="ed343-134">Secure messages that are received and decrypted using this thumbprint are then only routed to this and other hosts that are configured with this thumbprint.</span></span>  
  
   3. <span data-ttu-id="ed343-135">**証明書の選択**ダイアログ ボックスがインストールした解読証明書を選択し、すべてのダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ed343-135">In the **Select Certificate** dialog box, select the decryption certificate that you installed, and then close all the dialog boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed343-136">参照</span><span class="sxs-lookup"><span data-stu-id="ed343-136">See Also</span></span>  
 [<span data-ttu-id="ed343-137">MIME またはメッセージの SMIME 証明書の構成</span><span class="sxs-lookup"><span data-stu-id="ed343-137">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)