---
title: 送信ポートに証明書を割り当てる方法 |Microsoft ドキュメント
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
ms.openlocfilehash: ec19c845c6b0cfb5d19bd7a961fe9ddfbcf2a3d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247482"
---
# <a name="how-to-assign-a-certificate-to-a-send-port"></a><span data-ttu-id="6fc07-102">送信ポートに証明書を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="6fc07-102">How to Assign a Certificate to a Send Port</span></span>
<span data-ttu-id="6fc07-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートにセキュリティ証明書を割り当てる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fc07-103">This topic describes how to use the BizTalk Server Administration console to assign a security certificate to a send port.</span></span> <span data-ttu-id="6fc07-104">証明書は、BizTalk Server が実行されているコンピューターの "その他のユーザー" 証明書ストアに格納しておく必要があります。それ以外の場合、この送信ポートに関連付けられているメッセージは処理されずにエラーが記録されます。</span><span class="sxs-lookup"><span data-stu-id="6fc07-104">The certificate must exist in the Other People certificate store on the computer running BizTalk Server, or messages associated with this send port will not be processed, and errors will be logged.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6fc07-105">アプリケーション開発者が開発プロセス中にセキュリティ証明書を送信ポートに割り当てるには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6fc07-105">The application developer can assign a security certificate to a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6fc07-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="6fc07-106">Prerequisites</span></span>  
 <span data-ttu-id="6fc07-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fc07-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6fc07-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="6fc07-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-assign-a-certificate-to-a-send-port"></a><span data-ttu-id="6fc07-109">送信ポートに証明書を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="6fc07-109">To assign a certificate to a send port</span></span>  
  
1.  <span data-ttu-id="6fc07-110">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="6fc07-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6fc07-111">コンソール ツリーで、BizTalk グループを展開し、送信ポートに証明書を割り当てる BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="6fc07-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to assign a certificate to a send port.</span></span>  
  
3.  <span data-ttu-id="6fc07-112">展開**送信ポート**、送信ポートを右クリックし、をクリックして**プロパティ**、クリックして**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="6fc07-112">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Certificate**.</span></span>  
  
4.  <span data-ttu-id="6fc07-113">証明書がローカル コンピューターに存在する場合にクリックして**参照**、この送信ポートに割り当てるし、をクリックする証明書を参照**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6fc07-113">If the certificate exists on the local computer, click **Browse**, browse to the certificate that you want to assign to this send port, and then click **OK**.</span></span> <span data-ttu-id="6fc07-114">それ以外の場合は、この手順を省略して次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="6fc07-114">Otherwise, skip this step.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fc07-115">証明書がローカル コンピューターに存在する場合でも、BizTalk Server の実行されているコンピューターが別にある場合は、そのコンピューターにも証明書が存在している必要があります。BizTalk Server の実行されているコンピューターに証明書がないと、送信ポートがメッセージを処理できません。</span><span class="sxs-lookup"><span data-stu-id="6fc07-115">Even if the certificate exists on the local computer, it must also exist on the computer running BizTalk Server, if different, before the send port will be able to process messages.</span></span>  
  
5.  <span data-ttu-id="6fc07-116">かどうか、証明書が、ローカル コンピューター上にありません、**拇印**ボックスに入力し、証明書の拇印を貼り付け、またはをクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="6fc07-116">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="6fc07-117">証明書の拇印の形式は、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH です。H は 16 進数です。</span><span class="sxs-lookup"><span data-stu-id="6fc07-117">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc07-118">参照</span><span class="sxs-lookup"><span data-stu-id="6fc07-118">See Also</span></span>  
 [<span data-ttu-id="6fc07-119">作成して、送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="6fc07-119">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)