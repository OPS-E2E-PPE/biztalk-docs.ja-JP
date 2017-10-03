---
title: "送信ポートから証明書を削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, certificates
- managing [send ports], certificates
- certificates, deleting
- deleting, certificates
ms.assetid: fd93a83f-c2aa-4de2-9996-4ca4ec6d4a4c
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5193b1b6003660aac0e0b427da0f0a338b56d8ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-certificate-from-a-send-port"></a><span data-ttu-id="032b8-102">送信ポート グループから証明書を削除する方法</span><span class="sxs-lookup"><span data-stu-id="032b8-102">How to Remove a Certificate from a Send Port</span></span>
<span data-ttu-id="032b8-103">このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートからセキュリティ証明書を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="032b8-103">This topic describes how to use the BizTalk Server Administration console to remove a security certificate from a send port.</span></span> <span data-ttu-id="032b8-104">この操作を実行すると、送信ポートではメッセージが暗号化されなくなり、メッセージはクリア テキストで送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="032b8-104">When you do this, the send port will no longer encrypt messages; messages will be sent in clear text.</span></span> <span data-ttu-id="032b8-105">証明書を送信ポートから削除しても、証明書ストアからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="032b8-105">Removing a certificate from a send port does not remove it from the certificate store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="032b8-106">アプリケーション開発者が開発プロセス中にセキュリティ証明書を送信ポートから削除するには、このトピックの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="032b8-106">The application developer can remove a security certificate from a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="032b8-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="032b8-107">Prerequisites</span></span>  
 <span data-ttu-id="032b8-108">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="032b8-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="032b8-109">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="032b8-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-certificate-from-a-send-port"></a><span data-ttu-id="032b8-110">送信ポートから証明書を削除するには</span><span class="sxs-lookup"><span data-stu-id="032b8-110">To remove a certificate from a send port</span></span>  
  
1.  <span data-ttu-id="032b8-111">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="032b8-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="032b8-112">コンソール ツリーで、BizTalk グループを展開し、送信ポートから証明書を削除する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="032b8-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to remove a certificate from a send port.</span></span>  
  
3.  <span data-ttu-id="032b8-113">展開**送信ポート**、送信ポートを右クリックし、をクリックして**プロパティ**、クリックして**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="032b8-113">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="032b8-114">をクリックして**削除証明書**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="032b8-114">Click **Remove certificate**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="032b8-115">参照</span><span class="sxs-lookup"><span data-stu-id="032b8-115">See Also</span></span>  
 [<span data-ttu-id="032b8-116">作成して、送信ポートの構成</span><span class="sxs-lookup"><span data-stu-id="032b8-116">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)