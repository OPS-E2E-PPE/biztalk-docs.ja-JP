---
title: "署名付きメッセージを受信するための BizTalk Server を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48479532-24a9-41d9-a3b8-2a23f4e76457
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 814aa3f25866f18a1d7fe536bc47a996f286916d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-for-receiving-signed-messages"></a><span data-ttu-id="08cdd-102">署名付きメッセージを受信するための BizTalk Server の構成方法</span><span class="sxs-lookup"><span data-stu-id="08cdd-102">How to Configure BizTalk Server for Receiving Signed Messages</span></span>
<span data-ttu-id="08cdd-103">次の手順では、暗号化されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成するときの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="08cdd-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted messages.</span></span>  
  
-   <span data-ttu-id="08cdd-104">署名付きメッセージを受信するためのパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="08cdd-104">To create a pipeline to receive signed messages</span></span>  
  
-   <span data-ttu-id="08cdd-105">署名付きメッセージを受信するための受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="08cdd-105">To configure the receive location for receiving signed messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="08cdd-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="08cdd-106">Prerequisites</span></span>  
 <span data-ttu-id="08cdd-107">構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s 署名付きメッセージを受信するための手順を実行する必要があります[デジタル署名の証明書をインストールする方法](../core/how-to-install-the-certificates-for-digital-signatures.md)です。</span><span class="sxs-lookup"><span data-stu-id="08cdd-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for receiving signed messages, you must perform the steps in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-receive-signed-messages"></a><span data-ttu-id="08cdd-108">署名付きメッセージを受信するためのパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="08cdd-108">To create a pipeline to receive signed messages</span></span>  
  
1.  <span data-ttu-id="08cdd-109">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="08cdd-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
    1.  <span data-ttu-id="08cdd-110">**ファイル** メニューのをクリックして**新しい項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="08cdd-110">On the **File** menu, click **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="08cdd-111">**新しい項目の追加** ダイアログ ボックスで BizTalk プロジェクトの項目を展開し、をクリックして**パイプライン ファイル**、をクリックし、**受信パイプライン**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="08cdd-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Receive Pipeline** template.</span></span>  
  
    3.  <span data-ttu-id="08cdd-112">**名前**フィールドに、パイプラインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="08cdd-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
    4.  <span data-ttu-id="08cdd-113">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="08cdd-113">Click **Add**.</span></span>  
  
         <span data-ttu-id="08cdd-114">新しいパイプラインがソリューション エクスプローラーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="08cdd-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="08cdd-115">MIME/SMIME デコーダー パイプライン コンポーネントをドラッグして、**デコード**受信パイプラインのステージ。</span><span class="sxs-lookup"><span data-stu-id="08cdd-115">Drag the MIME/SMIME Decoder pipeline component into the **Decode** stage of a receive pipeline.</span></span>  
  
     <span data-ttu-id="08cdd-116">![MIME & #47。SMIME デコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span><span class="sxs-lookup"><span data-stu-id="08cdd-116">![MIME&#47;SMIME Decoder pipeline component](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span></span>  
  
    -   <span data-ttu-id="08cdd-117">MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成、**プロパティ**ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="08cdd-117">Configure the MIME/SMIME Decoder pipeline component properties in the **Properties** window.</span></span> <span data-ttu-id="08cdd-118">MIME/SMIME デコーダーの詳細については、次を参照してください。 [- MIME/SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="08cdd-118">For more information about the MIME/SMIME decoder, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="08cdd-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="08cdd-119">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="08cdd-120">BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="08cdd-120">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span> <span data-ttu-id="08cdd-121">詳細については、次を参照してください。[受信場所のインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="08cdd-121">For more information, see [How to Configure Per-instance Pipeline Properties for a Receive Location](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="08cdd-122">MIME/SMIME デコーダー パイプライン コンポーネントは、解読とデジタル署名の検証の両方を実行します (両方の機能を実行するように構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="08cdd-122">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="08cdd-123">したがって、暗号化および署名されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ受信パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="08cdd-123">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="08cdd-124">つまり、解読用とデジタル署名の検証用に異なるパイプラインを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="08cdd-124">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
3.  <span data-ttu-id="08cdd-125">受信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="08cdd-125">Build and deploy the receive pipeline.</span></span>  
  
### <a name="to-configure-the-receive-location-for-receiving-signed-messages"></a><span data-ttu-id="08cdd-126">署名付きメッセージを受信するための受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="08cdd-126">To configure the receive location for receiving signed messages</span></span>  
  
1.  <span data-ttu-id="08cdd-127">前の手順で作成した BizTalk アセンブリを、署名付きメッセージの受信場所を含む BizTalk アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="08cdd-127">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to receive signed messages.</span></span> <span data-ttu-id="08cdd-128">BizTalk アセンブリを追加する方法の詳細については、次を参照してください。 [BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="08cdd-128">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="08cdd-129">前の手順で作成した受信パイプラインを使用して、BizTalk アプリケーションの受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="08cdd-129">Configure the receive locations in the BizTalk Application with the receive pipeline that you created in previous procedure.</span></span> <span data-ttu-id="08cdd-130">受信場所の構成方法の詳細についてを参照してください[受信場所のプロパティを編集する方法](../core/how-to-edit-the-properties-of-a-receive-location.md)です。</span><span class="sxs-lookup"><span data-stu-id="08cdd-130">For more information about how to configure receive locations, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08cdd-131">参照</span><span class="sxs-lookup"><span data-stu-id="08cdd-131">See Also</span></span>  
 <span data-ttu-id="08cdd-132">[BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="08cdd-132">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="08cdd-133">[署名付きメッセージを送信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="08cdd-133">[How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md) </span></span>  
 <span data-ttu-id="08cdd-134">[メッセージの送信者の認証](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="08cdd-134">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="08cdd-135">署名付きメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="08cdd-135">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)