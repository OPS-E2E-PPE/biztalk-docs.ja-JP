---
title: 暗号化された MIME/SMIME メッセージを送信する BizTalk Server を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f67152-5f80-4040-a9d6-0819fab7fcb5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dded85a219f5a32ce83ebc4da96f0f0566bf8c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253390"
---
# <a name="how-to-configure-biztalk-server-to-send-encrypted-mimesmime-messages"></a><span data-ttu-id="59ae7-102">暗号化された MIME/SMIME メッセージを送信する BizTalk Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="59ae7-102">How to Configure BizTalk Server to Send Encrypted MIME/SMIME Messages</span></span>
<span data-ttu-id="59ae7-103">このトピックでは、証明書を使用して暗号化された MIME/SMIME メッセージを送信する BizTalk Server を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="59ae7-103">This topic describes how to configure BizTalk Server to use certificates to send encrypted MIME/SMIME messages.</span></span> <span data-ttu-id="59ae7-104">以下の手順は、AS2 トランスポート経由で暗号化されたメッセージの送信の構成にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="59ae7-104">The procedure below also applies to configuring the sending of encrypted messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="59ae7-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="59ae7-105">Prerequisites</span></span>  
 <span data-ttu-id="59ae7-106">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="59ae7-106">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-send-encrypted-messages"></a><span data-ttu-id="59ae7-107">暗号化されたメッセージを送信する BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="59ae7-107">To configure BizTalk Server to send encrypted messages</span></span>  
  
1. <span data-ttu-id="59ae7-108">次のように、暗号化されたメッセージを送信するためのパイプラインを作成します。</span><span class="sxs-lookup"><span data-stu-id="59ae7-108">Create a pipeline to send encrypted messages, as follows:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="59ae7-109">この手順に含まれるため、AS2Send および AS2EdiSend パイプラインを暗号化されたメッセージを送信するための AS2 トランスポートを構成するときは必要ありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="59ae7-109">This step is not necessary when configuring AS2 transport for sending encrypted messages because the AS2Send and AS2EdiSend pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
   1.  <span data-ttu-id="59ae7-110">送信パイプラインを作成し、パイプラインのエンコード ステージに MIME/SMIME エンコーダー パイプライン コンポーネントをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="59ae7-110">Create a send pipeline and then drag the MIME/SMIME Encoder pipeline component into the Encode stage of the pipeline.</span></span>  
  
   2.  <span data-ttu-id="59ae7-111">**プロパティ**ウィンドウで、MIME/SMIME エンコーダー パイプライン コンポーネントを有効にする暗号化プロパティを構成**True**します。</span><span class="sxs-lookup"><span data-stu-id="59ae7-111">In the **Properties** window, configure the MIME/SMIME Encoder pipeline component Enable encryption property to **True**.</span></span>  
  
       > [!NOTE]  
       >  <span data-ttu-id="59ae7-112">BizTalk グループにパイプラインを展開した後、BizTalk Server 管理コンソールを使用して、送信パイプライン コンポーネントのプロパティを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="59ae7-112">You can configure the send pipeline component properties using the BizTalk Server Administration console after the pipeline has been deployed into a BizTalk group.</span></span>  
  
   3.  <span data-ttu-id="59ae7-113">送信パイプラインをビルドして配置します。</span><span class="sxs-lookup"><span data-stu-id="59ae7-113">Build and deploy the send pipeline.</span></span>  
  
2. <span data-ttu-id="59ae7-114">次のように、暗号化されたメッセージを送信するための送信ポートを構成するには。</span><span class="sxs-lookup"><span data-stu-id="59ae7-114">Configure the send port for sending encrypted messages, as follows:</span></span>  
  
   1.  <span data-ttu-id="59ae7-115">暗号化されたメッセージを受信する受信場所を含む BizTalk アプリケーションに送信パイプラインを含むに作成した BizTalk アセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="59ae7-115">Add the BizTalk assembly that you created containing the send pipeline to the BizTalk application including the receive locations to receive encrypted messages.</span></span>  
  
       > [!NOTE]  
       >  <span data-ttu-id="59ae7-116">AS2Send および AS2EdiSend パイプラインが BizTalk EDI アプリケーションに含まれているために、暗号化されたメッセージを送信するための AS2 トランスポートを構成するときに、この手順は必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="59ae7-116">This step is not necessary when configuring AS2 transport for sending encrypted messages because the AS2Send and AS2EdiSend pipelines are included in the BizTalk EDI Application.</span></span>  
  
   2.  <span data-ttu-id="59ae7-117">BizTalk アプリケーションを前の手順で作成した送信パイプラインで送信ポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="59ae7-117">Configure the send port in the BizTalk Application with the send pipeline that you created in the previous procedure.</span></span>  
  
   3.  <span data-ttu-id="59ae7-118">クリックすると、送信ポートを右クリックしてインストールされている暗号化証明書を割り当てる**プロパティ**、 をクリックし、**証明書**します。</span><span class="sxs-lookup"><span data-stu-id="59ae7-118">Assign the encryption certificate that you installed by right-clicking the send port, clicking **Properties**, and then clicking **Certificate**.</span></span> <span data-ttu-id="59ae7-119">をクリックして**参照**、この送信ポートに割り当てるし をクリックしたい証明書を参照**OK**します。</span><span class="sxs-lookup"><span data-stu-id="59ae7-119">Click **Browse**, browse to the certificate that you want to assign to this send port, and then click **OK**.</span></span>  
  
       > [!NOTE]  
       >  <span data-ttu-id="59ae7-120">かどうか、証明書がありません、ローカル コンピューター上で、**拇印**ボックスに入力し、証明書の拇印を貼り付けますまたはクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="59ae7-120">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="59ae7-121">証明書の拇印は、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進形式を持ちます。</span><span class="sxs-lookup"><span data-stu-id="59ae7-121">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>