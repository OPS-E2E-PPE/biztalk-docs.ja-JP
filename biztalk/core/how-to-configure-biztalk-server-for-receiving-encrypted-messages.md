---
title: 暗号化されたメッセージを受信するための BizTalk Server を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd1e7e4c-f80c-468e-aa86-7c18406feead
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 551e661faf9d9b1bd9313af4afab3791ca143e3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386292"
---
# <a name="how-to-configure-biztalk-server-for-receiving-encrypted-messages"></a><span data-ttu-id="86977-102">暗号化されたメッセージを受信するための BizTalk Server の構成方法</span><span class="sxs-lookup"><span data-stu-id="86977-102">How to Configure BizTalk Server for Receiving Encrypted Messages</span></span>
<span data-ttu-id="86977-103">次の手順では、暗号化されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成するときの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="86977-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted messages.</span></span>  
  
-   <span data-ttu-id="86977-104">暗号化されたメッセージを受信するためのパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="86977-104">To create a pipeline to receive encrypted messages</span></span>  
  
-   <span data-ttu-id="86977-105">暗号化されたメッセージを受信するための受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="86977-105">To configure the receive location for receiving encrypted messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="86977-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="86977-106">Prerequisites</span></span>  
 <span data-ttu-id="86977-107">構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]暗号化されたメッセージを受信するためで手順を実行する必要があります[メッセージの暗号化の証明書をインストールする方法](../core/how-to-install-the-certificates-for-encrypted-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="86977-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for receiving encrypted messages, you must perform the steps in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-receive-encrypted-messages"></a><span data-ttu-id="86977-108">暗号化されたメッセージを受信するためのパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="86977-108">To create a pipeline to receive encrypted messages</span></span>  
  
1. <span data-ttu-id="86977-109">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="86977-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
   1.  <span data-ttu-id="86977-110">**ファイル** メニューのをクリックして**新しい項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="86977-110">On the **File** menu, click **Add New Item**.</span></span>  
  
   2.  <span data-ttu-id="86977-111">**新しい項目の追加** ダイアログ ボックスで、BizTalk プロジェクトの項目を展開し、**パイプライン ファイル**、 をクリックし、**受信パイプライン**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="86977-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Receive Pipeline** template.</span></span>  
  
   3.  <span data-ttu-id="86977-112">**名前**フィールドに、パイプラインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="86977-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
   4.  <span data-ttu-id="86977-113">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="86977-113">Click **Add**.</span></span>  
  
        <span data-ttu-id="86977-114">新しいパイプラインがソリューション エクスプローラーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="86977-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="86977-115">MIME/SMIME デコーダー パイプライン コンポーネントを受信パイプラインのデコード ステージにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="86977-115">Drag the MIME/SMIME Decoder pipeline component into the Decode stage of a receive pipeline.</span></span>  
  
    <span data-ttu-id="86977-116">![MIME&#47;SMIME デコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span><span class="sxs-lookup"><span data-stu-id="86977-116">![MIME&#47;SMIME Decoder pipeline component](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span></span>  
  
   -   <span data-ttu-id="86977-117">MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成、**プロパティ**ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="86977-117">Configure the MIME/SMIME Decoder pipeline component properties in the **Properties** window.</span></span> <span data-ttu-id="86977-118">MIME/SMIME デコーダーの詳細については、次を参照してください。 [MIME-SMIME デコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)します。</span><span class="sxs-lookup"><span data-stu-id="86977-118">For more information about the MIME/SMIME decoder, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="86977-119">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="86977-119">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="86977-120">BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="86977-120">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span> <span data-ttu-id="86977-121">詳細については、次を参照してください。[受信場所のインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="86977-121">For more information, see [How to Configure Per-instance Pipeline Properties for a Receive Location](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="86977-122">MIME/SMIME デコーダー パイプライン コンポーネントは、解読とデジタル署名の検証の両方を実行します (両方の機能を実行するように構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="86977-122">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="86977-123">したがって、暗号化および署名されたメッセージを受信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ受信パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="86977-123">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="86977-124">つまり、解読用とデジタル署名の検証用に異なるパイプラインを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="86977-124">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
3. <span data-ttu-id="86977-125">受信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="86977-125">Build and deploy the receive pipeline.</span></span>  
  
### <a name="to-configure-the-receive-location-for-receiving-encrypted-messages"></a><span data-ttu-id="86977-126">暗号化されたメッセージを受信するための受信場所を構成するには</span><span class="sxs-lookup"><span data-stu-id="86977-126">To configure the receive location for receiving encrypted messages</span></span>  
  
1.  <span data-ttu-id="86977-127">前の手順で作成した BizTalk アセンブリを、暗号化されたメッセージの受信場所を含む BizTalk アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="86977-127">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to receive encrypted messages.</span></span> <span data-ttu-id="86977-128">BizTalk アセンブリを追加する方法の詳細については、次を参照してください。[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="86977-128">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="86977-129">前の手順で作成した受信パイプラインを使用して、BizTalk アプリケーションの受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="86977-129">Configure the receive locations in the BizTalk Application with the receive pipeline that you created in previous procedure.</span></span> <span data-ttu-id="86977-130">構成する方法については、受信場所を参照してください[受信場所のプロパティを編集する方法](../core/how-to-edit-the-properties-of-a-receive-location.md)します。</span><span class="sxs-lookup"><span data-stu-id="86977-130">For more information about how to configure receive locations, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
3.  <span data-ttu-id="86977-131">手順でインストールされている解読証明書の受信場所の受信ハンドラーとして使用されるホストを構成するには"暗号化されたメッセージを受信するための BizTalk ホストを構成する"で[暗号化の証明書をインストールする方法メッセージ](../core/how-to-install-the-certificates-for-encrypted-messages.md)します。</span><span class="sxs-lookup"><span data-stu-id="86977-131">Configure the host used as receive handler for the receive location with the decryption certificate that you installed in the procedure," To configure BizTalk hosts for receiving encrypted messages" in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span> <span data-ttu-id="86977-132">詳細についてはホストのプロパティを構成するを参照してください方法[ホスト プロパティを変更する方法](../core/how-to-modify-host-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="86977-132">For more information how to configure host properties, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86977-133">参照</span><span class="sxs-lookup"><span data-stu-id="86977-133">See Also</span></span>  
 <span data-ttu-id="86977-134">[BizTalk Server は、暗号化されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="86977-134">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 <span data-ttu-id="86977-135">[暗号化されたメッセージを送信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="86977-135">[How to Configure BizTalk Server for Sending Encrypted Messages](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md) </span></span>  
 [<span data-ttu-id="86977-136">暗号化されたメッセージの送受信</span><span class="sxs-lookup"><span data-stu-id="86977-136">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)