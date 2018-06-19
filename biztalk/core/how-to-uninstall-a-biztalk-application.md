---
title: BizTalk アプリケーションをアンインストールする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], uninstalling
- applications, uninstalling
- uninstalling, applications
- undeploying, uninstalling
ms.assetid: ab721c6e-194e-4b8a-bfd1-d0139d284373
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cba0c5f4ea8340612bb42c4a15257acd449848d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256842"
---
# <a name="how-to-uninstall-a-biztalk-application"></a><span data-ttu-id="eb432-102">BizTalk アプリケーションをアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="eb432-102">How to Uninstall a BizTalk Application</span></span>
<span data-ttu-id="eb432-103">このトピックでは、コントロール パネルの [プログラムの追加と削除] または BTSTask コマンド ライン ツールを使用して、BizTalk アプリケーションをアンインストールする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="eb432-103">This topic describes how to use the Add or Remove Programs control panel or the BTSTask command-line tool to uninstall a BizTalk application.</span></span> <span data-ttu-id="eb432-104">これらは、アプリケーションをアンインストールするためのサポートされているメソッドだけです。</span><span class="sxs-lookup"><span data-stu-id="eb432-104">These are the only supported methods for uninstalling an application.</span></span> <span data-ttu-id="eb432-105">BizTalk アプリケーションを更新したときなど、BizTalk 用の .msi ファイルが複数インストールされている場合、.msi ファイルをダブルクリックする方法や msiexec を使用する方法では BizTalk アプリケーションが完全にアンインストールされない可能性があります。したがって、これらのアンインストール方法はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="eb432-105">If you installed multiple .msi files for this application, for example to update the application, double-clicking the .msi file or using msiexec may not completely uninstall the application and are therefore not supported uninstallation methods.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="eb432-106">実行中の BizTalk アプリケーションをアンインストールすると、アプリケーションでエラーが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb432-106">Uninstalling a BizTalk application while it is running can cause errors in the application.</span></span> <span data-ttu-id="eb432-107">この問題を回避するために、ベスト プラクティスを確認することがあることをお勧めとしてがない実行中」の説明に従って、アプリケーションのインスタンスをサービス[すべてのサービス インスタンスの検索方法](../core/how-to-search-for-all-service-instances.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb432-107">In order to avoid this problem, as a best practice we recommend that you verify there are no running service instances for the application, as described in [How to Search for All Service Instances](../core/how-to-search-for-all-service-instances.md).</span></span> <span data-ttu-id="eb432-108">かどうか、必要に応じてを停止するアプリケーションを実行中のすべてのインスタンスを完全に停止する」の説明に従って完全停止 オプションを使用して[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb432-108">If necessary, you can stop the application by using the Full Stop option to completely stop all running instances, as described in [How to Start and Stop a BizTalk Application](../core/how-to-start-and-stop-a-biztalk-application.md).</span></span> <span data-ttu-id="eb432-109">この方法を実行すると、処理中のメッセージが完了しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="eb432-109">Be aware that when you do this, in-process messages will not complete.</span></span>  
  
 <span data-ttu-id="eb432-110">BizTalk アプリケーションをアンインストールするときは、BizTalk に関連するすべてのファイルと設定が削除されるよう、処理前および処理後のスクリプトを BizTalk アプリケーションの .msi ファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb432-110">A pre- or post-processing script should be included in the application .msi file to remove all of the files and settings associated with the application when it is uninstalled.</span></span> <span data-ttu-id="eb432-111">処理前または処理後のスクリプトを追加していない場合、このトピックの手順に従って BizTalk アプリケーションのファイルと設定をローカル ファイル システムから削除すると、次のような例外が生じます。</span><span class="sxs-lookup"><span data-stu-id="eb432-111">If a pre- or post-processing script has not been included, the procedures in this topic will remove the application's files and settings from the local file system, with the following exceptions.</span></span>  
  
-   <span data-ttu-id="eb432-112">BizTalk アプリケーションに仮想ディレクトリが含まれている場合、BizTalk アプリケーションをインストールした後で仮想ディレクトリにファイルを追加していない限り、仮想ディレクトリとそのファイルは削除されます。</span><span class="sxs-lookup"><span data-stu-id="eb432-112">If the application includes a virtual directory, the virtual directory and its files are deleted, unless files were added to the virtual directory after the application was installed.</span></span> <span data-ttu-id="eb432-113">アプリケーションをインストールした後で仮想ディレクトリにファイルを追加した場合は、仮想ディレクトリも追加したファイルも削除されません。</span><span class="sxs-lookup"><span data-stu-id="eb432-113">In this case, the virtual directory and the added files are not deleted.</span></span> <span data-ttu-id="eb432-114">仮想ディレクトリと追加ファイルを削除する場合は、明示的に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb432-114">If you want to delete the virtual directory and the added files, you must do so explicitly.</span></span>  
  
-   <span data-ttu-id="eb432-115">処理前および処理後のスクリプトは削除されますが、インストール時またはアンインストール時にスクリプトによって追加されたファイルは削除されず、スクリプトによって実行されたアクションが取り消されることもありません。</span><span class="sxs-lookup"><span data-stu-id="eb432-115">Pre- and post-processing scripts are deleted, but any files added by the scripts during installation or uninstallation are not deleted, nor are any actions taken by the scripts undone.</span></span> <span data-ttu-id="eb432-116">スクリプトが追加したファイルを削除する場合、またはスクリプトのアクションを取り消す場合は、明示的に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb432-116">If you want to delete files added by scripts or undo their actions, you must do so explicitly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eb432-117">アプリケーションのインポート時に、展開プロパティでインポート先が指定されていた処理前または処理後のスクリプトだけが、アンインストール中に実行されます。</span><span class="sxs-lookup"><span data-stu-id="eb432-117">Only pre-or post-processing scripts that have a destination location specified in its deployment properties when the application is imported will run during uninstallation.</span></span> <span data-ttu-id="eb432-118">詳細については、次を参照してください。[前に追加する方法または処理後のスクリプトをアプリケーションに](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb432-118">For more information, see [How to Add a Pre- or Post-processing Script to an Application](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span></span>  
  
-   <span data-ttu-id="eb432-119">BizTalk アプリケーションのアンインストール時に証明書は削除されません。</span><span class="sxs-lookup"><span data-stu-id="eb432-119">Certificates are never deleted when you uninstall a BizTalk application.</span></span> <span data-ttu-id="eb432-120">証明書を削除する場合は、明示的に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb432-120">If you want to delete a certificate, you must do so explicitly.</span></span> <span data-ttu-id="eb432-121">また、コンポーネントは Windows レジストリから削除されず、BizTalk アセンブリはグローバル アセンブリ キャッシュ (GAC) から削除されません。</span><span class="sxs-lookup"><span data-stu-id="eb432-121">In addition, components are not removed from the Windows Registry and BizTalk assemblies are not removed from the global assembly cache (GAC).</span></span> <span data-ttu-id="eb432-122">これらを削除する場合は、明示的に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb432-122">If you want to remove them, you must do so explicitly.</span></span> <span data-ttu-id="eb432-123">詳細については、次を参照してください。[するその他のファイルを削除すると、BizTalk アプリケーションの設定方法](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb432-123">For more information, see [How to Remove Other Files and Settings for a BizTalk Application](../core/how-to-remove-other-files-and-settings-for-a-biztalk-application.md).</span></span>  
  
 <span data-ttu-id="eb432-124">アンインストールの完了前にアンインストール操作を取り消すと、BizTalk Server はアンインストールをロールバックします。ただし、操作の取り消し前に処理前および処理後のスクリプトによって実行されたアクションはロールバックされません。</span><span class="sxs-lookup"><span data-stu-id="eb432-124">If you cancel the uninstallation operation before it completes, BizTalk Server will roll back the uninstallation, except for any actions that were taken by pre- or post-processing scripts before the operation was canceled.</span></span> <span data-ttu-id="eb432-125">アンインストールを開始する前の状態にアプリケーションを復元するには、.msi ファイルをダブルクリックして、アプリケーションを再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="eb432-125">To restore the application to its state before you started the uninstallation, double-click the .msi file and reinstall the application.</span></span> <span data-ttu-id="eb432-126">アプリケーションに対して複数の .msi ファイルがインストールされている場合、アプリケーションを再インストールするには、.msi ファイルが最初にインストールされた順序で各 .msi ファイルをダブルクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb432-126">If multiple .msi files have been installed for this application, you should double-click each .msi file to reinstall the application in the order in which the .msi files were originally installed.</span></span>  
  
 <span data-ttu-id="eb432-127">処理後のスクリプトの詳細については、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb432-127">For more information about post-processing scripts, see [Using Pre- and Post-processing Scripts to Customize Application Deployment](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb432-128">BizTalk アプリケーションを完全に展開解除、する必要がありますも削除する BizTalk グループから」の説明に従って[BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb432-128">To completely undeploy a BizTalk application, you must also delete it from the BizTalk group, as described in [How to Delete a BizTalk Application from the BizTalk Group](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="eb432-129">前提条件</span><span class="sxs-lookup"><span data-stu-id="eb432-129">Prerequisites</span></span>  
 <span data-ttu-id="eb432-130">このトピックの手順を実行するには、適切なアクセス許可でログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb432-130">To perform the procedures in this topic, you must be logged on with appropriate permissions.</span></span> <span data-ttu-id="eb432-131">詳細については、次を参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="eb432-131">For more information, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-uninstall-a-biztalk-application"></a><span data-ttu-id="eb432-132">BizTalk アプリケーションをアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="eb432-132">To uninstall a BizTalk application</span></span>  
  
#### <a name="using-uninstall-or-change-a-program"></a><span data-ttu-id="eb432-133">プログラムのアンインストールまたは変更を使用する場合</span><span class="sxs-lookup"><span data-stu-id="eb432-133">Using Uninstall or change a program</span></span>  
  
1.  <span data-ttu-id="eb432-134">コンピューターでアプリケーションを実行して、をクリックして**開始**、] をクリックして**コントロール パネルの [**、順にダブルクリック**プログラムと機能**します。</span><span class="sxs-lookup"><span data-stu-id="eb432-134">On the computer running the application, click **Start**, click **Control Panel**, and then double-click  **Programs and Features**.</span></span>  
  
2.  <span data-ttu-id="eb432-135">[**のアンインストールと変更プログラム**] ページで、削除、およびをクリックする BizTalk アプリケーションを右クリックして**アンインストール**です。</span><span class="sxs-lookup"><span data-stu-id="eb432-135">On **Uninstall or change a program** page, right-click the BizTalk application to remove, and then click **Uninstall**.</span></span>  
  
     <span data-ttu-id="eb432-136">Windows インストーラーによって、指定したアプリケーションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="eb432-136">Windows Installer removes the specified application.</span></span>  
  
3.  <span data-ttu-id="eb432-137">複数のコンピューターでアプリケーションを実行している場合は、それぞれのコンピューターで上記の手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb432-137">If the application is running on multiple computers, repeat these steps on each computer.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="eb432-138">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="eb432-138">Using the command line</span></span>  
  
1.  <span data-ttu-id="eb432-139">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="eb432-139">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="eb432-140">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="eb432-140">Type the following command, substituting the appropriate value, as described in the following table:</span></span>  
  
     <span data-ttu-id="eb432-141">**BTSTask UninstallApp** [**/applicationname は:***値*]</span><span class="sxs-lookup"><span data-stu-id="eb432-141">**BTSTask UninstallApp** [**/ApplicationName:***value*]</span></span>  
  
     <span data-ttu-id="eb432-142">例:</span><span class="sxs-lookup"><span data-stu-id="eb432-142">Example:</span></span>  
  
     <span data-ttu-id="eb432-143">**Applicationname: myapplication BTSTask UninstallApp**</span><span class="sxs-lookup"><span data-stu-id="eb432-143">**BTSTask UninstallApp /ApplicationName:MyApplication**</span></span>  
  
    |<span data-ttu-id="eb432-144">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eb432-144">Parameter</span></span>|<span data-ttu-id="eb432-145">値</span><span class="sxs-lookup"><span data-stu-id="eb432-145">Value</span></span>|  
    |---------------|-----------|  
    |<span data-ttu-id="eb432-146">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="eb432-146">**/ApplicationName**</span></span>|<span data-ttu-id="eb432-147">アンインストールする BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="eb432-147">Name of the BizTalk application to uninstall.</span></span> <span data-ttu-id="eb432-148">名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb432-148">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb432-149">参照</span><span class="sxs-lookup"><span data-stu-id="eb432-149">See Also</span></span>  
 <span data-ttu-id="eb432-150">[BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md) </span><span class="sxs-lookup"><span data-stu-id="eb432-150">[Undeploying BizTalk Applications](../core/undeploying-biztalk-applications.md) </span></span>  
 [<span data-ttu-id="eb432-151">UninstallApp コマンド</span><span class="sxs-lookup"><span data-stu-id="eb432-151">UninstallApp Command</span></span>](../core/uninstallapp-command.md)