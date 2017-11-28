---
title: "署名付きメッセージを送信するための BizTalk Server を構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be86fbb3-de80-4d9f-bcf0-c61347704229
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef71f5c11d6c1a000369644b822aa9f4d4ef792
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-for-sending-signed-messages"></a><span data-ttu-id="247d8-102">署名付きメッセージを送信するための BizTalk Server の構成方法</span><span class="sxs-lookup"><span data-stu-id="247d8-102">How to Configure BizTalk Server for Sending Signed Messages</span></span>
<span data-ttu-id="247d8-103">署名付きメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="247d8-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send signed messages.</span></span>  
  
-   <span data-ttu-id="247d8-104">署名付きメッセージを送信するためのパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="247d8-104">To create a pipeline to send signed messages</span></span>  
  
-   <span data-ttu-id="247d8-105">署名付きメッセージを送信するための送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="247d8-105">To configure the send port for sending signed messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="247d8-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="247d8-106">Prerequisites</span></span>  
 <span data-ttu-id="247d8-107">構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s 署名付きメッセージを送信するための手順を実行する必要があります[デジタル署名の証明書をインストールする方法](../core/how-to-install-the-certificates-for-digital-signatures.md)です。</span><span class="sxs-lookup"><span data-stu-id="247d8-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for sending signed messages, you must perform the steps in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-send-signed-messages"></a><span data-ttu-id="247d8-108">署名付きメッセージを送信するためのパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="247d8-108">To create a pipeline to send signed messages</span></span>  
  
1.  <span data-ttu-id="247d8-109">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="247d8-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
    1.  <span data-ttu-id="247d8-110">**ファイル** メニューのをクリックして**新しい項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="247d8-110">On the **File** menu, click **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="247d8-111">**新しい項目の追加** ダイアログ ボックスで BizTalk プロジェクトの項目を展開し、をクリックして**パイプライン ファイル**、をクリックし、**送信パイプライン**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="247d8-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Send Pipeline** template.</span></span>  
  
    3.  <span data-ttu-id="247d8-112">**名前**フィールドに、パイプラインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="247d8-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
    4.  <span data-ttu-id="247d8-113">**[追加]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="247d8-113">Click **Add**.</span></span>  
  
         <span data-ttu-id="247d8-114">新しいパイプラインがソリューション エクスプローラーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="247d8-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="247d8-115">MIME/SMIME エンコーダー パイプライン コンポーネントを受信パイプラインの [エンコード] ステージにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="247d8-115">Drag the MIME/SMIME Encoder pipeline component into the Encode stage of a receive pipeline.</span></span>  
  
     <span data-ttu-id="247d8-116">![MIME & #47。SMIME エンコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span><span class="sxs-lookup"><span data-stu-id="247d8-116">![MIME&#47;SMIME Encoder pipeline component](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span></span>  
  
3.  <span data-ttu-id="247d8-117">[プロパティ] ウィンドウで、MIME/SMIME エンコーダー パイプライン コンポーネントを構成する**署名の種類**プロパティを**ClearSign**または**BlobSign**です。</span><span class="sxs-lookup"><span data-stu-id="247d8-117">In the Properties window, configure the MIME/SMIME Encoder pipeline component **Signature type** property to **ClearSign**or **BlobSign**.</span></span> <span data-ttu-id="247d8-118">詳細については、**暗号化を有効にする**プロパティを参照してください[- MIME/SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="247d8-118">For more information about the **Enable encryption** property, see [How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="247d8-119">暗号化を使用しても場合のみ選択**BlobSign**です。</span><span class="sxs-lookup"><span data-stu-id="247d8-119">If you are also using encryption, you can only select **BlobSign**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="247d8-120">BizTalk グループにパイプラインを展開した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して送信パイプライン コンポーネントのプロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="247d8-120">You can configure the send pipeline component properties using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="247d8-121">詳細については、次を参照してください。[送信ポートのインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="247d8-121">For more information, see [How to Configure Per-Instance Pipeline Properties for a Send Port](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="247d8-122">MIME/SMIME エンコーダー パイプライン コンポーネントは、暗号化とデジタル署名の両方を実行します (両方の機能を実行するように構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="247d8-122">The MIME/SMIME Encoder pipeline component performs both encryption and digital signing (when configured to perform both functions).</span></span> <span data-ttu-id="247d8-123">したがって、暗号化および署名されたメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ送信パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="247d8-123">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted and signed messages, you can use the same send pipeline.</span></span> <span data-ttu-id="247d8-124">つまり、暗号化用とデジタル署名用に異なるパイプラインを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="247d8-124">In other words, you do not have to create separate pipelines for encryption and digital signing.</span></span>  
  
4.  <span data-ttu-id="247d8-125">送信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="247d8-125">Build and deploy the send pipeline.</span></span>  
  
### <a name="to-configure-the-send-port-for-sending-signed-messages"></a><span data-ttu-id="247d8-126">署名付きメッセージを送信するための送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="247d8-126">To configure the send port for sending signed messages</span></span>  
  
1.  <span data-ttu-id="247d8-127">前の手順で作成した BizTalk アセンブリを、送信する署名付きメッセージの受信場所を含む BizTalk アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="247d8-127">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to sending signed messages.</span></span> <span data-ttu-id="247d8-128">BizTalk アセンブリを追加する方法の詳細については、次を参照してください。 [BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="247d8-128">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="247d8-129">前の手順で作成した送信パイプラインを使用して、BizTalk アプリケーションの送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="247d8-129">Configure the send port in the BizTalk Application with the send pipeline that you created in previous procedure.</span></span> <span data-ttu-id="247d8-130">送信ポートを構成する方法の詳細については、次を参照してください。[の作成および構成する送信ポート](../core/creating-and-configuring-send-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="247d8-130">For more information about how to configure send ports, see [Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md).</span></span>  
  
3.  <span data-ttu-id="247d8-131">BizTalk グループ、署名証明書を構成でインストールした[デジタル署名の証明書をインストールする方法](../core/how-to-install-the-certificates-for-digital-signatures.md)です。</span><span class="sxs-lookup"><span data-stu-id="247d8-131">Configure the BizTalk group with the signing certificate that you installed in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span> <span data-ttu-id="247d8-132">詳細については、BizTalk グループを構成する方法[グループのプロパティを変更する方法](../core/how-to-modify-group-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="247d8-132">For more information how to configure a BizTalk group, see [How to Modify Group Properties](../core/how-to-modify-group-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="247d8-133">参照</span><span class="sxs-lookup"><span data-stu-id="247d8-133">See Also</span></span>  
 <span data-ttu-id="247d8-134">[署名付きメッセージを受信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="247d8-134">[How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span></span>  
 <span data-ttu-id="247d8-135">[BizTalk Server が署名されたメッセージで使用する証明書](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="247d8-135">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 [<span data-ttu-id="247d8-136">署名付きメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="247d8-136">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)