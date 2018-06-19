---
title: ロール リンクの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8860e11-3d2c-450f-a7d2-cc116478999c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07f85bfe0d16b3963b0ba18585220f508f679346
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262634"
---
# <a name="manage-role-links"></a><span data-ttu-id="ee56f-102">ロール リンクを管理します。</span><span class="sxs-lookup"><span data-stu-id="ee56f-102">Manage Role Links</span></span>

## <a name="overview"></a><span data-ttu-id="ee56f-103">概要</span><span class="sxs-lookup"><span data-stu-id="ee56f-103">Overview</span></span>
<span data-ttu-id="ee56f-104">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk アプリケーションのロール リンクを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee56f-104">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage role links in a BizTalk application.</span></span> <span data-ttu-id="ee56f-105">ロール リンクとは、企業間取引にかかわるパーティ間の関係を定義し、両方向の連携に使用されるメッセージとポートの種類を指定するものです。</span><span class="sxs-lookup"><span data-stu-id="ee56f-105">A role link defines the relationship between parties involved in a business transaction and specifies the message and port types used in the interaction in both directions.</span></span> <span data-ttu-id="ee56f-106">ロール リンクの背景情報については、次を参照してください。[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="ee56f-106">For background information on role links, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  

## <a name="added-to-application"></a><span data-ttu-id="ee56f-107">アプリケーションに追加</span><span class="sxs-lookup"><span data-stu-id="ee56f-107">Added to application</span></span>  
 <span data-ttu-id="ee56f-108">ロール リンクは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk アセンブリとしてビルドおよびコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="ee56f-108">Role links are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="ee56f-109">ロール リンクを単独でアプリケーションに追加することはできません。ロール リンクは次のようにしてアプリケーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ee56f-109">You cannot add role links to an application individually; a role link is added to an application as follows:</span></span>  
  
-   <span data-ttu-id="ee56f-110">」の説明に従って、アプリケーションにロール リンクを含む BizTalk アセンブリを追加すると[BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="ee56f-110">When you add a BizTalk assembly containing a role link to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
-   <span data-ttu-id="ee56f-111">」の説明に従って、ロール リンクを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートしたとき[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="ee56f-111">When you import an .msi file into an application that includes a BizTalk assembly containing a role link, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
-   <span data-ttu-id="ee56f-112">開発者が展開したときにアプリケーションから、ロール リンクを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="ee56f-112">When a developer deploys into an application an assembly containing a role link from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  

## <a name="deploy-to-production"></a><span data-ttu-id="ee56f-113">実稼働環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="ee56f-113">Deploy to production</span></span>  
 <span data-ttu-id="ee56f-114">BizTalk アプリケーションの開発者は、ロール リンクを作成することにより、企業間取引にかかわる複数のパーティ間 (企業とその業者など) の通信を実装します。</span><span class="sxs-lookup"><span data-stu-id="ee56f-114">The BizTalk application developer creates role links to implement communications between two or more parties involved in a business transaction, such as your organization and a supplier.</span></span> <span data-ttu-id="ee56f-115">開発者が指定するのはロールだけでよく、取引にかかわるパーティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ee56f-115">The developer does not necessarily specify the parties that are involved in the transaction, only their roles.</span></span> <span data-ttu-id="ee56f-116">ロール リンクを含むアプリケーションを実稼働環境に展開し、パーティ間の実際の通信を有効にするには、このセクションに書かれた手順に従い、次の構成作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee56f-116">To deploy an application that includes a role link to a production environment and enable actual communication between the parties, the following configuration must be performed, as described in this section:</span></span>  
  
-   <span data-ttu-id="ee56f-117">ロール リンクに定義された各ロールにパーティを割り当てる (開発プロセス中に行っていない場合)。</span><span class="sxs-lookup"><span data-stu-id="ee56f-117">If it wasn't done during the development process, a party must be assigned to each role defined in the role link.</span></span> <span data-ttu-id="ee56f-118">これを、ロールに対してパーティを "参加させる" と言います。</span><span class="sxs-lookup"><span data-stu-id="ee56f-118">This is called "enlisting" a party for a role.</span></span> <span data-ttu-id="ee56f-119">後で割り当てが不要になった場合は、そのパーティの参加をロールから解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="ee56f-119">You can later unenlist the party if you no longer want the party to have the assigned role.</span></span>  
  
-   <span data-ttu-id="ee56f-120">ロール リンクに定義された各パーティの論理ポートを、アプリケーションがホストされる BizTalk ホスト インスタンスの物理的ポートにバインドする。</span><span class="sxs-lookup"><span data-stu-id="ee56f-120">The logical ports for each party defined within the role link must be bound to physical ports on the BizTalk host instances that will host the application.</span></span>  
  
 <span data-ttu-id="ee56f-121">ロール リンクの開発に関する詳細については、次を参照してください。[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)です。</span><span class="sxs-lookup"><span data-stu-id="ee56f-121">For more information about developing role links, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee56f-122">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="ee56f-122">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="ee56f-123">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="ee56f-123">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="ee56f-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="ee56f-124">Next step</span></span>
  
-   [<span data-ttu-id="ee56f-125">参加させる、またはロールに対してパーティを参加解除する方法</span><span class="sxs-lookup"><span data-stu-id="ee56f-125">How to Enlist or Unenlist a Party for a Role</span></span>](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)