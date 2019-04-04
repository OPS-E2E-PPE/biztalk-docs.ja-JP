---
title: アプリケーションにファイルを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [applications], adding files
- files, adding to applications
- managing [resources], adding files
ms.assetid: 6665b946-113a-4026-a0a3-6b67ede4b689
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f07991c8ecb85f21eed4cf6fb59d11d3f6f15e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007675"
---
# <a name="how-to-add-a-file-to-an-application"></a><span data-ttu-id="1a3fd-102">アプリケーションにファイルを追加する方法</span><span class="sxs-lookup"><span data-stu-id="1a3fd-102">How to Add a File to an Application</span></span>
<span data-ttu-id="1a3fd-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンド ラインを使用して、BizTalk アプリケーションにファイルを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-103">This topic describes how to use the BizTalk Server Administration console or the command line to add a file to a BizTalk application.</span></span> <span data-ttu-id="1a3fd-104">アプリケーションをインストールすると、アプリケーションに追加するファイルはインストール フォルダーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-104">Files that you add to your application are copied to the installation folder when the application is installed.</span></span> <span data-ttu-id="1a3fd-105">ファイルをアプリケーションの .msi ファイルにエクスポートして、アプリケーションと共にさまざまな環境に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-105">Files can also can be exported into the application's .msi file and moved to different deployment environments with the application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a3fd-106">Readme ファイルを追加する方法の詳細については、[Readme ファイルへのリンク方法](../core/how-to-link-to-a-readme-file.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-106">For instructions on adding a Readme file, see [How to Link to a Readme File](../core/how-to-link-to-a-readme-file.md).</span></span>  
  
 <span data-ttu-id="1a3fd-107">アプリケーションに既に存在するファイルを上書きするには、[上書き] オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-107">If you want to overwrite a file that already exists in the application, specify the Overwrite option.</span></span> <span data-ttu-id="1a3fd-108">[上書き] オプションは、両方のファイルが同じ名前の場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-108">The overwrite option only works when both files have the same file name.</span></span> <span data-ttu-id="1a3fd-109">このオプションを指定しなかった場合、追加するファイルと同じ名前のファイルが既にアプリケーションに存在すると、追加操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-109">If not specified, and a file already exists in the application with the same file name as the one being added, the add operation will fail.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1a3fd-110">他の種類のアイテムとは異なり、BizTalk グループ内の複数のファイルに同じ名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-110">Unlike some other types of artifacts, you can have more than one file having the same file name in a BizTalk group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1a3fd-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="1a3fd-111">Prerequisites</span></span>  
 <span data-ttu-id="1a3fd-112">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-112">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="1a3fd-113">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-113">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-add-a-file-to-an-application"></a><span data-ttu-id="1a3fd-114">アプリケーションにファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="1a3fd-114">To add a file to an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="1a3fd-115">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="1a3fd-115">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="1a3fd-116">クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-116">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="1a3fd-117">コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、ファイルを追加するアプリケーションが含まれる BizTalk グループの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-117">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] and the BizTalk Group containing the application to which you want to add the file.</span></span>  
  
3. <span data-ttu-id="1a3fd-118">[アプリケーション] を展開し、ファイルを追加するアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-118">Expand Applications and the application to which you want to add a file.</span></span>  
  
4. <span data-ttu-id="1a3fd-119">右クリックし、**リソース**フォルダーをポイントして**追加**、 をクリックし、**リソース**します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-119">Right-click the **Resources** folder, point to **Add**, and then click **Resources**.</span></span>  
  
5. <span data-ttu-id="1a3fd-120">クリックして**追加**ファイルを選択し、クリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-120">Click **Add**, select the file, and then click **Open**.</span></span>  
  
6. <span data-ttu-id="1a3fd-121">**ファイルの種類**ドロップダウン リストで、 **System.BizTalk:File**します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-121">In the **File type** drop-down list, select **System.BizTalk:File**.</span></span>  
  
7. <span data-ttu-id="1a3fd-122">**先**ファイル名を含む .msi ファイルから、アプリケーションのインストール時にコピーするファイルのある場所の完全なパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-122">In **Destination**, type the full path of the location where the file is to be copied when the application is installed from the .msi file, including the file name.</span></span> <span data-ttu-id="1a3fd-123">既定値は、アプリケーションのインストール フォルダー、%BTAD_InstallDir% です。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-123">The default is %BTAD_InstallDir%, the application installation folder.</span></span> <span data-ttu-id="1a3fd-124">このパスを指定しないと、インストールでローカル ファイル システムにファイルがコピーされません。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-124">If this path is not provided, the file is not copied to the local file system during installation.</span></span>  
  
8. <span data-ttu-id="1a3fd-125">完了したら、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-125">When finished, click **OK**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="1a3fd-126">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="1a3fd-126">Using the command line</span></span>  
  
1. <span data-ttu-id="1a3fd-127">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-127">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="1a3fd-128">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-128">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="1a3fd-129">**BTSTask AddResource** [**/applicationname は:**<em>値</em>] **/Type:System.BizTalk:File** **[/overwrite]** **/Source:**<em>値</em>[**/Destination:**<em>値</em>] [**/Server:** <em>値</em>] [**/database:**<em>値</em>]</span><span class="sxs-lookup"><span data-stu-id="1a3fd-129">**BTSTask AddResource** [**/ApplicationName:**<em>value</em>] **/Type:System.BizTalk:File** [**/Overwrite**] **/Source:**<em>value</em> [**/Destination:**<em>value</em>] [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="1a3fd-130">例:</span><span class="sxs-lookup"><span data-stu-id="1a3fd-130">Example:</span></span>  
  
    <span data-ttu-id="1a3fd-131">**BTSTask AddResource applicationname: myapplication/Type:System.BizTalk:File/overwrite/Source:"C:\Source Files\File.txt"/Destination:"C:\New Files\File.txt"/Server:MyDatabaseServer/Database:BizTalkMgmtDb**</span><span class="sxs-lookup"><span data-stu-id="1a3fd-131">**BTSTask AddResource /ApplicationName:MyApplication /Type:System.BizTalk:File /Overwrite /Source:"C:\Source Files\File.txt" /Destination:"C:\New Files\File.txt" /Server:MyDatabaseServer /Database:BizTalkMgmtDb**</span></span>  
  
   |<span data-ttu-id="1a3fd-132">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1a3fd-132">Parameter</span></span>|<span data-ttu-id="1a3fd-133">値</span><span class="sxs-lookup"><span data-stu-id="1a3fd-133">Value</span></span>|  
   |---------------|-----------|  
   |<span data-ttu-id="1a3fd-134">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="1a3fd-134">**/ApplicationName**</span></span>|<span data-ttu-id="1a3fd-135">ファイルを追加する BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-135">Name of the BizTalk application to which to add the file.</span></span> <span data-ttu-id="1a3fd-136">アプリケーション名が指定されなかった場合、既定の BizTalk アプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-136">If the application name is not specified, the default BizTalk application is used.</span></span> <span data-ttu-id="1a3fd-137">名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-137">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="1a3fd-138">**/型**</span><span class="sxs-lookup"><span data-stu-id="1a3fd-138">**/Type**</span></span>|<span data-ttu-id="1a3fd-139">**System.BizTalk:File** (この値小文字は区別されません)。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-139">**System.BizTalk:File** (This value is not case-sensitive.)</span></span>|  
   |<span data-ttu-id="1a3fd-140">**/上書き**</span><span class="sxs-lookup"><span data-stu-id="1a3fd-140">**/Overwrite**</span></span>|<span data-ttu-id="1a3fd-141">既存のファイルを更新するためのオプション。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-141">Option to update an existing file.</span></span> <span data-ttu-id="1a3fd-142">指定しなかった場合、追加するファイルと同じ名前のファイルが既にアプリケーションに存在した場合、AddResource 操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-142">If not specified, and a file already exists in the application that has the same name as the file being added, the AddResource operation fails.</span></span>|  
   |<span data-ttu-id="1a3fd-143">**/ソース**</span><span class="sxs-lookup"><span data-stu-id="1a3fd-143">**/Source**</span></span>|<span data-ttu-id="1a3fd-144">ファイルの完全パス (ファイル名を含む)。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-144">Full path of the file, including the file name.</span></span> <span data-ttu-id="1a3fd-145">パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-145">If the path includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="1a3fd-146">**/変換先**</span><span class="sxs-lookup"><span data-stu-id="1a3fd-146">**/Destination**</span></span>|<span data-ttu-id="1a3fd-147">アプリケーションを .msi ファイルからインストールしたときにファイルがコピーされる場所 (完全パス)。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-147">Full path of the location where the file is to be copied when the application is installed from the .msi file.</span></span> <span data-ttu-id="1a3fd-148">パスにスペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-148">If the path includes spaces, you must enclose it in double quotation marks (").</span></span> <span data-ttu-id="1a3fd-149">指定しなかった場合、インストール中、このファイルはローカル ファイル システムにコピーされません。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-149">If not provided, the file is not copied to the local file system during installation.</span></span>|  
   |<span data-ttu-id="1a3fd-150">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="1a3fd-150">**/Server**</span></span>|<span data-ttu-id="1a3fd-151">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-151">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="1a3fd-152">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-152">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="1a3fd-153">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-153">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="1a3fd-154">例 :</span><span class="sxs-lookup"><span data-stu-id="1a3fd-154">Examples:</span></span><br /><br /> <span data-ttu-id="1a3fd-155">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="1a3fd-155">Server=MyServer</span></span><br /><br /> <span data-ttu-id="1a3fd-156">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="1a3fd-156">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="1a3fd-157">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-157">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="1a3fd-158">**/データベース**</span><span class="sxs-lookup"><span data-stu-id="1a3fd-158">**/Database**</span></span>|<span data-ttu-id="1a3fd-159">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-159">Name of the BizTalk Management database.</span></span> <span data-ttu-id="1a3fd-160">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a3fd-160">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a3fd-161">参照</span><span class="sxs-lookup"><span data-stu-id="1a3fd-161">See Also</span></span>  
 <span data-ttu-id="1a3fd-162">[.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="1a3fd-162">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 <span data-ttu-id="1a3fd-163">[AddResource コマンド: ファイル](../core/addresource-command-file.md) </span><span class="sxs-lookup"><span data-stu-id="1a3fd-163">[AddResource Command: File](../core/addresource-command-file.md) </span></span>  
 [<span data-ttu-id="1a3fd-164">BizTalk アプリケーションの作成と変更</span><span class="sxs-lookup"><span data-stu-id="1a3fd-164">Creating and Modifying BizTalk Applications</span></span>](../core/creating-and-modifying-biztalk-applications.md)