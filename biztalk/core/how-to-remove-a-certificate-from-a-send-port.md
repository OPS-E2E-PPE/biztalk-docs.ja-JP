---
title: 送信ポートから証明書を削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, certificates
- managing [send ports], certificates
- certificates, deleting
- deleting, certificates
ms.assetid: fd93a83f-c2aa-4de2-9996-4ca4ec6d4a4c
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0cee3cb77368b8128ad5be66e4628f9c693f71c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335096"
---
# <a name="how-to-remove-a-certificate-from-a-send-port"></a><span data-ttu-id="3afe0-102">送信ポートから証明書を削除する方法</span><span class="sxs-lookup"><span data-stu-id="3afe0-102">How to Remove a Certificate from a Send Port</span></span>
<span data-ttu-id="3afe0-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートからセキュリティ証明書を削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="3afe0-103">This topic describes how to use the BizTalk Server Administration console to remove a security certificate from a send port.</span></span> <span data-ttu-id="3afe0-104">これを行うときに、送信ポートのメッセージが暗号化されなくメッセージは、クリア テキストで送信されます。</span><span class="sxs-lookup"><span data-stu-id="3afe0-104">When you do this, the send port will no longer encrypt messages; messages will be sent in clear text.</span></span> <span data-ttu-id="3afe0-105">送信ポートから証明書の削除は削除されません証明書ストアから。</span><span class="sxs-lookup"><span data-stu-id="3afe0-105">Removing a certificate from a send port does not remove it from the certificate store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3afe0-106">アプリケーション開発者から削除できますセキュリティ証明書を送信ポートを開発プロセス中にこのトピックの手順を使用しています。</span><span class="sxs-lookup"><span data-stu-id="3afe0-106">The application developer can remove a security certificate from a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3afe0-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="3afe0-107">Prerequisites</span></span>  
 <span data-ttu-id="3afe0-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3afe0-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="3afe0-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="3afe0-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-certificate-from-a-send-port"></a><span data-ttu-id="3afe0-110">送信ポートから証明書を削除するには</span><span class="sxs-lookup"><span data-stu-id="3afe0-110">To remove a certificate from a send port</span></span>  
  
1. <span data-ttu-id="3afe0-111">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="3afe0-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="3afe0-112">コンソール ツリーで、BizTalk グループと、送信ポートから証明書を削除する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="3afe0-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to remove a certificate from a send port.</span></span>  
  
3. <span data-ttu-id="3afe0-113">展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**証明書**します。</span><span class="sxs-lookup"><span data-stu-id="3afe0-113">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Certificates**.</span></span>  
  
4. <span data-ttu-id="3afe0-114">クリックして**証明書の削除**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="3afe0-114">Click **Remove certificate**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3afe0-115">参照</span><span class="sxs-lookup"><span data-stu-id="3afe0-115">See Also</span></span>  
 [<span data-ttu-id="3afe0-116">送信ポートの作成および構成</span><span class="sxs-lookup"><span data-stu-id="3afe0-116">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)