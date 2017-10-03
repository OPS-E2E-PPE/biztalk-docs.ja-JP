---
title: "証明書を割り当てる方法、受信場所 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 54ae300e-62c5-480f-a9b7-e5c3457a0f80
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94554aa5781ed609e5129d58ab75e5709e432278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-a-certificate-to-a-receive-location"></a><span data-ttu-id="6d926-102">受信場所に証明書を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="6d926-102">How to Assign a Certificate to a Receive Location</span></span>
<span data-ttu-id="6d926-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所にセキュリティ証明書を割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d926-103">This topic describes how to use the BizTalk Server Administration console to assign a security certificate to a receive location.</span></span> <span data-ttu-id="6d926-104">この手順は、双方向の受信場所に対してのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="6d926-104">You can perform this procedure on a two-way receive location only.</span></span> <span data-ttu-id="6d926-105">証明書は、BizTalk Server が実行されているコンピューターの "その他のユーザー" 証明書ストアに格納しておく必要があります。それ以外の場合、この受信場所に関連付けられているメッセージは処理されずにエラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="6d926-105">The certificate must exist in the Other People certificate store on the computer running BizTalk Server, or messages associated with this receive location will not be processed, and errors will be logged.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6d926-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="6d926-106">Prerequisites</span></span>  
 <span data-ttu-id="6d926-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d926-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6d926-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="6d926-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-assign-a-certificate-to-a-receive-location"></a><span data-ttu-id="6d926-109">受信場所に証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="6d926-109">To assign a certificate to a receive location</span></span>  
  
1.  <span data-ttu-id="6d926-110">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="6d926-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6d926-111">コンソール ツリーで、BizTalk グループを展開し、受信場所に証明書を割り当てる BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="6d926-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to assign a certificate to a receive location.</span></span>  
  
3.  <span data-ttu-id="6d926-112">展開**受信場所**、受信場所を右クリックし、をクリックして**プロパティ**、クリックして**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="6d926-112">Expand **Receive Locations**, right-click the receive location, click **Properties**, and then click **Certificate**.</span></span>  
  
4.  <span data-ttu-id="6d926-113">ローカル コンピューターの証明書が存在する場合にをクリックして**参照**、[参照] を割り当てるには、この証明書を受信場所をクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6d926-113">If the certificate exists on the local computer, click **Browse**, browse to the certificate that you want to assign to this receive location, and then click **OK**.</span></span> <span data-ttu-id="6d926-114">それ以外の場合は、この手順を省略して次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="6d926-114">Otherwise, skip this step.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d926-115">リモート コンピューターからこの操作を実行する場合は、ローカル コンピューターだけではなく、BizTalk Server を実行するコンピューターにも証明書が存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6d926-115">If you are performing this operation from a remote computer, make sure that the certificate exists on the computer running BizTalk Server, and not only on the local computer.</span></span> <span data-ttu-id="6d926-116">そうでない場合、受信場所はメッセージを処理できません。</span><span class="sxs-lookup"><span data-stu-id="6d926-116">Otherwise, the receive location will not be able to process messages.</span></span>  
  
5.  <span data-ttu-id="6d926-117">かどうか、証明書が、ローカル コンピューター上にありません、**拇印**ボックスに入力し、証明書の拇印を貼り付け、またはをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6d926-117">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="6d926-118">証明書の拇印の形式は、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH です。H は 16 進数です。</span><span class="sxs-lookup"><span data-stu-id="6d926-118">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d926-119">参照</span><span class="sxs-lookup"><span data-stu-id="6d926-119">See Also</span></span>  
 [<span data-ttu-id="6d926-120">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="6d926-120">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)