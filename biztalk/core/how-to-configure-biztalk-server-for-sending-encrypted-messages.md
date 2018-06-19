---
title: 暗号化されたメッセージを送信するための BizTalk Server を構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb751d7c-49cd-46f0-9630-254cf06c497e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0b3ef721c263c892690b9ac5b7d2dd15155f0dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248874"
---
# <a name="how-to-configure-biztalk-server-for-sending-encrypted-messages"></a><span data-ttu-id="4c308-102">暗号化されたメッセージを送信するための BizTalk Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="4c308-102">How to Configure BizTalk Server for Sending Encrypted Messages</span></span>
<span data-ttu-id="4c308-103">暗号化されたメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4c308-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted messages.</span></span>  
  
-   <span data-ttu-id="4c308-104">暗号化されたメッセージを送信するためのパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="4c308-104">To create a pipeline to send encrypted messages</span></span>  
  
-   <span data-ttu-id="4c308-105">暗号化されたメッセージを送信するための送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="4c308-105">To configure the send port for sending encrypted messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4c308-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="4c308-106">Prerequisites</span></span>  
 <span data-ttu-id="4c308-107">構成する前に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]暗号化されたメッセージを送信するためで手順を実行する必要があります[メッセージの暗号化の証明書をインストールする方法](../core/how-to-install-the-certificates-for-encrypted-messages.md)です。</span><span class="sxs-lookup"><span data-stu-id="4c308-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for sending encrypted messages, you must perform the steps in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-send-encrypted-messages"></a><span data-ttu-id="4c308-108">暗号化されたメッセージを送信するためのパイプラインを作成するには</span><span class="sxs-lookup"><span data-stu-id="4c308-108">To create a pipeline to send encrypted messages</span></span>  
  
1.  <span data-ttu-id="4c308-109">Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のソリューション エクスプローラーで、パイプラインを作成するプロジェクトを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c308-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
    1.  <span data-ttu-id="4c308-110">**ファイル** メニューのをクリックして**新しい項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="4c308-110">On the **File** menu, click **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="4c308-111">**新しい項目の追加** ダイアログ ボックスで BizTalk プロジェクトの項目を展開し、をクリックして**パイプライン ファイル**、をクリックし、**送信パイプライン**テンプレート。</span><span class="sxs-lookup"><span data-stu-id="4c308-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Send Pipeline** template.</span></span>  
  
    3.  <span data-ttu-id="4c308-112">**名前**フィールドに、パイプラインの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c308-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
    4.  <span data-ttu-id="4c308-113">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c308-113">Click **Add**.</span></span>  
  
         <span data-ttu-id="4c308-114">新しいパイプラインがソリューション エクスプローラーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c308-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="4c308-115">MIME/SMIME エンコーダー パイプライン コンポーネントを受信パイプラインの [エンコード] ステージにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="4c308-115">Drag the MIME/SMIME Encoder pipeline component into the Encode stage of a receive pipeline.</span></span>  
  
     <span data-ttu-id="4c308-116">![MIME & #47。SMIME エンコーダー パイプライン コンポーネント](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span><span class="sxs-lookup"><span data-stu-id="4c308-116">![MIME&#47;SMIME Encoder pipeline component](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span></span>  
  
    -   <span data-ttu-id="4c308-117">[プロパティ] ウィンドウで、MIME/SMIME エンコーダー パイプライン コンポーネントを構成する**暗号化を有効にする**プロパティを`True`です。</span><span class="sxs-lookup"><span data-stu-id="4c308-117">In the Properties window, configure the MIME/SMIME Encoder pipeline component **Enable encryption** property to `True`.</span></span> <span data-ttu-id="4c308-118">詳細については、**暗号化を有効にする**プロパティを参照してください[- MIME/SMIME エンコーダー パイプライン コンポーネントを構成する方法](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)です。</span><span class="sxs-lookup"><span data-stu-id="4c308-118">For more information about the **Enable encryption** property, see [How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4c308-119">BizTalk グループにパイプラインを展開した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して送信パイプライン コンポーネントのプロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="4c308-119">You can configure the send pipeline component properties using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="4c308-120">詳細については、次を参照してください。[送信ポートのインスタンスごとのパイプライン プロパティを構成する方法](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="4c308-120">For more information, see [How to Configure Per-Instance Pipeline Properties for a Send Port](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4c308-121">MIME/SMIME エンコーダー パイプライン コンポーネントは、暗号化とデジタル署名の両方を実行します (両方の機能を実行するように構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="4c308-121">The MIME/SMIME Encoder pipeline component performs both encryption and digital signing (when configured to perform both functions).</span></span> <span data-ttu-id="4c308-122">したがって、暗号化および署名されたメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ送信パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c308-122">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted and signed messages, you can use the same send pipeline.</span></span> <span data-ttu-id="4c308-123">つまり、暗号化用とデジタル署名用に異なるパイプラインを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4c308-123">In other words, you do not have to create separate pipelines for encryption and digital signing.</span></span>  
  
3.  <span data-ttu-id="4c308-124">送信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="4c308-124">Build and deploy the send pipeline.</span></span>  
  
### <a name="to-configure-the-send-port-for-sending-encrypted-messages"></a><span data-ttu-id="4c308-125">暗号化されたメッセージを送信するための送信ポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="4c308-125">To configure the send port for sending encrypted messages</span></span>  
  
1.  <span data-ttu-id="4c308-126">前の手順で作成した BizTalk アセンブリを、暗号化されたメッセージを送信する送信ポートを含む BizTalk アプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c308-126">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the send ports to send encrypted messages.</span></span> <span data-ttu-id="4c308-127">BizTalk アセンブリを追加する方法の詳細については、次を参照してください。 [BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="4c308-127">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="4c308-128">前の手順で作成した送信パイプラインを持つ BizTalk アプリケーションに送信ポートを構成しにインストールされている暗号化証明書を割り当てます[メッセージの暗号化の証明書をインストールする方法](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="4c308-128">Configure the send port in the BizTalk Application with the send pipeline that you created in previous procedure, and then assign the encryption certificate that you installed in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span> <span data-ttu-id="4c308-129">送信ポートを構成する方法の詳細については、次を参照してください。[送信ポートに証明書を割り当てる方法](../core/how-to-assign-a-certificate-to-a-send-port.md)です。</span><span class="sxs-lookup"><span data-stu-id="4c308-129">For more information about how to configure send ports, see [How to Assign a Certificate to a Send Port](../core/how-to-assign-a-certificate-to-a-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c308-130">参照</span><span class="sxs-lookup"><span data-stu-id="4c308-130">See Also</span></span>  
 <span data-ttu-id="4c308-131">[暗号化されたメッセージを受信するための BizTalk Server を構成する方法](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="4c308-131">[How to Configure BizTalk Server for Receiving Encrypted Messages](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md) </span></span>  
 <span data-ttu-id="4c308-132">[BizTalk Server は暗号化されたメッセージを使用する証明書](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="4c308-132">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 [<span data-ttu-id="4c308-133">暗号化されたメッセージを送受信します。</span><span class="sxs-lookup"><span data-stu-id="4c308-133">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)