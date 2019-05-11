---
title: 送信ポートに証明書を割り当てる方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, assigning
- managing [send ports], certificates
- assigning certificates
- certificates, send ports
ms.assetid: ba9e9c8b-f5b6-4fee-9e89-31b0f1df6ed4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb9fbc2cc7237f1e5cf9343f7ae8537b7ea8218a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387207"
---
# <a name="how-to-assign-a-certificate-to-a-send-port"></a><span data-ttu-id="db8ab-102">送信ポートに証明書を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="db8ab-102">How to Assign a Certificate to a Send Port</span></span>
<span data-ttu-id="db8ab-103">このトピックでは、BizTalk Server 管理コンソールを使用して送信ポートにセキュリティ証明書を割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="db8ab-103">This topic describes how to use the BizTalk Server Administration console to assign a security certificate to a send port.</span></span> <span data-ttu-id="db8ab-104">証明書は、BizTalk Server を実行しているコンピューターの他のユーザー証明書ストアに存在する必要があります、この送信ポートに関連付けられているメッセージは処理されずやエラーをログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="db8ab-104">The certificate must exist in the Other People certificate store on the computer running BizTalk Server, or messages associated with this send port will not be processed, and errors will be logged.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db8ab-105">アプリケーション開発者割り当てることができますセキュリティ証明書を送信ポートに開発プロセス中にこのトピックの手順を使用しています。</span><span class="sxs-lookup"><span data-stu-id="db8ab-105">The application developer can assign a security certificate to a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="db8ab-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="db8ab-106">Prerequisites</span></span>  
 <span data-ttu-id="db8ab-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db8ab-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="db8ab-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="db8ab-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-assign-a-certificate-to-a-send-port"></a><span data-ttu-id="db8ab-109">送信ポートに証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="db8ab-109">To assign a certificate to a send port</span></span>  
  
1. <span data-ttu-id="db8ab-110">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="db8ab-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="db8ab-111">コンソール ツリーで、BizTalk グループと送信ポートに証明書を割り当てる BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="db8ab-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to assign a certificate to a send port.</span></span>  
  
3. <span data-ttu-id="db8ab-112">展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**証明書**します。</span><span class="sxs-lookup"><span data-stu-id="db8ab-112">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Certificate**.</span></span>  
  
4. <span data-ttu-id="db8ab-113">ローカル コンピューターの証明書が存在する場合にクリックします**参照**、この送信ポートに割り当てるし をクリックしたい証明書を参照**OK**します。</span><span class="sxs-lookup"><span data-stu-id="db8ab-113">If the certificate exists on the local computer, click **Browse**, browse to the certificate that you want to assign to this send port, and then click **OK**.</span></span> <span data-ttu-id="db8ab-114">それ以外の場合、この手順をスキップします。</span><span class="sxs-lookup"><span data-stu-id="db8ab-114">Otherwise, skip this step.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="db8ab-115">ローカル コンピューターの証明書が存在する場合でも、送信ポートがメッセージを処理できる前に、異なる場合、BizTalk Server を実行するコンピューターにする必要がありますも存在します。</span><span class="sxs-lookup"><span data-stu-id="db8ab-115">Even if the certificate exists on the local computer, it must also exist on the computer running BizTalk Server, if different, before the send port will be able to process messages.</span></span>  
  
5. <span data-ttu-id="db8ab-116">かどうか、証明書がありません、ローカル コンピューター上で、**拇印**ボックスに入力し、証明書の拇印を貼り付けますまたはクリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="db8ab-116">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="db8ab-117">証明書の拇印は、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進形式を持ちます。</span><span class="sxs-lookup"><span data-stu-id="db8ab-117">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db8ab-118">参照</span><span class="sxs-lookup"><span data-stu-id="db8ab-118">See Also</span></span>  
 [<span data-ttu-id="db8ab-119">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="db8ab-119">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)