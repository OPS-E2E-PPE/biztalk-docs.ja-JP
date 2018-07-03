---
title: 別のアプリケーションへの参照を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, referencing
ms.assetid: 6a177560-ee1f-403a-a68a-ade409a39a35
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6781ebc9c6cb0c3f7c68dfbbcff683193e15ac15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018553"
---
# <a name="how-to-add-a-reference-to-another-application"></a><span data-ttu-id="4b131-102">他のアプリケーションへの参照を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4b131-102">How to Add a Reference to Another Application</span></span>
<span data-ttu-id="4b131-103">このトピックでは、BizTalk Server 管理コンソールを使用して、1 つのアプリケーションから別のアプリケーションへの参照を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b131-103">This topic describes how to use the BizTalk Server Administration console to add a reference from one application to another application.</span></span> <span data-ttu-id="4b131-104">」の説明に従って、インポート ウィザードを使用して、アプリケーションをインポートするときに、その他のアプリケーションへの参照を追加することも[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b131-104">You can also add a reference to the other application when you import your application by using the Import Wizard, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="4b131-105">同じ BizTalk グループの別のアプリケーション内に既に存在するアイテムを、現在のアプリケーションで使用する場合は、参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b131-105">You add a reference when you want to use an artifact in the current application that already exists in another application in the same BizTalk group.</span></span> <span data-ttu-id="4b131-106">これは、ほとんどの種類のアイテムが BizTalk グループ内で一意である必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="4b131-106">This is because most types of artifacts must be unique in a BizTalk group.</span></span> <span data-ttu-id="4b131-107">現在のアプリケーションに重複するアイテムを追加するのではなく、既にこのアイテムを含んでいる他のアプリケーションへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b131-107">Rather than adding the duplicate artifact to the current application, you add a reference to the other application that already contains the artifact.</span></span> <span data-ttu-id="4b131-108">詳細については、次を参照してください。[成果物をする必要がありますする内で一意で、アプリケーションまたはグループ](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b131-108">For more information, see [Artifacts That Must Be Unique in an Application or Group](../core/artifacts-that-must-be-unique-in-an-application-or-group.md).</span></span>  
  
 <span data-ttu-id="4b131-109">仮想ディレクトリを使用する場合、または別のアプリケーションに既に存在する証明書を使用する場合は、参照を追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4b131-109">It is not necessary to add a reference when you want to use a virtual directory or a certificate that already exists in another application.</span></span> <span data-ttu-id="4b131-110">さらに、これらの場合は循環参照が作成される可能性があるため、参照を追加しないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4b131-110">Furthermore, we recommend against doing this because it can create a circular reference.</span></span>  
  
 <span data-ttu-id="4b131-111">依存関係のあるアプリケーションをインポートする場合は、参照もインポートできます。</span><span class="sxs-lookup"><span data-stu-id="4b131-111">When you import an application that has dependencies, references can be imported as well.</span></span> <span data-ttu-id="4b131-112">別のアプリケーションへの参照を追加すると、両方のアプリケーションの展開方法に影響することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b131-112">When adding a reference to another application, bear in mind that this affects the way you deploy both applications.</span></span> <span data-ttu-id="4b131-113">詳細については、次を参照してください。[依存関係とアプリケーションの展開](../core/dependencies-and-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b131-113">For more information, see [Dependencies and Application Deployment](../core/dependencies-and-application-deployment.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4b131-114">前提条件</span><span class="sxs-lookup"><span data-stu-id="4b131-114">Prerequisites</span></span>  
 <span data-ttu-id="4b131-115">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b131-115">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="4b131-116">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="4b131-116">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-add-a-reference-to-another-application"></a><span data-ttu-id="4b131-117">別のアプリケーションへの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="4b131-117">To add a reference to another application</span></span>  
  
1. <span data-ttu-id="4b131-118">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="4b131-118">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="4b131-119">コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]] を展開し、参照を作成するアプリケーションを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4b131-119">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and right-click the application in which you want to create a reference.</span></span> <span data-ttu-id="4b131-120">これは、別のアプリケーションに含まれているアイテムを使用するアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="4b131-120">This is the application in which you want to use an artifact that is contained in another application.</span></span>  
  
3. <span data-ttu-id="4b131-121">をポイント**追加**し**参照**します。</span><span class="sxs-lookup"><span data-stu-id="4b131-121">Point to **Add** and then click **References**.</span></span>  
  
4. <span data-ttu-id="4b131-122">**アプリケーション**、(、または使用する複数のアイテムを格納しているアプリケーション) の参照を追加するアプリケーションの順にクリックします チェック ボックスをオンに**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4b131-122">In **Applications**, select the check box of the application to which you want to add a reference (the application containing the artifact or artifacts that you want to use), and then click **OK**.</span></span>  
  
    <span data-ttu-id="4b131-123">参照が現在のアプリケーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="4b131-123">The reference is added to the current application.</span></span> <span data-ttu-id="4b131-124">コンソール ツリーで、このアプリケーションから参照したアプリケーションに、他の 1 つ以上のアプリケーションから参照されていることを示す手の形のアイコンが追加されます。</span><span class="sxs-lookup"><span data-stu-id="4b131-124">In the console tree, a hand icon is added to the application that you referred from this application to indicate that it is referenced by one or more other applications.</span></span>  
  
    <span data-ttu-id="4b131-125">![共有アプリケーション アイコン](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")</span><span class="sxs-lookup"><span data-stu-id="4b131-125">![Shared application icon](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b131-126">参照</span><span class="sxs-lookup"><span data-stu-id="4b131-126">See Also</span></span>  
 [<span data-ttu-id="4b131-127">BizTalk アプリケーションの作成と変更</span><span class="sxs-lookup"><span data-stu-id="4b131-127">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)