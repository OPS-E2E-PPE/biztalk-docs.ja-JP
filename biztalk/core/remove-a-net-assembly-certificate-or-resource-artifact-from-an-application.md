---
title: アプリケーションから .NET アセンブリ、証明書、またはその他のリソース アイテムを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0af1ab10400b51515b3041e12935e571eb76be69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397959"
---
# <a name="how-to-remove-a-net-assembly-certificate-or-other-resource-artifact-from-an-application"></a><span data-ttu-id="daaec-102">アプリケーションから .NET アセンブリ、証明書、またはその他のリソース アイテムを削除する方法</span><span class="sxs-lookup"><span data-stu-id="daaec-102">How to Remove a .NET Assembly, Certificate, or Other Resource Artifact from an Application</span></span>
<span data-ttu-id="daaec-103">このトピックでは、BizTalk Server 管理コンソールまたはコマンドラインを使用して BizTalk アプリケーションから次のリソース アイテムを削除する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="daaec-103">This topic describes how to use the BizTalk Server Administration console or the command line to remove the following resource artifacts from a BizTalk application.</span></span> <span data-ttu-id="daaec-104">このトピックの手順を使用すると、BizTalk 管理データベースからアイテムが削除されます。</span><span class="sxs-lookup"><span data-stu-id="daaec-104">Using the procedures in this topic removes the artifact from the BizTalk Management database.</span></span> <span data-ttu-id="daaec-105">これらの場所のいずれかに存在する場合、成果物ファイル システム、証明書ストア、インターネット インフォメーション サービス (IIS)、または、Windows レジストリから削除されません。</span><span class="sxs-lookup"><span data-stu-id="daaec-105">It does not remove the artifact from the file system, certificate store, Internet Information Services (IIS), or the Windows registry, if it exists in any of these locations.</span></span> <span data-ttu-id="daaec-106">さらに、バインド ファイルを削除する場合、バインドは変更されません: バインド ファイルのみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="daaec-106">In addition, if you remove a binding file, the bindings remain unchanged – only the binding file is removed.</span></span>  
  
- <span data-ttu-id="daaec-107">.NET アセンブリ</span><span class="sxs-lookup"><span data-stu-id="daaec-107">.NET assemblies</span></span>  
  
- <span data-ttu-id="daaec-108">COM コンポーネント</span><span class="sxs-lookup"><span data-stu-id="daaec-108">COM components</span></span>  
  
- <span data-ttu-id="daaec-109">証明書</span><span class="sxs-lookup"><span data-stu-id="daaec-109">Certificates</span></span>  
  
- <span data-ttu-id="daaec-110">アドホック ファイル</span><span class="sxs-lookup"><span data-stu-id="daaec-110">Ad hoc files</span></span>  
  
- <span data-ttu-id="daaec-111">BAM 定義</span><span class="sxs-lookup"><span data-stu-id="daaec-111">BAM definitions</span></span>  
  
- <span data-ttu-id="daaec-112">バインド ファイル</span><span class="sxs-lookup"><span data-stu-id="daaec-112">Binding files</span></span>  
  
- <span data-ttu-id="daaec-113">仮想ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="daaec-113">Virtual directories</span></span>  
  
  <span data-ttu-id="daaec-114">仮想ディレクトリがアプリケーションをインポートまたは追加するには、いずれかに明示的に追加された場合は、このトピックの手順を使用して削除できます。</span><span class="sxs-lookup"><span data-stu-id="daaec-114">If a virtual directory is explicitly added to an application, either by being imported from or added, it can be removed by using the procedures in this topic.</span></span> <span data-ttu-id="daaec-115">明示的に追加されていないではなく参照で追加した受信場所の構成時に、このトピックの手順を使用して削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="daaec-115">If it was not explicitly added, but rather was added by reference when a receive location was configured, you cannot remove it by using the procedures in this topic.</span></span> <span data-ttu-id="daaec-116">これは、仮想ディレクトリが BizTalk 管理データベースに格納されていないためにです。</span><span class="sxs-lookup"><span data-stu-id="daaec-116">This is because the virtual directory is not stored in the BizTalk Management database.</span></span> <span data-ttu-id="daaec-117">アプリケーションの .msi ファイルをエクスポートするときに、仮想ディレクトリを IIS から取得したし、.msi ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="daaec-117">When you export the application .msi file the virtual directory will be obtained from IIS and added to the .msi file.</span></span> <span data-ttu-id="daaec-118">.Msi ファイルをインポートするときに仮想ディレクトリがそのグループの BizTalk 管理データベースに追加されます。</span><span class="sxs-lookup"><span data-stu-id="daaec-118">When you import the .msi file, the virtual directory will be added to the BizTalk Management database for that group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="daaec-119">前提条件</span><span class="sxs-lookup"><span data-stu-id="daaec-119">Prerequisites</span></span>  
 <span data-ttu-id="daaec-120">このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="daaec-120">To perform the procedures in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="daaec-121">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="daaec-121">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
## <a name="to-remove-a-resource-artifact-from-an-application"></a><span data-ttu-id="daaec-122">アプリケーションからリソース アイテムを削除するには</span><span class="sxs-lookup"><span data-stu-id="daaec-122">To remove a resource artifact from an application</span></span>  
  
#### <a name="using-the-biztalk-server-administration-console"></a><span data-ttu-id="daaec-123">BizTalk Server 管理コンソールの使用</span><span class="sxs-lookup"><span data-stu-id="daaec-123">Using the BizTalk Server Administration console</span></span>  
  
1. <span data-ttu-id="daaec-124">クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。</span><span class="sxs-lookup"><span data-stu-id="daaec-124">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="daaec-125">コンソール ツリーで、BizTalk Server 管理コンソールを展開、およびを削除するリソース アイテムが含まれる BizTalk グループを展開し、成果物を含むアプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="daaec-125">In the console tree, expand BizTalk Server Administration, expand the BizTalk group containing the resource artifact to remove, and then expand the application containing the artifact.</span></span>  
  
3. <span data-ttu-id="daaec-126">をクリックして、**リソース**フォルダーは、アイテムを右クリックし、順にクリックします**削除**します。</span><span class="sxs-lookup"><span data-stu-id="daaec-126">Click the **Resources** folder, right-click the artifact, and then click **Remove**.</span></span>  
  
#### <a name="using-the-command-line"></a><span data-ttu-id="daaec-127">コマンドラインを使用</span><span class="sxs-lookup"><span data-stu-id="daaec-127">Using the command line</span></span>  
  
1. <span data-ttu-id="daaec-128">次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型`cmd`、順にクリックします**OK**。</span><span class="sxs-lookup"><span data-stu-id="daaec-128">Open a command prompt as follows: Click **Start**, click **Run**, type `cmd`, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="daaec-129">次の表に示すように、適切な値を置き換えて、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="daaec-129">Type the following command, substituting the appropriate values, as described in the following table:</span></span>  
  
    <span data-ttu-id="daaec-130">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span><span class="sxs-lookup"><span data-stu-id="daaec-130">**BTSTask RemoveResource** [**/ApplicationName:**<em>value</em>] **/Luid:**<em>value</em> [**/Server:**<em>value</em>] [**/Database:**<em>value</em>]</span></span>  
  
    <span data-ttu-id="daaec-131">例:</span><span class="sxs-lookup"><span data-stu-id="daaec-131">Example:</span></span>  
  
    <span data-ttu-id="daaec-132">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span><span class="sxs-lookup"><span data-stu-id="daaec-132">**BTSTask RemoveResource /ApplicationName:MyApplication /Luid:"MyAssembly, Version=1.0.0.0, Culture=neutral, PublicKeyToken=0123456789ABCDEF"**</span></span>  
  
   |<span data-ttu-id="daaec-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="daaec-133">Parameter</span></span>|<span data-ttu-id="daaec-134">説明</span><span class="sxs-lookup"><span data-stu-id="daaec-134">Description</span></span>|  
   |---------------|-----------------|  
   |<span data-ttu-id="daaec-135">**/ApplicationName**</span><span class="sxs-lookup"><span data-stu-id="daaec-135">**/ApplicationName**</span></span>|<span data-ttu-id="daaec-136">削除するアイテムが含まれる BizTalk アプリケーションの名前です。</span><span class="sxs-lookup"><span data-stu-id="daaec-136">Name of the BizTalk application containing the artifact to delete.</span></span> <span data-ttu-id="daaec-137">指定しなかった場合、既定のアプリケーションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="daaec-137">If not specified, the default application is used.</span></span> <span data-ttu-id="daaec-138">名前にスペースが含まれている場合は、二重引用符 (") で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="daaec-138">If the name includes spaces, you must enclose it in double quotation marks (").</span></span>|  
   |<span data-ttu-id="daaec-139">**/Luid**</span><span class="sxs-lookup"><span data-stu-id="daaec-139">**/Luid**</span></span>|<span data-ttu-id="daaec-140">成果物のローカルで一意の識別子 (LUID)。</span><span class="sxs-lookup"><span data-stu-id="daaec-140">Locally unique identifier (LUID) of the artifact.</span></span> <span data-ttu-id="daaec-141">LUID を取得するにを使用して、 **ListApp** 」の説明に従って、コマンド[ListApp コマンド](../core/listapp-command.md)します。</span><span class="sxs-lookup"><span data-stu-id="daaec-141">You can obtain the LUID by using the **ListApp** command, as described in [ListApp Command](../core/listapp-command.md).</span></span>|  
   |<span data-ttu-id="daaec-142">**/サーバー**</span><span class="sxs-lookup"><span data-stu-id="daaec-142">**/Server**</span></span>|<span data-ttu-id="daaec-143">BizTalk 管理データベースをホストする SQL Server インスタンスの名前。ServerName\InstanceName,Port の形式で指定します。</span><span class="sxs-lookup"><span data-stu-id="daaec-143">Name of the SQL Server instance hosting the BizTalk Management database, in the form ServerName\InstanceName,Port.</span></span><br /><br /> <span data-ttu-id="daaec-144">インスタンス名の指定は、そのインスタンス名がサーバー名と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="daaec-144">Instance name is only required when the instance name is different than the server name.</span></span> <span data-ttu-id="daaec-145">ポートの指定は、SQL Server で使用するポート番号が既定値 (1433) と異なる場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="daaec-145">Port is only required when SQL Server uses a port number other than the default (1433).</span></span><br /><br /> <span data-ttu-id="daaec-146">例 :</span><span class="sxs-lookup"><span data-stu-id="daaec-146">Examples:</span></span><br /><br /> <span data-ttu-id="daaec-147">Server=MyServer</span><span class="sxs-lookup"><span data-stu-id="daaec-147">Server=MyServer</span></span><br /><br /> <span data-ttu-id="daaec-148">Server=MyServer\MySQLServer,1533</span><span class="sxs-lookup"><span data-stu-id="daaec-148">Server=MyServer\MySQLServer,1533</span></span><br /><br /> <span data-ttu-id="daaec-149">指定しなかった場合、ローカル コンピューターで実行されている SQL Server インスタンスの名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="daaec-149">If not provided, the name of the SQL Server instance running on the local computer is used.</span></span>|  
   |<span data-ttu-id="daaec-150">**/Database**</span><span class="sxs-lookup"><span data-stu-id="daaec-150">**/Database**</span></span>|<span data-ttu-id="daaec-151">BizTalk 管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="daaec-151">Name of the BizTalk Management database.</span></span> <span data-ttu-id="daaec-152">指定しなかった場合、SQL Server のローカル インスタンスで実行されている BizTalk 管理データベースが使用されます。</span><span class="sxs-lookup"><span data-stu-id="daaec-152">If not specified, the BizTalk Management database running in the local instance of SQL Server is used.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="daaec-153">参照</span><span class="sxs-lookup"><span data-stu-id="daaec-153">See Also</span></span>  
 <span data-ttu-id="daaec-154">[.NET アセンブリ、証明書、およびその他のリソースを管理します。](../core/managing-net-assemblies-certificates-and-other-resources.md) </span><span class="sxs-lookup"><span data-stu-id="daaec-154">[Managing .NET Assemblies, Certificates, and Other Resources](../core/managing-net-assemblies-certificates-and-other-resources.md) </span></span>  
 [<span data-ttu-id="daaec-155">RemoveResource コマンド</span><span class="sxs-lookup"><span data-stu-id="daaec-155">RemoveResource Command</span></span>](../core/removeresource-command.md)