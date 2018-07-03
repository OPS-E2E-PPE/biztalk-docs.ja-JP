---
title: SelectiveBindingImport (アプリケーションの展開サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding files, importing
- examples, applications
- binding files, examples
- examples, importing
- applications, binding files
- applications, examples
- applications, importing
- deploying, scripts
- examples, binding files
ms.assetid: 963bfc80-8cc4-4d90-96b4-e85ae04405cf
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b289e2c37797d10e8676f2d8d948090c9eb59fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005107"
---
# <a name="selectivebindingimport-application-deployment-sample"></a><span data-ttu-id="bd89b-102">SelectiveBindingImport (アプリケーションの展開サンプル)</span><span class="sxs-lookup"><span data-stu-id="bd89b-102">SelectiveBindingImport (Application Deployment Sample)</span></span>
<span data-ttu-id="bd89b-103">このトピックでは、SelectiveBindingImport サンプルの使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-103">This topic explains how to use the SelectiveBindingImport sample.</span></span> <span data-ttu-id="bd89b-104">このサンプル スクリプトを使用すると、1 つのアプリケーションをさまざまな展開先環境にインポートするときに、異なるバインドをそのアプリケーションに適用できます。</span><span class="sxs-lookup"><span data-stu-id="bd89b-104">You can use this sample script to apply different bindings to an application when you import the application into different destination environments.</span></span> <span data-ttu-id="bd89b-105">この方法は、ネットワーク共有に格納されているバインド ファイルからバインドをインポートするときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="bd89b-105">You can use this approach when you want to import the bindings from binding files that are stored on a network share.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd89b-106">アプリケーションのインポート中にネットワーク共有からバインド ファイルを自動的にインポートする必要がない場合は、異なる展開先環境が指定されている各種のバインド ファイルをアプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="bd89b-106">If you do not need to automatically import binding files from a network share during application import, you can add to the application different binding files that have different destination environments specified.</span></span> <span data-ttu-id="bd89b-107">アプリケーションをインポートするときは、環境を指定でき、その環境のバインドが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="bd89b-107">When you import the application, you can specify the environment, and the bindings for that environment will be applied automatically.</span></span> <span data-ttu-id="bd89b-108">詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-108">For more information, see [Binding Files and Application Deployment](../core/binding-files-and-application-deployment.md).</span></span>  
  
 <span data-ttu-id="bd89b-109">BizTalk アプリケーションは、通常は開発環境からテスト環境、ステージング環境、実稼働環境へと順番に移動されます。</span><span class="sxs-lookup"><span data-stu-id="bd89b-109">BizTalk applications are typically moved from development to testing to staging and then to production environments.</span></span> <span data-ttu-id="bd89b-110">通常は、各環境で異なるバインドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd89b-110">The bindings used in different environments are typically different.</span></span> <span data-ttu-id="bd89b-111">このサンプルを使用すると、各種の環境のバインドを次のように適用できます。</span><span class="sxs-lookup"><span data-stu-id="bd89b-111">Using this sample, you can apply bindings for different environments as follows:</span></span>  
  
1.  <span data-ttu-id="bd89b-112">使用するバインド ファイルすべてをネットワーク共有に配置します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-112">Placing all the binding files that you want to use on a network share.</span></span>  
  
2.  <span data-ttu-id="bd89b-113">アプリケーションのインポート中に特定の展開先環境用の正しいバインド ファイルをこの場所からインポートするアプリケーションに、処理後のスクリプトを追加します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-113">Adding a post-processing script to the application that will import from this location the correct binding file for the particular destination environment during application import.</span></span> <span data-ttu-id="bd89b-114">スクリプトは、ローカル コンピューターに設定された %ENVIRONMENT% という環境変数を読み取って、環境を検出します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-114">The script detects the environment by reading an environment variable named %ENVIRONMENT% that you set on the local computer,</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="bd89b-115">このサンプルの処理</span><span class="sxs-lookup"><span data-stu-id="bd89b-115">What This Sample Does</span></span>  
 <span data-ttu-id="bd89b-116">このサンプルは、BizTalk アプリケーションの .msi ファイルに含まれている処理後のスクリプトを使用して、ネットワーク共有からバインド ファイルを選択的にインポートする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bd89b-116">This sample illustrates how to selectively import binding files from a network share by using a post-processing script contained in a BizTalk application .msi file.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="bd89b-117">このサンプルの場所</span><span class="sxs-lookup"><span data-stu-id="bd89b-117">Where to Find This Sample</span></span>  
 <span data-ttu-id="bd89b-118">次のサンプル フォルダーとファイルを検索する*\<サンプル パス\>* \Application Deployment\SelectiveBindingImport:</span><span class="sxs-lookup"><span data-stu-id="bd89b-118">You can find the following sample folders and files under *\<Samples Path\>* \Application Deployment\SelectiveBindingImport:</span></span>  
  
-   <span data-ttu-id="bd89b-119">Develop (フォルダー)</span><span class="sxs-lookup"><span data-stu-id="bd89b-119">Develop (Folder)</span></span>  
  
    -   <span data-ttu-id="bd89b-120">Dev.xml</span><span class="sxs-lookup"><span data-stu-id="bd89b-120">Dev.xml</span></span>  
  
-   <span data-ttu-id="bd89b-121">Production (フォルダー)</span><span class="sxs-lookup"><span data-stu-id="bd89b-121">Production (Folder)</span></span>  
  
    -   <span data-ttu-id="bd89b-122">Production.xml</span><span class="sxs-lookup"><span data-stu-id="bd89b-122">Production.xml</span></span>  
  
-   <span data-ttu-id="bd89b-123">Staging (フォルダー)</span><span class="sxs-lookup"><span data-stu-id="bd89b-123">Staging (Folder)</span></span>  
  
    -   <span data-ttu-id="bd89b-124">Staging.xml</span><span class="sxs-lookup"><span data-stu-id="bd89b-124">Staging.xml</span></span>  
  
-   <span data-ttu-id="bd89b-125">Test (フォルダー)</span><span class="sxs-lookup"><span data-stu-id="bd89b-125">Test (Folder)</span></span>  
  
    -   <span data-ttu-id="bd89b-126">Test.xml</span><span class="sxs-lookup"><span data-stu-id="bd89b-126">Test.xml</span></span>  
  
-   <span data-ttu-id="bd89b-127">SelectiveBindings.bat</span><span class="sxs-lookup"><span data-stu-id="bd89b-127">SelectiveBindings.bat</span></span>  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="bd89b-128">このサンプルの使用方法</span><span class="sxs-lookup"><span data-stu-id="bd89b-128">How to Use This Sample</span></span>  
 <span data-ttu-id="bd89b-129">次の手順に従って、このサンプルを実行します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-129">Use the following procedures to run this sample.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="bd89b-130">サンプルを実行するには</span><span class="sxs-lookup"><span data-stu-id="bd89b-130">To run the sample</span></span>  
  
1. <span data-ttu-id="bd89b-131">実行**から Build.Bat、 *\<サンプル パス\>* \Application Deployment\CreateApp**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="bd89b-131">Run **Build.Bat from the *\<Samples Path\>* \Application Deployment\CreateApp** directory.</span></span> <span data-ttu-id="bd89b-132">これで、次のファイルを作成、 *\<サンプル パス\>* \Application Deployment\CreateApp\Dlls フォルダー: Schemas.dll、Maps.dll、および Orchestrations.dll します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-132">This creates the following files in the *\<Samples Path\>* \Application Deployment\CreateApp\Dlls folder: Schemas.dll, Maps.dll, and Orchestrations.dll.</span></span>  
  
2. <span data-ttu-id="bd89b-133">**アプリケーションを作成します。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-133">**Create the application.**</span></span> <span data-ttu-id="bd89b-134">BizTalk Server 管理コンソールで必要」の説明に従って、アプリケーションを作成[アプリケーションを作成する方法](../core/how-to-create-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-134">In the BizTalk Server Administration console, create an application, as described in [How to Create an Application](../core/how-to-create-an-application.md).</span></span>  
  
3. <span data-ttu-id="bd89b-135">**.Dll ファイルが最初の手順で作成したアプリケーションを追加します。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-135">**Add to the application the .dll files created in the first step.**</span></span> <span data-ttu-id="bd89b-136">手順については、次を参照してください。[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-136">For instructions, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
4. <span data-ttu-id="bd89b-137">**次のように、環境変数を作成します。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-137">**Create the ENVIRONMENT variable, as follows:**</span></span>  
  
   1.  <span data-ttu-id="bd89b-138">[スタート] メニューを右クリックして**マイ コンピューター**クリック**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-138">On the Start menu, right-click **My Computer** and click **Properties**.</span></span>  
  
   2.  <span data-ttu-id="bd89b-139">**詳細**] タブで [**環境変数**。</span><span class="sxs-lookup"><span data-stu-id="bd89b-139">On the **Advanced** tab, click **Environment Variables**.</span></span>  
  
   3.  <span data-ttu-id="bd89b-140">**ユーザー変数**セクションで、**新規**します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-140">In the **User variables** section, click **New**.</span></span>  
  
   4.  <span data-ttu-id="bd89b-141">**変数名**、型**環境**します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-141">In **Variable name**, type **ENVIRONMENT**.</span></span>  
  
   5.  <span data-ttu-id="bd89b-142">**変数値**、環境の次の値の型:**開発**、**運用**、**ステージング**、または**テスト**します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-142">In **Variable value**, type on of the following values for the environment: **Develop**, **Production**, **Staging**, or **Test**.</span></span> <span data-ttu-id="bd89b-143">これらの値では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="bd89b-143">These values are case sensitive.</span></span>  
  
5. <span data-ttu-id="bd89b-144">クリックして**OK** 3 回です。</span><span class="sxs-lookup"><span data-stu-id="bd89b-144">Click **OK** three times.</span></span>  
  
6. <span data-ttu-id="bd89b-145">**バインド ファイルをファイル システム上の場所にコピーします。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-145">**Copy the binding files to a location on your file system.**</span></span> <span data-ttu-id="bd89b-146">Develop、Test、Staging、および Production フォルダーの .xml バインド ファイルをファイル システム内の場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="bd89b-146">Copy the binding .xml files from the Develop, Test, Staging, and Production folders to a location on your file system.</span></span>  
  
7. <span data-ttu-id="bd89b-147">**処理後のスクリプトを編集します。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-147">**Edit the post-processing script.**</span></span> <span data-ttu-id="bd89b-148">SelectiveBindings.bat を次のように編集します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-148">Edit SelectiveBindings.bat as follows:</span></span>  
  
   1.  <span data-ttu-id="bd89b-149">**バインド ファイルの場所を指定します。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-149">**Specify the binding file location.**</span></span> <span data-ttu-id="bd89b-150">BINDINGS_LOC を含んでいる行で、REM を削除し、バインド ファイルのコピー先のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-150">In the line containing BINDINGS_LOC, delete REM, and provide the path to the location where you copied the binding files.</span></span>  
  
        <span data-ttu-id="bd89b-151">例:</span><span class="sxs-lookup"><span data-stu-id="bd89b-151">Example:</span></span>  
  
        <span data-ttu-id="bd89b-152">BINDINGS_LOC=C:\MyBindings</span><span class="sxs-lookup"><span data-stu-id="bd89b-152">BINDINGS_LOC=C:\MyBindings</span></span>  
  
   2.  <span data-ttu-id="bd89b-153">**アプリケーション名を指定します。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-153">**Specify the application name.**</span></span> <span data-ttu-id="bd89b-154">APPLICATION_NAME を含んでいる行で、REM を削除し、バインドのインポート先のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-154">In the line containing APPLICATION_NAME, delete REM, and provide the name of the application into which you want to import the bindings.</span></span>  
  
        <span data-ttu-id="bd89b-155">例:</span><span class="sxs-lookup"><span data-stu-id="bd89b-155">Example:</span></span>  
  
        <span data-ttu-id="bd89b-156">APPLICATION_Name=SelectiveBindingImport</span><span class="sxs-lookup"><span data-stu-id="bd89b-156">APPLICATION_Name=SelectiveBindingImport</span></span>  
  
8. <span data-ttu-id="bd89b-157">**処理後のスクリプトとしてアプリケーションにスクリプトを追加します。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-157">**Add the script to the application as a post-processing script.**</span></span> <span data-ttu-id="bd89b-158">手順については、次を参照してください。[より前に追加する方法または処理後のスクリプトをアプリケーションに](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-158">For instructions, see [How to Add a Pre- or Post-processing Script to an Application](../core/how-to-add-a-pre-or-post-processing-script-to-an-application.md).</span></span>  
  
9. <span data-ttu-id="bd89b-159">**アプリケーションをエクスポートします。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-159">**Export the application.**</span></span> <span data-ttu-id="bd89b-160">手順については、次を参照してください。 [BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-160">For instructions, see [How to Export a BizTalk Application](../core/how-to-export-a-biztalk-application.md).</span></span>  
  
10. <span data-ttu-id="bd89b-161">**アプリケーションを削除します。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-161">**Delete the application.**</span></span> <span data-ttu-id="bd89b-162">手順については、次を参照してください。 [BizTalk グループから BizTalk アプリケーションを削除する方法](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-162">For instructions, see [How to Delete a BizTalk Application from the BizTalk Group](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md).</span></span>  
  
11. <span data-ttu-id="bd89b-163">**アプリケーションをインポートします。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-163">**Import the application.**</span></span> <span data-ttu-id="bd89b-164">手順については、次を参照してください。 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-164">For instructions, see [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span> <span data-ttu-id="bd89b-165">インポート先の環境を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bd89b-165">You do not need to specify a destination environment.</span></span>  
  
12. <span data-ttu-id="bd89b-166">**正しいバインド ファイルが適用されたことを確認します。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-166">**Verify that the right binding file was applied.**</span></span> <span data-ttu-id="bd89b-167">確認するには、受信場所の説明フィールドを次のようにチェックします。</span><span class="sxs-lookup"><span data-stu-id="bd89b-167">You can do this by checking the description field of the receive locations, as follows:</span></span>  
  
    1. <span data-ttu-id="bd89b-168">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-168">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
    2. <span data-ttu-id="bd89b-169">コンソール ツリーで、BizTalk グループ、BizTalk アプリケーション、および受信場所のフォルダーを展開します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-169">In the console tree, expand the BizTalk group, the BizTalk application, and the Receive Locations folder.</span></span>  
  
    3. <span data-ttu-id="bd89b-170">右ペインで、受信場所の説明を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-170">In the right pane, view the description of the receive locations.</span></span>  
  
13. <span data-ttu-id="bd89b-171">**アプリケーションをインストールします。**</span><span class="sxs-lookup"><span data-stu-id="bd89b-171">**Install the application.**</span></span> <span data-ttu-id="bd89b-172">手順については、次を参照してください。 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="bd89b-172">For instructions, see [How to Install a BizTalk Application](../core/how-to-install-a-biztalk-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd89b-173">参照</span><span class="sxs-lookup"><span data-stu-id="bd89b-173">See Also</span></span>  
 <span data-ttu-id="bd89b-174">[アプリケーションの展開 (BizTalk Server Samples フォルダー)](../core/application-deployment-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="bd89b-174">[Application Deployment (BizTalk Server Samples Folder)](../core/application-deployment-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="bd89b-175">BizTalk アプリケーションの展開</span><span class="sxs-lookup"><span data-stu-id="bd89b-175">Deploying BizTalk Applications</span></span>](../core/deploying-biztalk-applications.md)