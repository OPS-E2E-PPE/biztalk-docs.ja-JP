---
title: "BizTalk アセンブリの管理 |Microsoft ドキュメント"
description: "BizTalk Server で、追加、更新、依存関係の表示、およびアセンブリの削除を含むアセンブリと共に動作へのリンク"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62cc92f5-a1ea-46e4-88e6-b8a71a0c40a2
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c0dc8e74e23c7dc0b3a4e7a62a76297988b6b2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="manage-biztalk-assemblies"></a><span data-ttu-id="0265e-103">BizTalk アセンブリを管理します。</span><span class="sxs-lookup"><span data-stu-id="0265e-103">Manage BizTalk Assemblies</span></span>

## <a name="overview"></a><span data-ttu-id="0265e-104">概要</span><span class="sxs-lookup"><span data-stu-id="0265e-104">Overview</span></span>
<span data-ttu-id="0265e-105">ここでは、BizTalk グループに BizTalk アセンブリを展開した後、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは BTSTask コマンドライン ツールを使用して BizTalk アセンブリを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0265e-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console or the BTSTask command-line tool to manage BizTalk assemblies after they have been deployed into a BizTalk group.</span></span> <span data-ttu-id="0265e-106">BizTalk アセンブリは、オーケストレーション、パイプライン、スキーマ、マップなど、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ビジネス ソリューションで使用するリソース情報を集めて格納した Microsoft Windows の DLL ファイルです。</span><span class="sxs-lookup"><span data-stu-id="0265e-106">A BizTalk assembly is a Microsoft Windows DLL file that contains resource information, such as orchestrations, pipelines, schemas, and maps to be used in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] business solution.</span></span> <span data-ttu-id="0265e-107">BizTalk アセンブリの背景情報については、次を参照してください。 [BizTalk アセンブリ](../core/biztalk-assemblies.md)です。</span><span class="sxs-lookup"><span data-stu-id="0265e-107">For background information on BizTalk assemblies, see [BizTalk Assemblies](../core/biztalk-assemblies.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0265e-108">プロパティ スキーマの展開または展開解除は機密データの公開につながる可能性があり、追跡時に機密情報が公開されてしまう可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="0265e-108">Deploying or undeploying a property schema may expose sensitive data, and subsequently expose sensitive information during tracking.</span></span> <span data-ttu-id="0265e-109">プロパティ スキーマが含まれているアセンブリを展開または展開解除すると、必ずイベント ビューアーによってイベントが Windows アプリケーション イベント ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="0265e-109">Whenever an assembly containing a property schema is deployed or undeployed, the event viewer logs an event in the Windows Application Event Log.</span></span> <span data-ttu-id="0265e-110">イベント ログに記録されているメッセージを調べて、すべてのアセンブリ展開アクティビティが機密データに関するポリシーに従っていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0265e-110">You should check the event log for these messages to ensure that all assembly deployment activities are in line with your policies for any sensitive data.</span></span> <span data-ttu-id="0265e-111">(展開に関してイベント ログに生成されるメッセージ:「ユーザー「{1}」には、"{0}"プロパティのスキーマを含んでいるアセンブリが展開されている」です。</span><span class="sxs-lookup"><span data-stu-id="0265e-111">(The message generated to the Event Log for deployment is: "The user "{1}" deployed the assembly "{0}" containing property schemas."</span></span> <span data-ttu-id="0265e-112">展開解除に関してイベント ログに生成されるメッセージ:「「{1}」ユーザーは、"{0}"プロパティのスキーマを含んでいるアセンブリを展開解除」です)。</span><span class="sxs-lookup"><span data-stu-id="0265e-112">The message generated to the Event Log for undeployment is: "The user "{1}" undeployed the assembly "{0}" containing property schemas.")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0265e-113">Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。</span><span class="sxs-lookup"><span data-stu-id="0265e-113">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="0265e-114">WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0265e-114">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="0265e-115">開発者は、使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、BizTalk アセンブリを開発する[BizTalk Server アプリケーションの開発](../core/developing-biztalk-server-applications.md)からに展開できると[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]」の説明に従って[を展開します。BizTalk アプリケーションに Visual Studio から BizTalk アセンブリ](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="0265e-115">The developer uses [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] to develop BizTalk assemblies, as described in [Developing BizTalk Server Applications](../core/developing-biztalk-server-applications.md), and can deploy them from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span> <span data-ttu-id="0265e-116">また、開発者は、このセクションで説明する管理コンソールを使用して、開発プロセス中に BizTalk アセンブリを管理できます。</span><span class="sxs-lookup"><span data-stu-id="0265e-116">The developer can also manage BizTalk assemblies during the development process by using either the administration console, as described in this section.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0265e-117">次の手順</span><span class="sxs-lookup"><span data-stu-id="0265e-117">Next steps</span></span> 
  
-   [<span data-ttu-id="0265e-118">BizTalk アセンブリをアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="0265e-118">Add a BizTalk Assembly to an Application</span></span>](../core/how-to-add-a-biztalk-assembly-to-an-application.md)  
  
-   [<span data-ttu-id="0265e-119">BizTalk アセンブリの展開オプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="0265e-119">Modify the Deployment Options of a BizTalk Assembly</span></span>](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)  
  
-   [<span data-ttu-id="0265e-120">BizTalk アセンブリの依存関係を表示します。</span><span class="sxs-lookup"><span data-stu-id="0265e-120">View the Dependencies for a BizTalk Assembly</span></span>](../core/how-to-view-the-dependencies-for-a-biztalk-assembly.md)  
  
-   [<span data-ttu-id="0265e-121">BizTalk アセンブリをアプリケーションから削除します。</span><span class="sxs-lookup"><span data-stu-id="0265e-121">Remove a BizTalk Assembly from an Application</span></span>](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)