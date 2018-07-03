---
title: ロール リンクの管理 |Microsoft Docs
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
ms.openlocfilehash: e31ec8af7f8c5dd785b471654e9a9cfd7446bbf3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998947"
---
# <a name="manage-role-links"></a><span data-ttu-id="dfb90-102">ロール リンクを管理します。</span><span class="sxs-lookup"><span data-stu-id="dfb90-102">Manage Role Links</span></span>

## <a name="overview"></a><span data-ttu-id="dfb90-103">概要</span><span class="sxs-lookup"><span data-stu-id="dfb90-103">Overview</span></span>
<span data-ttu-id="dfb90-104">このセクションでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して BizTalk アプリケーションのロール リンクを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dfb90-104">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to manage role links in a BizTalk application.</span></span> <span data-ttu-id="dfb90-105">ロール リンクとは、企業間取引にかかわるパーティ間の関係を定義し、両方向の連携に使用されるメッセージとポートの種類を指定するものです。</span><span class="sxs-lookup"><span data-stu-id="dfb90-105">A role link defines the relationship between parties involved in a business transaction and specifies the message and port types used in the interaction in both directions.</span></span> <span data-ttu-id="dfb90-106">ロール リンクの背景については、次を参照してください。[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="dfb90-106">For background information on role links, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  

## <a name="added-to-application"></a><span data-ttu-id="dfb90-107">アプリケーションに追加</span><span class="sxs-lookup"><span data-stu-id="dfb90-107">Added to application</span></span>  
 <span data-ttu-id="dfb90-108">ロール リンクは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、BizTalk アセンブリとしてビルドおよびコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="dfb90-108">Role links are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="dfb90-109">ロール リンクを単独でアプリケーションに追加することはできません。ロール リンクは次のようにしてアプリケーションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="dfb90-109">You cannot add role links to an application individually; a role link is added to an application as follows:</span></span>  
  
- <span data-ttu-id="dfb90-110">」の説明に従って、アプリケーションにロール リンクを含む BizTalk アセンブリを追加するときに[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="dfb90-110">When you add a BizTalk assembly containing a role link to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="dfb90-111">」の説明に従って、ロール リンクを含む BizTalk アセンブリを含むアプリケーションを .msi ファイルをインポートする[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="dfb90-111">When you import an .msi file into an application that includes a BizTalk assembly containing a role link, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="dfb90-112">開発者が展開したときに、アプリケーションからのロール リンクを含むアセンブリ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="dfb90-112">When a developer deploys into an application an assembly containing a role link from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  

## <a name="deploy-to-production"></a><span data-ttu-id="dfb90-113">運用環境にデプロイします。</span><span class="sxs-lookup"><span data-stu-id="dfb90-113">Deploy to production</span></span>  
 <span data-ttu-id="dfb90-114">BizTalk アプリケーションの開発者は、ロール リンクを作成することにより、企業間取引にかかわる複数のパーティ間 (企業とその業者など) の通信を実装します。</span><span class="sxs-lookup"><span data-stu-id="dfb90-114">The BizTalk application developer creates role links to implement communications between two or more parties involved in a business transaction, such as your organization and a supplier.</span></span> <span data-ttu-id="dfb90-115">開発者が指定するのはロールだけでよく、取引にかかわるパーティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dfb90-115">The developer does not necessarily specify the parties that are involved in the transaction, only their roles.</span></span> <span data-ttu-id="dfb90-116">ロール リンクを含むアプリケーションを実稼働環境に展開し、パーティ間の実際の通信を有効にするには、このセクションに書かれた手順に従い、次の構成作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfb90-116">To deploy an application that includes a role link to a production environment and enable actual communication between the parties, the following configuration must be performed, as described in this section:</span></span>  
  
- <span data-ttu-id="dfb90-117">ロール リンクに定義された各ロールにパーティを割り当てる (開発プロセス中に行っていない場合)。</span><span class="sxs-lookup"><span data-stu-id="dfb90-117">If it wasn't done during the development process, a party must be assigned to each role defined in the role link.</span></span> <span data-ttu-id="dfb90-118">これを、ロールに対してパーティを "参加させる" と言います。</span><span class="sxs-lookup"><span data-stu-id="dfb90-118">This is called "enlisting" a party for a role.</span></span> <span data-ttu-id="dfb90-119">後で割り当てが不要になった場合は、そのパーティの参加をロールから解除することもできます。</span><span class="sxs-lookup"><span data-stu-id="dfb90-119">You can later unenlist the party if you no longer want the party to have the assigned role.</span></span>  
  
- <span data-ttu-id="dfb90-120">ロール リンクに定義された各パーティの論理ポートを、アプリケーションがホストされる BizTalk ホスト インスタンスの物理的ポートにバインドする。</span><span class="sxs-lookup"><span data-stu-id="dfb90-120">The logical ports for each party defined within the role link must be bound to physical ports on the BizTalk host instances that will host the application.</span></span>  
  
  <span data-ttu-id="dfb90-121">ロール リンクの開発に関する詳細については、次を参照してください。[オーケストレーションでロール リンクを使用して](../core/using-role-links-in-orchestrations.md)します。</span><span class="sxs-lookup"><span data-stu-id="dfb90-121">For more information about developing role links, see [Using Role Links in Orchestrations](../core/using-role-links-in-orchestrations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfb90-122">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="dfb90-122">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="dfb90-123">WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="dfb90-123">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="dfb90-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="dfb90-124">Next step</span></span>
  
-   [<span data-ttu-id="dfb90-125">参加またはロールに対してパーティを参加解除する方法</span><span class="sxs-lookup"><span data-stu-id="dfb90-125">How to Enlist or Unenlist a Party for a Role</span></span>](../core/how-to-enlist-or-unenlist-a-party-for-a-role.md)