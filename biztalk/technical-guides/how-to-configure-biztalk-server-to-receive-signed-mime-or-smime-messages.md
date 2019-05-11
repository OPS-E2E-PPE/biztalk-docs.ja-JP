---
title: MIME または SMIME メッセージに署名された受信する BizTalk Server を構成する方法 |Microsoft Docs
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
ms.openlocfilehash: 26882e196fe90d87b9e63bc13d487f60ac99627c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253322"
---
# <a name="how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages"></a><span data-ttu-id="920ba-102">MIME または SMIME メッセージに署名された受信する BizTalk Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="920ba-102">How to Configure BizTalk Server to Receive Signed MIME or SMIME Messages</span></span>
<span data-ttu-id="920ba-103">このトピックでは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]証明書を使用して署名された MIME/SMIME メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="920ba-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to receive signed MIME/SMIME messages.</span></span> <span data-ttu-id="920ba-104">以下の手順は、AS2 トランスポート経由での署名付きメッセージの受信の構成にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="920ba-104">The procedure below also applies to configuring the receiving of signed messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="920ba-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="920ba-105">Prerequisites</span></span>  
 <span data-ttu-id="920ba-106">このトピックの手順を実行する必要がありますがログオンしてのメンバーとして、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="920ba-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-receive-signed-messages"></a><span data-ttu-id="920ba-107">署名付きメッセージを受信する BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="920ba-107">To configure BizTalk Server to receive signed messages</span></span>  
  
1. <span data-ttu-id="920ba-108">次のように、署名付きメッセージを受信するためのパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="920ba-108">Create a pipeline to receive signed messages, as follows:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="920ba-109">この手順に含まれるので、AS2Receive と AS2EdiReceive パイプラインを署名付きメッセージを受信するため、AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="920ba-109">This step is not necessary when configuring AS2 transport for receiving signed messages because the AS2Receive and AS2EdiReceive pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
   1. <span data-ttu-id="920ba-110">受信パイプラインを作成し、受信パイプラインのデコード ステージに MIME/SMIME デコーダー パイプライン コンポーネントをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="920ba-110">Create a receive pipeline and then drag the MIME/SMIME Decoder pipeline component into the Decode stage of the receive pipeline.</span></span>  
  
   2. <span data-ttu-id="920ba-111">**プロパティ**ウィンドウで、MIME/SMIME デコーダー パイプライン コンポーネントのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="920ba-111">In the **Properties** window, configure the MIME/SMIME Decoder pipeline component properties.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="920ba-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk グループにパイプラインを展開した後、受信場所のパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="920ba-112">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="920ba-113">BizTalk グループの受信場所ごとに、異なるパイプライン プロパティを構成できます。</span><span class="sxs-lookup"><span data-stu-id="920ba-113">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
   3. <span data-ttu-id="920ba-114">受信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="920ba-114">Build and deploy the receive pipeline.</span></span>  
  
2. <span data-ttu-id="920ba-115">次のように、署名付きメッセージを受信するための受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="920ba-115">Configure a receive location for receiving signed messages, as follows:</span></span>  
  
   1. <span data-ttu-id="920ba-116">署名付きメッセージを受信する受信場所を含む BizTalk アプリケーションに受信パイプラインを含むに作成した BizTalk アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="920ba-116">Add the BizTalk assembly that you created containing the receive pipeline to the BizTalk application including the receive locations to receive signed messages.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="920ba-117">この手順は、AS2Receive と AS2EdiReceive パイプラインで BizTalk EDI アプリケーションに含まれるため、署名付きメッセージを受信するは、AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="920ba-117">This step is not necessary when configuring AS2 transport for receiving signed messages because the AS2Receive and AS2EdiReceive pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   2. <span data-ttu-id="920ba-118">前の手順で作成した受信パイプラインを備えた BizTalk アプリケーションでは、受信場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="920ba-118">Configure the receive locations in the BizTalk application with the receive pipeline that you created in previous procedure.</span></span>  
  
3. <span data-ttu-id="920ba-119">次のように、署名付きメッセージを受信するための証明書で、パーティを構成します。</span><span class="sxs-lookup"><span data-stu-id="920ba-119">Configure the party with a certificate for receiving signed messages, as follows:</span></span>  
  
   -   <span data-ttu-id="920ba-120">オープン、**パーティのプロパティ** ダイアログ ボックスで、BizTalk Server 管理コンソール をクリックして、**証明書** タブで、をクリックして**参照**、適切な証明書を選択クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="920ba-120">Open the **Party Properties** dialog box in the BizTalk Server Administration Console, click the **Certificate** tab, click **Browse**, select the appropriate certificate, and then click **OK**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="920ba-121">パーティの署名確認に使用する証明書は、他のパーティの署名確認に使用する証明書と重複しない、一意のものでなければなりません。</span><span class="sxs-lookup"><span data-stu-id="920ba-121">The certificate used to verify a signature for a party must be unique from the certificates used to verify signatures for other parties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="920ba-122">参照</span><span class="sxs-lookup"><span data-stu-id="920ba-122">See Also</span></span>  
 [<span data-ttu-id="920ba-123">MIME またはメッセージの SMIME 証明書の構成</span><span class="sxs-lookup"><span data-stu-id="920ba-123">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)