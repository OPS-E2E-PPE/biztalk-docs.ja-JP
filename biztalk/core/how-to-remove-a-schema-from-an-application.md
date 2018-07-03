---
title: アプリケーションからスキーマを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, schemas
- applications, schemas
- schemas, deleting
- managing [schemas], deleting
- managing [schemas], applications
- schemas, applications
ms.assetid: 17dd5869-b56c-4166-9f02-03e04e691eda
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0693d94736c4ef3d8ad5ee561ed6b42650c90ab3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985435"
---
# <a name="how-to-remove-a-schema-from-an-application"></a><span data-ttu-id="6b1c2-102">スキーマをアプリケーションから削除する方法</span><span class="sxs-lookup"><span data-stu-id="6b1c2-102">How to Remove a Schema from an Application</span></span>
<span data-ttu-id="6b1c2-103">ここでは、BizTalk Server 管理コンソールを使用して、スキーマをアプリケーションから削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-103">This topic describes how to use the BizTalk Server Administration console to remove a schema from an application.</span></span> <span data-ttu-id="6b1c2-104">この手順では、グループの BizTalk 管理データベースからもスキーマを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-104">This procedure removes the schema from the BizTalk Management database for the group as well.</span></span> <span data-ttu-id="6b1c2-105">スキーマの新しいバージョンを展開した後にスキーマを削除する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-105">You might want to remove a schema after deploying a new version of the schema.</span></span> <span data-ttu-id="6b1c2-106">詳細とアプリケーションのアイテムを更新するための重要な考慮事項は、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-106">For more information and important considerations for updating application artifacts, see [Updating BizTalk Applications](../core/updating-biztalk-applications.md).</span></span>  
  
 <span data-ttu-id="6b1c2-107">スキーマを削除し、同じルート名前空間を持つスキーマの前のバージョンがアプリケーションに存在する場合は、前のバージョンがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-107">When you remove a schema, and a previous version of the schema having the same root namespace exists in the application, the previous version will become active.</span></span>  
  
 <span data-ttu-id="6b1c2-108">スキーマを削除すると、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-108">When you remove a schema, the following occurs:</span></span>  
  
-   <span data-ttu-id="6b1c2-109">スキーマが BizTalk 管理データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-109">The schema is deleted from the BizTalk Management database.</span></span>  
  
-   <span data-ttu-id="6b1c2-110">スキーマを含む BizTalk アセンブリも BizTalk 管理データベースから削除されますが、ローカル ファイル システムまたはグローバル アセンブリ キャッシュ (GAC) 内に存在する場合、そのアセンブリは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-110">The BizTalk assembly that contains the schema is deleted from the BizTalk Management database, but is not removed from the local file system or the global assembly cache (GAC), if it exists in these locations.</span></span>  
  
-   <span data-ttu-id="6b1c2-111">BizTalk アセンブリが削除されると、アセンブリに含まれるアイテムもすべて BizTalk 管理データベースから削除されます。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-111">As a consequence of the BizTalk assembly being deleted, all artifacts contained in the assembly are removed deleted the BizTalk Management database as well.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6b1c2-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="6b1c2-112">Prerequisites</span></span>  
 <span data-ttu-id="6b1c2-113">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-113">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="6b1c2-114">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-114">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-schema"></a><span data-ttu-id="6b1c2-115">スキーマを削除するには</span><span class="sxs-lookup"><span data-stu-id="6b1c2-115">To remove a schema</span></span>  
  
1. <span data-ttu-id="6b1c2-116">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="6b1c2-117">コンソール ツリーで、展開**BizTalk Server 管理**スキーマが含まれる BizTalk グループを削除して、スキーマを含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-117">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema to remove and the application containing the schema.</span></span>  
  
3. <span data-ttu-id="6b1c2-118">クリックして**スキーマ**、スキーマを右クリックし、クリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="6b1c2-118">Click **Schemas**, right-click the schema, and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b1c2-119">参照</span><span class="sxs-lookup"><span data-stu-id="6b1c2-119">See Also</span></span>  
 [<span data-ttu-id="6b1c2-120">スキーマの管理</span><span class="sxs-lookup"><span data-stu-id="6b1c2-120">Managing Schemas</span></span>](../core/managing-schemas.md)