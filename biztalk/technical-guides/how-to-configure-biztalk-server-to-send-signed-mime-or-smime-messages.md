---
title: "MIME または SMIME メッセージを送信する BizTalk Server を構成する方法が署名されて |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba42463b-2c12-4329-919e-aca427d14eee
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 623e8e6349494ce1d15089093b1620b4da76adbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-to-send-signed-mime-or-smime-messages"></a><span data-ttu-id="c4a68-102">MIME または SMIME メッセージを送信する BizTalk Server を構成する方法が署名済み</span><span class="sxs-lookup"><span data-stu-id="c4a68-102">How to Configure BizTalk Server to Send Signed MIME or SMIME Messages</span></span>
<span data-ttu-id="c4a68-103">このトピックは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]符号付きの MIME/SMIME メッセージを送信する証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="c4a68-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to send signed MIME/SMIME messages.</span></span> <span data-ttu-id="c4a68-104">以下の手順は、署名付きメッセージの送信の AS2 トランスポート経由で構成にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="c4a68-104">The procedure below also applies to configuring the sending of signed messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c4a68-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="c4a68-105">Prerequisites</span></span>  
 <span data-ttu-id="c4a68-106">このトピックの手順を実行する必要がありますログインする必要がのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="c4a68-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-send-signed-messages"></a><span data-ttu-id="c4a68-107">署名付きメッセージを送信する BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="c4a68-107">To configure BizTalk Server to send signed messages</span></span>  
  
1.  <span data-ttu-id="c4a68-108">次のように、署名付きメッセージを送信するためのパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4a68-108">Create a pipeline to send signed messages, as follows:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4a68-109">この手順に含まれるため、AS2Send および AS2EdiSend パイプラインを署名付きメッセージを送信するための AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c4a68-109">This step is not necessary when configuring AS2 transport for sending signed messages because the AS2Send and AS2EdiSend pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
    1.  <span data-ttu-id="c4a68-110">送信パイプラインを作成し、パイプラインのエンコード ステージに MIME/SMIME エンコーダー パイプライン コンポーネントをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="c4a68-110">Create a send pipeline and then drag the MIME/SMIME Encoder pipeline component into the Encode stage of the pipeline.</span></span>  
  
    2.  <span data-ttu-id="c4a68-111">**プロパティ**ウィンドウ、ClearSign または [blobsign] に MIME/SMIME エンコーダー パイプライン コンポーネントの署名の種類プロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4a68-111">In the **Properties** window, configure the MIME/SMIME Encoder pipeline component Signature type property to ClearSign or BlobSign.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c4a68-112">暗号化を使用しても場合は、[blobsign] のみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="c4a68-112">If you are also using encryption, you can only select BlobSign.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c4a68-113">BizTalk グループにパイプラインを展開した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して送信パイプライン コンポーネントのプロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c4a68-113">You can configure the send pipeline component properties using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console after the pipeline has been deployed into a BizTalk group.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c4a68-114">MIME/SMIME エンコーダー パイプライン コンポーネントは、暗号化とデジタル署名の両方を実行します (両方の機能を実行するように構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="c4a68-114">The MIME/SMIME Encoder pipeline component performs both encryption and digital signing (when configured to perform both functions).</span></span> <span data-ttu-id="c4a68-115">したがって、暗号化および署名されたメッセージを送信するように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成する場合は、同じ送信パイプラインを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4a68-115">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted and signed messages, you can use the same send pipeline.</span></span> <span data-ttu-id="c4a68-116">つまり、暗号化用とデジタル署名用に異なるパイプラインを作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c4a68-116">In other words, you do not have to create separate pipelines for encryption and digital signing.</span></span>  
  
    3.  <span data-ttu-id="c4a68-117">送信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="c4a68-117">Build and deploy the send pipeline.</span></span>  
  
2.  <span data-ttu-id="c4a68-118">次のように、署名付きメッセージを送信するための送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4a68-118">Configure the send port for sending signed messages, as follows:</span></span>  
  
    1.  <span data-ttu-id="c4a68-119">署名付きメッセージを送信する送信ポートを含む BizTalk アプリケーションに送信パイプラインを含むに作成した BizTalk アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="c4a68-119">Add the BizTalk assembly that you created containing the send pipeline to the BizTalk application that includes the send ports to send signed messages.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="c4a68-120">この手順は、AS2Send パイプラインと AS2EdiSend パイプラインが BizTalk EDI アプリケーションに含まれるためには、メッセージをサインインした状態を送信するための AS2 トランスポートを構成するために必要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c4a68-120">This step is not necessary when configuring AS2 transport for sending signed messages because the AS2Send and AS2EdiSend pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="c4a68-121">前の手順で作成した送信パイプラインを持つ BizTalk アプリケーションでの送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4a68-121">Configure the send port in the BizTalk application with the send pipeline that you created in the previous procedure.</span></span>  
  
3.  <span data-ttu-id="c4a68-122">次のように、署名付きメッセージを送信するための証明書で、グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4a68-122">Configure the group with a certificate for sending signed messages, as follows:</span></span>  
  
    1.  <span data-ttu-id="c4a68-123">内の BizTalk グループを展開してインストールされている署名証明書を BizTalk グループの構成、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールの右**BizTalk グループ**、クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="c4a68-123">Configure the BizTalk group with the signing certificate that you installed by expanding the BizTalk group in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-clicking **BizTalk Group**, and then clicking **Properties**.</span></span>  
  
    2.  <span data-ttu-id="c4a68-124">証明書] タブをクリックし、をクリックして**参照**適切な証明書を選択し、[クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="c4a68-124">Click the Certificate tab, click **Browse**, select the appropriate certificate, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4a68-125">参照</span><span class="sxs-lookup"><span data-stu-id="c4a68-125">See Also</span></span>  
 [<span data-ttu-id="c4a68-126">MIME または SMIME メッセージの証明書の構成</span><span class="sxs-lookup"><span data-stu-id="c4a68-126">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)