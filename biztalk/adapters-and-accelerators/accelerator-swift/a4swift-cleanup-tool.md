---
title: "A4SWIFT クリーンアップ ツール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: A4SWIFT Cleanup tool
ms.assetid: e694f824-6097-4d60-bc7b-b4f1a40acea0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b2d0e251bf5e8a4169ff0d86cc6635944ca12e1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="a4swift-cleanup-tool"></a><span data-ttu-id="a1769-102">A4SWIFT クリーンアップ ツール</span><span class="sxs-lookup"><span data-stu-id="a1769-102">A4SWIFT Cleanup Tool</span></span>
<span data-ttu-id="a1769-103">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]クリーンアップ ツールを持つサーバーを準備することができます、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]の新規インストール用にインストールされている[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="a1769-103">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] cleanup tool enables you to prepare a server that has the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] installed on it for a new installation of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="a1769-104">ツールは、契約、部門、およびビジネス ルール エンジン (BRE) ポリシーなど、A4SWIFT の成果物を削除し、アセンブリの展開を解除します。</span><span class="sxs-lookup"><span data-stu-id="a1769-104">The tool removes A4SWIFT artifacts such as agreements, departments, and Business Rule Engine (BRE) policies, and undeploys assemblies.</span></span> <span data-ttu-id="a1769-105">ツールを実行して、A4SWIFT の多くのアイテムを手動で削除されないようにすることができます、展開解除が参照されるアセンブリを他のアセンブリからの問題が解決します。</span><span class="sxs-lookup"><span data-stu-id="a1769-105">Running the tool enables you to avoid manually removing many A4SWIFT artifacts, and resolves problems with undeploying assemblies that might be referenced from other assemblies.</span></span>  
  
 <span data-ttu-id="a1769-106">クリーンアップ ツールを実行するときに、成果物を削除した後、コンピューター (既定)、またはアンインストール A4SWIFT にインストールされている A4SWIFT のままの選択肢がありません。</span><span class="sxs-lookup"><span data-stu-id="a1769-106">When you run the cleanup tool, you have the choice of leaving A4SWIFT installed on the computer (the default), or uninstalling A4SWIFT after removing the artifacts.</span></span> <span data-ttu-id="a1769-107">A4SWIFT をアンインストールする前に、ツールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1769-107">You should run the tool before uninstalling A4SWIFT.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a1769-108">運用環境では、A4SWIFT クリーンアップ ツールを使わないでください。</span><span class="sxs-lookup"><span data-stu-id="a1769-108">Do not use the A4SWIFT cleanup tool in a production environment.</span></span> <span data-ttu-id="a1769-109">このツールはマルチ サーバー展開ではなく、単一サーバーの開発環境で使用するものです。</span><span class="sxs-lookup"><span data-stu-id="a1769-109">The tool is intended to be used in a single-server development environment, not in a multiserver deployment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1769-110">既定では、クリーンアップ ツール機能しません、他の言語が英語以外の。</span><span class="sxs-lookup"><span data-stu-id="a1769-110">By default, the cleanup tool does not work for any other language than English.</span></span> <span data-ttu-id="a1769-111">クリーンアップ ツールは、ローカライズされたコンピューターで動作するように環境を変更することができます、ただし、します。</span><span class="sxs-lookup"><span data-stu-id="a1769-111">You can, however, modify the environment so that the cleanup tool works on a localized computer.</span></span> <span data-ttu-id="a1769-112">FormPublish ツールを実行して、t パラメーターとテンプレート ドキュメント ライブラリのローカライズされた文字列と**t:VorLagen**ドイツ語の環境でします。</span><span class="sxs-lookup"><span data-stu-id="a1769-112">Run the FormPublish tool with the t parameter and the localized string for the Templates document library, for example, **t:VorLagen** in a German environment.</span></span> <span data-ttu-id="a1769-113">クリーンアップ ツールは、ローカライズされた環境で実行できます。</span><span class="sxs-lookup"><span data-stu-id="a1769-113">You can then run the cleanup tool in a localized environment.</span></span>  
  
 <span data-ttu-id="a1769-114">次では true、クリーンアップ ツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="a1769-114">The following must be true for the cleanup tool to run:</span></span>  
  
-   <span data-ttu-id="a1769-115">メンバーである必要がある必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者グループ。</span><span class="sxs-lookup"><span data-stu-id="a1769-115">You must be a member the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators groups.</span></span>  
  
-   [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]<span data-ttu-id="a1769-116">ツールを実行するサーバーにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1769-116"> must be installed on the server on which you run the tool.</span></span>  
  
-   <span data-ttu-id="a1769-117">MrsrConfiguration.dll、Shared.dll、および RuleEngineExtension.dll はツールを実行するサーバーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1769-117">MrsrConfiguration.dll, Shared.dll, and RuleEngineExtension.dll must be deployed on the server on which you run the tool.</span></span>  
  
## <a name="what-the-cleanup-tool-does"></a><span data-ttu-id="a1769-118">クリーンアップ ツールの実行内容</span><span class="sxs-lookup"><span data-stu-id="a1769-118">What the cleanup tool does</span></span>  
 <span data-ttu-id="a1769-119">A4SWIFT のクリーンアップ ツールでは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1769-119">The A4SWIFT cleanup tool performs the following operations:</span></span>  
  
-   <span data-ttu-id="a1769-120">実行**BM が展開解除**ForActivities.xml および MRSRBAM.xml に対する</span><span class="sxs-lookup"><span data-stu-id="a1769-120">Runs **BM Undeploy** against ForActivities.xml and MRSRBAM.xml</span></span>  
  
-   <span data-ttu-id="a1769-121">存在する場合、FrrActivities_ConnectionStrings.xml と MRSRActivities_ConnectionStrings.xml ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="a1769-121">Removes the FrrActivities_ConnectionStrings.xml and MRSRActivities_ConnectionStrings.xml files, if they exist</span></span>  
  
-   <span data-ttu-id="a1769-122">存在する場合は、A4SWIFT 2.1 を削除 (にサーバーをアップグレードした場合[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]が、セットアップがインストールされている A4SWIFT 2.1 を左) および A4SWIFT 2.1 フォルダーを削除</span><span class="sxs-lookup"><span data-stu-id="a1769-122">Removes A4SWIFT 2.1 if it exists (if you have upgraded the server to [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)], but Setup has left A4SWIFT 2.1 installed) and deletes the A4SWIFT 2.1 folder</span></span>  
  
-   <span data-ttu-id="a1769-123">A4SWIFT のすべてのアセンブリを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="a1769-123">Undeploys all A4SWIFT assemblies</span></span>  
  
-   <span data-ttu-id="a1769-124">A4SWIFT の管理者グループと、A4SWIFT Users グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="a1769-124">Deletes the A4SWIFT Administrator group and the A4SWIFT Users group</span></span>  
  
-   <span data-ttu-id="a1769-125">A4SWIFT データベースを削除します</span><span class="sxs-lookup"><span data-stu-id="a1769-125">Deletes the A4SWIFT database</span></span>  
  
-   <span data-ttu-id="a1769-126">A4SWIFT の仮想ディレクトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="a1769-126">Deletes the A4SWIFT virtual directory</span></span>  
  
-   <span data-ttu-id="a1769-127">完全なサイレント アンインストールを実行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]を削除し、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]フォルダー (選択した場合)</span><span class="sxs-lookup"><span data-stu-id="a1769-127">Runs a complete silent uninstall of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] and deletes the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] folder (if selected)</span></span>  
  
 <span data-ttu-id="a1769-128">成果物を削除し、アセンブリを展開解除、クリーンアップ ツールもは次のとおり</span><span class="sxs-lookup"><span data-stu-id="a1769-128">As it removes artifacts and undeploys assemblies, the cleanup tool also does the following:</span></span>  
  
-   <span data-ttu-id="a1769-129">実行するためにインターネット インフォメーション サービス (IIS) 管理サービスを開始します</span><span class="sxs-lookup"><span data-stu-id="a1769-129">Starts Internet Information Services (IIS) Admin Service in order to run</span></span>  
  
-   <span data-ttu-id="a1769-130">停止し、MSSQLSERVER、SQLSERVERAGENT、BizTalk、およびエンタープライズ シングル サインオン サービスを再起動</span><span class="sxs-lookup"><span data-stu-id="a1769-130">Stops and then restarts the MSSQLSERVER, SQLSERVERAGENT, BizTalk, and Enterprise Single Sign-On services</span></span>  
  
#### <a name="to-run-the-a4swift-cleanup-tool"></a><span data-ttu-id="a1769-131">A4SWIFT のクリーンアップ ツールを実行するには</span><span class="sxs-lookup"><span data-stu-id="a1769-131">To run the A4SWIFT cleanup tool</span></span>  
  
1.  <span data-ttu-id="a1769-132">A4SWIFT のクリーンアップ ツールを実行する前に、A4SWIFT の既定のアセンブリのいずれかを参照する他のプロジェクトを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="a1769-132">Prior to running the A4SWIFT cleanup tool, undeploy any project that refers to any of the A4SWIFT default assemblies.</span></span>  
  
2.  <span data-ttu-id="a1769-133">コマンド プロンプトを開きに移動\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for swift \sdk\tools です。</span><span class="sxs-lookup"><span data-stu-id="a1769-133">Open a command prompt and move to \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\Tools.</span></span>  
  
3.  <span data-ttu-id="a1769-134">型**A4SWIFTCleanupTool.exe**キーを押します**ENTER**です。</span><span class="sxs-lookup"><span data-stu-id="a1769-134">Type **A4SWIFTCleanupTool.exe** and then press **ENTER**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1769-135">A4SWIFTCleanupTool.exe を最初に実行すると、ヘルプ画面を表示され、パラメーターを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a1769-135">When you initially run A4SWIFTCleanupTool.exe, the tool displays a help screen, and prompts you to enter a parameter.</span></span> <span data-ttu-id="a1769-136">このツールは、パラメーターを入力するまでは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a1769-136">The tool will not run until you enter the parameter.</span></span>  
  
4.  <span data-ttu-id="a1769-137">ツールを実行するアクションに応じて、次のキーのいずれかを押すと**ENTER**:</span><span class="sxs-lookup"><span data-stu-id="a1769-137">Depending upon the actions that you want the tool to take, press one of the following keys, and then press **ENTER**:</span></span>  
  
    -   <span data-ttu-id="a1769-138">**0**の (既定) が実行されるアクションがありません</span><span class="sxs-lookup"><span data-stu-id="a1769-138">**0** for no actions taken (the default)</span></span>  
  
    -   <span data-ttu-id="a1769-139">**1**仮想ディレクトリとレジストリ設定を含め、コンピューター上のすべてのローカル A4SWIFT リソースを削除するには</span><span class="sxs-lookup"><span data-stu-id="a1769-139">**1** to remove all the local A4SWIFT resources on the computer, including the virtual directory and registry settings</span></span>  
  
    -   <span data-ttu-id="a1769-140">**2**を Sharepoint Web フォルダー、FIN メッセージ テンプレート、BRE ポリシーとボキャブラリ、BizTalk アイテム、および A4SWIFT データベースを含む BizTalk Server グループ上のすべての共有 A4SWIFT リソースを削除するには</span><span class="sxs-lookup"><span data-stu-id="a1769-140">**2** to remove all the shared A4SWIFT resources on the BizTalk Server group, including Sharepoint Web folders, FIN message templates, BRE policies and vocabularies, BizTalk artifacts, and the A4SWIFT database</span></span>  
  
    -   <span data-ttu-id="a1769-141">**3**すべてのローカルと共有リソースを削除するには</span><span class="sxs-lookup"><span data-stu-id="a1769-141">**3** to remove all the local and shared resources</span></span>  
  
    -   <span data-ttu-id="a1769-142">**4**すべてのローカルと共有リソースを削除すると、アンインストール、[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]製品です。</span><span class="sxs-lookup"><span data-stu-id="a1769-142">**4** to remove all the local and shared resources and uninstall the [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] product.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1769-143">参照</span><span class="sxs-lookup"><span data-stu-id="a1769-143">See Also</span></span>  
 [<span data-ttu-id="a1769-144">ツール</span><span class="sxs-lookup"><span data-stu-id="a1769-144">Tools</span></span>](../../adapters-and-accelerators/accelerator-swift/tools.md)