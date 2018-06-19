---
title: 証明書を削除する方法、受信場所 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 717d41bf-4260-4df4-9d0a-07243bb9b12c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e70cd846c364d52544bf8504d42132dd35fe65d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254538"
---
# <a name="how-to-remove-a-certificate-from-a-receive-location"></a><span data-ttu-id="336bb-102">受信場所から証明書を削除する方法</span><span class="sxs-lookup"><span data-stu-id="336bb-102">How to Remove a Certificate from a Receive Location</span></span>
<span data-ttu-id="336bb-103">このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所からセキュリティ証明書を削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="336bb-103">This topic describes how to use the BizTalk Server Administration console to remove a security certificate from a receive location.</span></span> <span data-ttu-id="336bb-104">この操作を実行すると、受信場所ではメッセージが暗号化されなくなり、メッセージはクリア テキストで送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="336bb-104">When you do this, the receive location will no longer encrypt messages; messages will be sent in clear text.</span></span> <span data-ttu-id="336bb-105">証明書を受信場所から削除しても、証明書ストアからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="336bb-105">Removing a certificate from a receive location does not remove it from the certificate store.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="336bb-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="336bb-106">Prerequisites</span></span>  
 <span data-ttu-id="336bb-107">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="336bb-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="336bb-108">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="336bb-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-certificate-from-a-receive-location"></a><span data-ttu-id="336bb-109">受信場所から証明書を削除するには</span><span class="sxs-lookup"><span data-stu-id="336bb-109">To remove a certificate from a receive location</span></span>  
  
1.  <span data-ttu-id="336bb-110">をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="336bb-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="336bb-111">コンソール ツリーで、BizTalk グループを展開し、受信場所から証明書を削除する BizTalk アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="336bb-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to remove a certificate from a receive location.</span></span>  
  
3.  <span data-ttu-id="336bb-112">展開**受信場所**、受信場所を右クリックし、をクリックして**プロパティ**、クリックして**証明書**です。</span><span class="sxs-lookup"><span data-stu-id="336bb-112">Expand **Receive Locations**, right-click the receive location, click **Properties**, and then click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="336bb-113">をクリックして**削除証明書**、クリックして **[ok]** です。</span><span class="sxs-lookup"><span data-stu-id="336bb-113">Click **Remove certificate**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="336bb-114">参照</span><span class="sxs-lookup"><span data-stu-id="336bb-114">See Also</span></span>  
 [<span data-ttu-id="336bb-115">受信場所の管理</span><span class="sxs-lookup"><span data-stu-id="336bb-115">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)