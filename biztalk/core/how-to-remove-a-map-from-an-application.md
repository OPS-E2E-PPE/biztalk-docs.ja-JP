---
title: アプリケーションからマップを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, maps
- deleting, maps
- managing [maps], deleting
- managing [maps], applications
ms.assetid: 27d9bb08-36f0-46ff-ae9a-2247be6e3f96
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8863e95aabed933872edbe9a93146e59ad7480d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000099"
---
# <a name="how-to-remove-a-map-from-an-application"></a><span data-ttu-id="be4e1-102">マップをアプリケーションから削除する方法</span><span class="sxs-lookup"><span data-stu-id="be4e1-102">How to Remove a Map from an Application</span></span>
<span data-ttu-id="be4e1-103">このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk アプリケーションからマップを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be4e1-103">This topic describes how to use the BizTalk Server Administration console to remove a map from a BizTalk application.</span></span> <span data-ttu-id="be4e1-104">マップの新しいバージョンを展開した後で、マップを削除する場合があります。</span><span class="sxs-lookup"><span data-stu-id="be4e1-104">You might want to remove a map after deploying a new version of the map.</span></span> <span data-ttu-id="be4e1-105">詳細とアプリケーションのアイテムを更新するための重要な考慮事項は、[BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be4e1-105">For more information and important considerations for updating application artifacts, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="be4e1-106">マップを削除すると、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="be4e1-106">When you remove a map, the following occurs:</span></span>  
  
-   <span data-ttu-id="be4e1-107">マップが BizTalk 管理データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="be4e1-107">The map is deleted from the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="be4e1-108">マップを含む BizTalk アセンブリも BizTalk 管理データベースから削除されますが、ローカル ファイル システムまたはグローバル アセンブリ キャッシュ (GAC) 内に存在する場合、そのアセンブリは削除されません。</span><span class="sxs-lookup"><span data-stu-id="be4e1-108">The BizTalk assembly that contains the map is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
-   <span data-ttu-id="be4e1-109">BizTalk アセンブリが削除されると、アセンブリに含まれるアイテムもすべて BizTalk 管理データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="be4e1-109">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are removed deleted the BizTalk Management database as well.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be4e1-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="be4e1-110">Prerequisites</span></span>  
 <span data-ttu-id="be4e1-111">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be4e1-111">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="be4e1-112">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="be4e1-112">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-map"></a><span data-ttu-id="be4e1-113">マップを削除するには</span><span class="sxs-lookup"><span data-stu-id="be4e1-113">To remove a map</span></span>  
  
1. <span data-ttu-id="be4e1-114">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="be4e1-114">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="be4e1-115">コンソール ツリーで、展開**BizTalk Server 管理**、削除するには、マップが含まれる BizTalk グループを展開し、マップを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="be4e1-115">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the map to remove, and then expand the application containing the map.</span></span>  
  
3. <span data-ttu-id="be4e1-116">をクリックして、**マップ**フォルダーは、マップを右クリックし、順にクリックします**削除**します。</span><span class="sxs-lookup"><span data-stu-id="be4e1-116">Click the **Maps** folder, right-click the map, and then click **Remove**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be4e1-117">複数のマップを削除するには、shift キーを押しながら、削除をマップの 1 つを右クリックしてをクリックし、各マップをクリックします。**削除**します。</span><span class="sxs-lookup"><span data-stu-id="be4e1-117">To remove multiple maps, hold down the shift key, click each map to remove, right-click one of the maps, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be4e1-118">参照</span><span class="sxs-lookup"><span data-stu-id="be4e1-118">See Also</span></span>  
 <span data-ttu-id="be4e1-119">[マップの管理](../core/managing-maps.md) </span><span class="sxs-lookup"><span data-stu-id="be4e1-119">[Managing Maps](../core/managing-maps.md) </span></span>  
 <span data-ttu-id="be4e1-120">[アプリケーションから BizTalk アセンブリを削除する方法](../core/how-to-remove-a-biztalk-assembly-from-an-application.md) </span><span class="sxs-lookup"><span data-stu-id="be4e1-120">[How to Remove a BizTalk Assembly from an Application](../core/how-to-remove-a-biztalk-assembly-from-an-application.md) </span></span>  
 [<span data-ttu-id="be4e1-121">BizTalk アプリケーションの展開解除</span><span class="sxs-lookup"><span data-stu-id="be4e1-121">Undeploying BizTalk Applications</span></span>](../core/undeploying-biztalk-applications.md)