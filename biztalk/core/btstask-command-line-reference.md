---
title: "BTSTask コマンド ライン リファレンス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c350695-13e9-441a-9f1e-03cdc3e41328
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c2de1e2e616b57d0cc8eda0cb9de9eae5c72d26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="btstask-command-line-reference"></a><span data-ttu-id="cecb2-102">BTSTask コマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="cecb2-102">BTSTask Command-Line Reference</span></span>
<span data-ttu-id="cecb2-103">このセクションの各トピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に付属する BTSTask コマンドライン ツールのリファレンス情報を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="cecb2-103">The topics in this section provide reference information for the BTSTask command-line tool included with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="cecb2-104">BTSTask を使用すると、さまざまなアプリケーション展開作業をコマンド ラインから実行できます。その例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cecb2-104">You can use BTSTask to perform many application deployment tasks from the command line, as follows:</span></span>  
  
-   <span data-ttu-id="cecb2-105">BizTalk アプリケーションを AddApp コマンドで BizTalk 管理データベースに追加する。</span><span class="sxs-lookup"><span data-stu-id="cecb2-105">Add a BizTalk application to the BizTalk Management database by using the AddApp command.</span></span>  
  
-   <span data-ttu-id="cecb2-106">AddResource コマンドでアプリケーションにアイテムを追加する。</span><span class="sxs-lookup"><span data-stu-id="cecb2-106">Add an artifact to an application by using the AddResource command.</span></span>  
  
-   <span data-ttu-id="cecb2-107">アプリケーションとそのアイテムを ExportApp コマンドで .msi ファイルにエクスポートする。</span><span class="sxs-lookup"><span data-stu-id="cecb2-107">Export an application and its artifacts to an .msi file by using the ExportApp command.</span></span>  
  
-   <span data-ttu-id="cecb2-108">バインド情報を ExportBindings コマンドで .xml ファイルにエクスポートする。</span><span class="sxs-lookup"><span data-stu-id="cecb2-108">Export binding information to an .xml file by using the ExportBindings command.</span></span>  
  
-   <span data-ttu-id="cecb2-109">ImportApp コマンドを使用して、.msi ファイルからアプリケーションをインポートする。</span><span class="sxs-lookup"><span data-stu-id="cecb2-109">Import an application from an .msi file by using the ImportApp command.</span></span>  
  
-   <span data-ttu-id="cecb2-110">ImportBindings コマンドを使用して、.xml ファイルからバインド情報をインポートする。</span><span class="sxs-lookup"><span data-stu-id="cecb2-110">Import binding information from an .xml file by using the ImportBindings command.</span></span>  
  
-   <span data-ttu-id="cecb2-111">ListApp コマンドを使用して、アプリケーションに含まれるアイテムを、ローカル一意識別子 (LUID) と共に一覧表示する。</span><span class="sxs-lookup"><span data-stu-id="cecb2-111">List the artifacts included in an application along with their locally unique identifiers (LUIDs) by using the ListApp command.</span></span>  
  
-   <span data-ttu-id="cecb2-112">特定の BizTalk グループを対象に、BizTalk 管理データベース内のすべてのアプリケーションを、ListApps コマンドを使用して一覧表示する。</span><span class="sxs-lookup"><span data-stu-id="cecb2-112">List all applications in the BizTalk Management database for the BizTalk group by using the ListApps command.</span></span>  
  
-   <span data-ttu-id="cecb2-113">ListPackage コマンドを使用して、.msi ファイル内のリソースを一覧表示する。</span><span class="sxs-lookup"><span data-stu-id="cecb2-113">List the resources in an .msi file by using the ListPackage command.</span></span>  
  
-   <span data-ttu-id="cecb2-114">ListTypes コマンドを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がサポートしているアイテムの種類をすべて一覧表示する。</span><span class="sxs-lookup"><span data-stu-id="cecb2-114">List all of the artifact types supported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] by using the ListTypes command.</span></span>  
  
-   <span data-ttu-id="cecb2-115">RemoveApp コマンドを使用して、BizTalk 管理データベースおよび BizTalk 管理コンソールからアプリケーションを削除する。</span><span class="sxs-lookup"><span data-stu-id="cecb2-115">Remove an application from the BizTalk Management database and the BizTalk Administration console by using the RemoveApp command.</span></span>  
  
-   <span data-ttu-id="cecb2-116">RemoveResource コマンドを使用して、アプリケーションからアイテムを削除する。</span><span class="sxs-lookup"><span data-stu-id="cecb2-116">Remove an artifact from an application by using the RemoveResource command.</span></span>  
  
-   <span data-ttu-id="cecb2-117">UninstallApp コマンドを使用して、アプリケーションをローカル コンピューターからアンインストールする。</span><span class="sxs-lookup"><span data-stu-id="cecb2-117">Uninstall an application from the local computer by using the UninstallApp command.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cecb2-118">アプリケーションのインポート中に実行される処理前/処理後スクリプトで BTSTask コマンドを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="cecb2-118">You cannot use BTSTask commands in a preprocessing or postprocessing script that will run during application import.</span></span> <span data-ttu-id="cecb2-119">使用すると、インポートに失敗する場合があります。</span><span class="sxs-lookup"><span data-stu-id="cecb2-119">If you do, the import may fail.</span></span> <span data-ttu-id="cecb2-120">スクリプトからは、インポート中に行われた変更を認識できないためです。</span><span class="sxs-lookup"><span data-stu-id="cecb2-120">This is because changes being made during import are not visible to scripts.</span></span>  
  
 <span data-ttu-id="cecb2-121">また、BTSTask の使用時に、コンソールの前景色を変更する方法を確認しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cecb2-121">In addition, you can learn how to edit the console foreground colors for BTSTask.</span></span> <span data-ttu-id="cecb2-122">コンソールの背景色が白だと、BTSTask コンソールの出力が読みづらくなってしまうため、前景色の変更が必要になります。</span><span class="sxs-lookup"><span data-stu-id="cecb2-122">If your console background color is white, you will have difficulty reading the BTSTask console output and will need to modify the console foreground colors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cecb2-123">スクリプトの実行が完了すると、成功の場合はゼロ (0) が、失敗の場合はゼロ以外の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="cecb2-123">When a script completes, it returns a zero (0) to indicate successful completion or a non-zero number to indicate failure.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cecb2-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="cecb2-124">In This Section</span></span>  
  
-   [<span data-ttu-id="cecb2-125">AddApp コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-125">AddApp Command</span></span>](../core/addapp-command.md)  
  
-   [<span data-ttu-id="cecb2-126">AddResource コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-126">AddResource Command</span></span>](../core/addresource-command.md)  
  
-   [<span data-ttu-id="cecb2-127">ExportApp コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-127">ExportApp Command</span></span>](../core/exportapp-command.md)  
  
-   [<span data-ttu-id="cecb2-128">ExportBindings コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-128">ExportBindings Command</span></span>](../core/exportbindings-command.md)  

- [<span data-ttu-id="cecb2-129">ExportParties コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-129">ExportParties Command</span></span>](../core/exportparties-command.md)

- [<span data-ttu-id="cecb2-130">ExportSettings コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-130">ExportSettings Command</span></span>](../core/exportsettings-command.md)
  
-   [<span data-ttu-id="cecb2-131">ImportApp コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-131">ImportApp Command</span></span>](../core/importapp-command.md)  
  
-   [<span data-ttu-id="cecb2-132">ImportBindings コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-132">ImportBindings Command</span></span>](../core/importbindings-command.md)  

- [<span data-ttu-id="cecb2-133">ImportParties コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-133">ImportParties Command</span></span>](../core/importparties-command.md)

- [<span data-ttu-id="cecb2-134">ImportSettings コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-134">ImportSettings Command</span></span>](../core/importsettings-command.md)
  
-   [<span data-ttu-id="cecb2-135">ListApp コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-135">ListApp Command</span></span>](../core/listapp-command.md)  
  
-   [<span data-ttu-id="cecb2-136">ListApps コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-136">ListApps Command</span></span>](../core/listapps-command.md)  
  
-   [<span data-ttu-id="cecb2-137">ListPackage コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-137">ListPackage Command</span></span>](../core/listpackage-command.md)  
  
-   [<span data-ttu-id="cecb2-138">ListTypes コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-138">ListTypes Command</span></span>](../core/listtypes-command.md)  
  
-   [<span data-ttu-id="cecb2-139">RemoveApp コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-139">RemoveApp Command</span></span>](../core/removeapp-command.md)  
  
-   [<span data-ttu-id="cecb2-140">RemoveResource コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-140">RemoveResource Command</span></span>](../core/removeresource-command.md)  
  
-   [<span data-ttu-id="cecb2-141">UninstallApp コマンド</span><span class="sxs-lookup"><span data-stu-id="cecb2-141">UninstallApp Command</span></span>](../core/uninstallapp-command.md)  
  
-   [<span data-ttu-id="cecb2-142">BTSTask のコンソールの色を編集する方法</span><span class="sxs-lookup"><span data-stu-id="cecb2-142">How to Edit the Console Colors for BTSTask</span></span>](../core/how-to-edit-the-console-colors-for-btstask.md)