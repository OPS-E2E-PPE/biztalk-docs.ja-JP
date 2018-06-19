---
title: MIME または SMIME メッセージを受信する BizTalk Server を構成する方法が署名されて |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50570257-7bb6-4ede-9026-873eefd06483
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88487fb96c89b8a611ab591223fa1820f70de1cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297818"
---
# <a name="how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages"></a><span data-ttu-id="cc697-102">MIME または SMIME メッセージを受信する BizTalk Server を構成する方法が署名済み</span><span class="sxs-lookup"><span data-stu-id="cc697-102">How to Configure BizTalk Server to Receive Signed MIME or SMIME Messages</span></span>
<span data-ttu-id="cc697-103">このトピックは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]符号付きの MIME/SMIME メッセージを受信する証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="cc697-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to receive signed MIME/SMIME messages.</span></span> <span data-ttu-id="cc697-104">以下の手順は、AS2 トランスポート経由での署名付きメッセージの受信の構成にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="cc697-104">The procedure below also applies to configuring the receiving of signed messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cc697-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="cc697-105">Prerequisites</span></span>  
 <span data-ttu-id="cc697-106">このトピックの手順を実行する必要がありますログインする必要がのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="cc697-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-receive-signed-messages"></a><span data-ttu-id="cc697-107">署名付きメッセージを受信する BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="cc697-107">To configure BizTalk Server to receive signed messages</span></span>  
  
1.  <span data-ttu-id="cc697-108">次のように、署名付きメッセージを受信するためのパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="cc697-108">Create a pipeline to receive signed messages, as follows:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc697-109">この手順に含まれるので、AS2Receive と AS2EdiReceive パイプラインを署名付きメッセージを受信の AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="cc697-109">This step is not necessary when configuring AS2 transport for receiving signed messages because the AS2Receive and AS2EdiReceive pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
    1.  <span data-ttu-id="cc697-110">受信パイプラインを作成し、受信パイプラインのデコード ステージに MIME/SMIME デコーダー パイプライン コンポーネントをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="cc697-110">Create a receive pipeline and then drag the MIME/SMIME Decoder pipeline component into the Decode stage of the receive pipeline.</span></span>  
  
    2.  <span data-ttu-id="cc697-111">**プロパティ**ウィンドウで、MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="cc697-111">In the **Properties** window, configure the MIME/SMIME Decoder pipeline component properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="cc697-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="cc697-112">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="cc697-113">BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="cc697-113">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
    3.  <span data-ttu-id="cc697-114">受信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="cc697-114">Build and deploy the receive pipeline.</span></span>  
  
2.  <span data-ttu-id="cc697-115">次のように、署名付きメッセージを受信するための受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc697-115">Configure a receive location for receiving signed messages, as follows:</span></span>  
  
    1.  <span data-ttu-id="cc697-116">署名付きメッセージを受信する受信場所を含む BizTalk アプリケーションに、受信パイプラインを含むに作成した BizTalk アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc697-116">Add the BizTalk assembly that you created containing the receive pipeline to the BizTalk application including the receive locations to receive signed messages.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="cc697-117">この手順は、AS2Receive パイプラインと AS2EdiReceive パイプラインが BizTalk EDI アプリケーションに含まれるために署名付きメッセージを受信するは、AS2 トランスポートを構成するときに必要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cc697-117">This step is not necessary when configuring AS2 transport for receiving signed messages because the AS2Receive and AS2EdiReceive pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="cc697-118">前の手順で作成した受信パイプラインを使用して BizTalk アプリケーションで受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="cc697-118">Configure the receive locations in the BizTalk application with the receive pipeline that you created in previous procedure.</span></span>  
  
3.  <span data-ttu-id="cc697-119">次のように、署名付きメッセージを受信するための証明書で、パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="cc697-119">Configure the party with a certificate for receiving signed messages, as follows:</span></span>  
  
    -   <span data-ttu-id="cc697-120">開く、**パーティのプロパティ** ダイアログ ボックスをクリックして、BizTalk Server 管理コンソールで、**証明書** タブで、をクリックして**参照**、適切な証明書を選択クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="cc697-120">Open the **Party Properties** dialog box in the BizTalk Server Administration Console, click the **Certificate** tab, click **Browse**, select the appropriate certificate, and then click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="cc697-121">パーティの署名確認に使用する証明書は、他のパーティの署名確認に使用する証明書と重複しない、一意のものでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="cc697-121">The certificate used to verify a signature for a party must be unique from the certificates used to verify signatures for other parties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc697-122">参照</span><span class="sxs-lookup"><span data-stu-id="cc697-122">See Also</span></span>  
 [<span data-ttu-id="cc697-123">MIME または SMIME メッセージの証明書の構成</span><span class="sxs-lookup"><span data-stu-id="cc697-123">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)