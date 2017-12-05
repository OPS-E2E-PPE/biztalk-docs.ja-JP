---
title: "アプリケーションから .NET アセンブリ、証明書、またはその他のリソース アイテムを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- virtual directories, deleting
- managing [.NET assemblies], deleting
- managing [applications], COM components
- managing [applications], deleting artifcats
- managing [certificates], deleting
- deleting, binding files
- binding files, deleting
- managing, COM components
- COM components, deleting
- managing [artifacts], deleting
- .NET assemblies, deleting
- deleting, virtual directories
- deleting, definitions [BAM]
- applications, .NET assemblies
- certificates, deleting
- deleting, .NET assemblies
- deleting, artifacts
- deleting, certificates
ms.assetid: b84eebac-261d-495f-80cd-ddda5bb08bef
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12196886285a84b391eb3037064f36f08aa5b1fe
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-remove-a-net-assembly-certificate-or-other-resource-artifact-from-an-application"></a><span data-ttu-id="df592-102">.NET アセンブリ、証明書またはその他のリソース アイテムをアプリケーションから削除する方法</span><span class="sxs-lookup"><span data-stu-id="df592-102">How to Remove a .NET Assembly, Certificate, or Other Resource Artifact from an Application</span></span>
<span data-ttu-id="df592-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンドラインを使用して BizTalk アプリケーションから、次のリソース アイテムを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="df592-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove the following resource artifacts from a BizTalk application.</span></span> <span data-ttu-id="df592-104">このトピックの手順を実行すると、BizTalk 管理データベースからアイテムが削除されます。</span><span class="sxs-lookup"><span data-stu-id="df592-104">Using the procedures in this topic removes the artifact from the BizTalk Management database.</span></span> <span data-ttu-id="df592-105">ただし、ファイル システム、証明書ストア、インターネット インフォメーション サービス (IIS)、または Windows レジストリからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="df592-105">It does not remove the artifact from the file system, certificate store, Internet Information Services (IIS), or the Windows registry, if it exists in any of these locations.</span></span> <span data-ttu-id="df592-106">また、バインド ファイルを削除した場合、バインド ファイルが削除されるのみで、バインドそのものは変更されません。</span><span class="sxs-lookup"><span data-stu-id="df592-106">In addition, if you remove a binding file, the bindings remain unchanged – only the binding file is removed.</span></span>  
  
-   <span data-ttu-id="df592-107">.NET アセンブリ</span><span class="sxs-lookup"><span data-stu-id="df592-107">.NET assemblies</span></span>  
  
-   <span data-ttu-id="df592-108">COM コンポーネント</span><span class="sxs-lookup"><span data-stu-id="df592-108">COM components</span></span>  
  
-   <span data-ttu-id="df592-109">証明書</span><span class="sxs-lookup"><span data-stu-id="df592-109">Certificates</span></span>  
  
-   <span data-ttu-id="df592-110">アドホック ファイル</span><span class="sxs-lookup"><span data-stu-id="df592-110">Ad hoc files</span></span>  
  
-   <span data-ttu-id="df592-111">BAM 定義</span><span class="sxs-lookup"><span data-stu-id="df592-111">BAM definitions</span></span>  
  
-   <span data-ttu-id="df592-112">バインド ファイル</span><span class="sxs-lookup"><span data-stu-id="df592-112">Binding files</span></span>  
  
-   <span data-ttu-id="df592-113">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="df592-113">Virtual directories</span></span>  
  
 <span data-ttu-id="df592-114">インポートまたは追加によって仮想ディレクトリを明示的にアプリケーションに追加した場合は、このトピックの手順を使用して仮想ディレクトリを削除できます。</span><span class="sxs-lookup"><span data-stu-id="df592-114">If a virtual directory is explicitly added to an application, either by being imported from or added, it can be removed by using the procedures in this topic.</span></span> <span data-ttu-id="df592-115">仮想ディレクトリを明示的に追加せず、受信場所の構成時に参照で追加した場合は、このトピックの手順を使用して仮想ディレクトリを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="df592-115">If it was not explicitly added, but rather was added by reference when a receive location was configured, you cannot remove it by using the procedures in this topic.</span></span> <span data-ttu-id="df592-116">これは、仮想ディレクトリが BizTalk 管理データベースに格納されないためです。</span><span class="sxs-lookup"><span data-stu-id="df592-116">This is because the virtual directory is not stored in the BizTalk Management database.</span></span> <span data-ttu-id="df592-117">アプリケーションの .msi ファイルをエクスポートすると、IIS から仮想ディレクトリが取得され、.msi ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="df592-117">When you export the application .msi file the virtual directory will be obtained from IIS and added to the .msi file.</span></span> <span data-ttu-id="df592-118">.msi ファイルをインポートすると、そのグループの BizTalk 管理データベースに仮想ディレクトリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="df592-118">When you import the .msi file, the virtual directory will be added to the BizTalk Management database for that group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="df592-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="df592-119">Prerequisites</span></span>  
 <span data-ttu-id="df592-120">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="df592-120">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="df592-121">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。</span><span class="sxs-lookup"><span data-stu-id="df592-121">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-resource-artifact-from-an-application"></a><span data-ttu-id="df592-122">アプリケーションからリソース アイテムを削除するには</span><span class="sxs-lookup"><span data-stu-id="df592-122">To remove a resource artifact from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="df592-123">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="df592-123">Using the BizTalk Server Administration console</span></span>  
  
1.  <span data-ttu-id="df592-124">をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="df592-124">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="df592-125">コンソール ツリーで、BizTalk Server 管理コンソールを展開し、削除するには、リソース アイテムが含まれる BizTalk グループを展開し、成果物を含むアプリケーションの順に展開します。</span><span class="sxs-lookup"><span data-stu-id="df592-125">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the resource artifact to remove, and then expand the application containing the artifact.</span></span>  
  
3.  <span data-ttu-id="df592-126">クリックして、**リソース**フォルダーは、アイテムを右クリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="df592-126">Click the **Resources** folder, right-click the artifact, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="df592-127">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="df592-127">Using the command line</span></span>  
  
1.  <span data-ttu-id="df592-128">次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリック**ok**です。</span><span class="sxs-lookup"><span data-stu-id="df592-128">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="df592-129">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="df592-129">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
     <span data-ttu-id="df592-130">**BTSTask RemoveResource** [**/applicationname は:***値*] **/Luid:***値*[**/Server:***値*] [**/database:***値*]</span><span class="sxs-lookup"><span data-stu-id="df592-130">**BTSTask RemoveResource** [**/ApplicationName:***value*] **/Luid:***value* [**/Server:***value*] [**/Database:***value*]</span></span>  
  
     <span data-ttu-id="df592-131">例:</span><span class="sxs-lookup"><span data-stu-id="df592-131">Example:</span></span>  
  
     <span data-ttu-id="df592-132">**BTSTask RemoveResource applicationname: myapplication/Luid:"MyAssembly, バージョン 1.0.0.0、Culture = neutral, PublicKeyToken = = 0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="df592-132">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
    |<span data-ttu-id="df592-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df592-133">Parameter</span></span>|<span data-ttu-id="df592-134">Description</span><span class="sxs-lookup"><span data-stu-id="df592-134">Description</span></span>|  
    |---------------|-----------------|  
    |<span data-ttu-id="df592-135">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="df592-135">**/ApplicationName**</span></span>|<span data-ttu-id="df592-136">削除するアイテムが存在する BizTalk アプリケーションの名前。</span><span class="sxs-lookup"><span data-stu-id="df592-136">Name of the BizTalk application containing the artifact to delete.</span></span> <span data-ttu-id="df592-137">指定しなかった場合、既定のアプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="df592-137">If not specified, the default application is used.</span></span> <span data-ttu-id="df592-138">名前には、スペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="df592-138">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
    |<span data-ttu-id="df592-139">**/Luid**</span><span class="sxs-lookup"><span data-stu-id="df592-139">**/Luid**</span></span>|<span data-ttu-id="df592-140">アイテムのローカル一意識別子 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="df592-140">Locally unique identifier (LUID) of the artifact.</span></span> <span data-ttu-id="df592-141">使用して、LUID を取得することができます、 **ListApp**コマンドを」の説明に従って[ListApp コマンド](../core/listapp-command.md)です。</span><span class="sxs-lookup"><span data-stu-id="df592-141">You can obtain the LUID by using the **ListApp** command, as described in [ListApp Command](../core/listapp-command.md).</span></span>|  
    |<span data-ttu-id="df592-142">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="df592-142">**/Server**</span></span>|<span data-ttu-id="df592-143">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="df592-143">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="df592-144">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="df592-144">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="df592-145">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="df592-145">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="df592-146">例 :</span><span class="sxs-lookup"><span data-stu-id="df592-146">Examples:</span></span><br /><br /> <span data-ttu-id="df592-147">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="df592-147">Server=MyServer</span></span><br /><br /> <span data-ttu-id="df592-148">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="df592-148">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="df592-149">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="df592-149">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
    |<span data-ttu-id="df592-150">**/データベース**</span><span class="sxs-lookup"><span data-stu-id="df592-150">**/Database**</span></span>|<span data-ttu-id="df592-151">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="df592-151">Name of the BizTalk Management database.</span></span> <span data-ttu-id="df592-152">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="df592-152">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df592-153">参照</span><span class="sxs-lookup"><span data-stu-id="df592-153">See Also</span></span>  
 <span data-ttu-id="df592-154">[.NET アセンブリ、証明書、およびその他のリソースの管理](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="df592-154">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 [<span data-ttu-id="df592-155">RemoveResource コマンド</span><span class="sxs-lookup"><span data-stu-id="df592-155">RemoveResource Command</span></span>](../core/removeresource-command.md)